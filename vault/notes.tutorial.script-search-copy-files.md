---
id: Pw7yTOYQHdrW6wez
title: Script Search Copy Files
desc: ''
updated: 1639453032297
created: 1626218661316
---
# Use Python to automate boring task 'Search and Copy files'

## Situation: 
I have many files whose filenames are stored in a column in an Excel file. I want to search these files, which were stored locally in my computer, and then copy them to a designated folder. I’m using MacOS X (version 10.11.6).

The structure of the Excel file is as follow.
![structure-excel-file](https://i.imgur.com/troM71w.png){max-width: 300px, display: block, margin: 0 auto}


## Solution:

Use `Applescript` (via `Automator`) or `Python`.

### My choice: Use `Python`  
Idea: write a python script that read input from a `listFile.csv`, search for all filenames in that csv file from a designated folder path, then copy all found files to a folder. Run the script by excecuting in terminal
```bash
> python3 searchCopy.py
```

Clone this [gist](https://gist.github.com/h7b/70646c21acf1bc9e83c405ef14cbf1f9) in a folder and practice.

### Another choice: Use `AppleScript`
ref: [discussion in Apple Communities](https://discussions.apple.com/thread/5528059?tstart=0)

In order to use AppleScript, I need to locate `Applescript Editor` in `/Applications/Utilities` (or search for it in `Spotlight`). Then I copy the script into Automator (as indicated in the screencap below)

![screencap01](https://i.imgur.com/YFb4Ft4.png){max-width: 300px, display: block, margin: 0 auto}

Thoughts: I tried but did not successfully with these AppleScript, just listed here for references.

#### Method 1:
Search entire directory including subfolders
> Note: the Excel file must be opened while script being executed

```AppleScript
set theDirectory to quoted form of POSIX path of (choose folder with prompt "Select Search Directory")
set theDestination to quoted form of POSIX path of (choose folder with prompt "Select Directory to Copy Files")
 
tell application "Microsoft Excel"
    tell active sheet
        tell used range
            set rc to count of rows
        end tell
            set theList to get value of range ("B1:B" & rc) as list
            repeat with theItem in theList
                if contents of theItem is not {""} then
                  do shell script "find " & theDirectory & " -iname '" & theItem & "*' -exec cp {} " & theDestination & " \\;"
                end if
            end repeat
    end tell
end tell
```

#### Method 2:
Search entire directory,subfolders included, for an exact match. Then output an error if the file does not exist (in a file named “error.txt” on the Desktop)

> Note: the Excel file must be opened while script being executed

```AppleScript
set theDirectory to quoted form of POSIX path of (choose folder with prompt "Select Search Directory")
set theDestination to quoted form of POSIX path of (choose folder with prompt "Select Directory to Copy Files")
 
tell application "Microsoft Excel"
    tell active sheet
        tell used range
            set rc to count of rows
        end tell
            set theList to get value of range ("B1:B" & rc) as list
            repeat with theItem in theList
                if contents of theItem is not {""} then
                    try
                        do shell script "cp  " & theDirectory & "/" & theItem & space & theDestination
                    on error
                        do shell script "echo " & theDirectory & "/" & theItem & " does not exist >> ~/Desktop/error.txt"
                    end try
                end if
            end repeat
    end tell
end tell
```

#### Method 3:
To avoid scripting the various spreadsheet apps, an idea comes up where the user selects the cells in spreadsheet apps, copies to clipboard, and then the script processes the data copied to clipboard instead of relying on data in spreadsheet apps.  
The following AppleScript which is a mere wrapper of bash script. Names are assumed to be given by TSV (tab separated values) text in the clipboard. Only the first field (column) is used. Line may be terminated by CRLF, CR or LF. Currently given name is foreward matched in file name. Verbose output of cp(1) and error messages if any are returned in the result pane/window of Script Editor.
```AppleScript
set src to (choose folder with prompt "Choose source folder")'s POSIX path
set dst to (choose folder with prompt "Choose destination folder")'s POSIX path
set args to ""
repeat with a in {src, dst}
    set args to args & a's quoted form & space
end repeat
do shell script "/bin/bash -s <<'EOF' - " & args & "
SRC=$1
DST=$2
export LC_CTYPE=UTF-8
{
while IFS=$'\\t' read -r name rest
do
    [[ -z $name ]] && continue
    find \"$SRC\" -type f -iname \"$name\"\\* -print0 | xargs -0 -J% cp -v -pPR % \"$DST\"
done < <(pbpaste | perl -CS -ln0e 'map {print quotemeta} split /\\r\\n|\\r|\\n/') } 2>&1
exit 0
EOF"
```