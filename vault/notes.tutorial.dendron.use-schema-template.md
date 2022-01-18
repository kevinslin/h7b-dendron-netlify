---
id: 0CUUNDwNeRutJrqHZATuk
title: Use Schema Template
desc: ''
updated: 1642466332203
created: 1642443093888
---
# How I use schema and templates in Dendron
ref: [Dendron wiki | Making Your First Schema](https://wiki.dendron.so/notes/5U4eAiqshI67VxIL40KWH/)

[Templates](https://wiki.dendron.so/notes/861cbdf8-102e-4633-9933-1f3d74df53d2/) are notes with pre-outlined content meant for reuse

[Schema](https://wiki.dendron.so/notes/c5e5adde-5459-409b-b34d-a0d75cbb1052/) is a *YAML* file that helps you to apply consistent structure to all your notes. One of the primary capabilities for schema is to automatically insert templates into new notes

## Situation

I want to create a schema and template for my notes in `reading` section.

## Solution
I follow this [guide](https://wiki.dendron.so/notes/5U4eAiqshI67VxIL40KWH/) to
1. Create a `reading` template  
    ![[templates.reading]]
    Next, in the frontmatter of `templates.md`, set `nav_exclude: true` to hide this note in the navigation bar
2. Create a `reading` schema
    ```yaml
    # Schema for my reading notes
    # It wil match 
    #     root.reading
    #     root.reading.note1
    #     root.reading.note2
    # It will not match
    #     root.reading.note1.highlight
    
    version: 1
    imports: []
    schemas:
      - id: reading
        children: []
        title: reading note
        parent: root
        namespace: true
        template: templates.reading
    ```

DONE

## Usage
When I want to create new note in `reading` section
1. Open `Dendron: Lookup Note` (`Ctrl+L`)
2. Type in: `reading.new-note-name`

Result: a new note will be created with info from `reading` template.

## Helpful resources:
- [Ryan Randall | some-dendron-starter-files](https://github.com/ryan-p-randall/some-dendron-starter-files)
- [Bassmann | dendron-schemas](https://github.com/Bassmann/Dendron-schemas)