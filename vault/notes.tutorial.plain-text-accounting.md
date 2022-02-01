---
id: BMYLBFSZCzSdDt1hjzmA0
title: Plain Text Accounting
desc: ''
updated: 1643684249215
created: 1643679182773
---
# Plain text accounting with Beancount

ref:
- [plain text accounting](https://plaintextaccounting.org/)
- [Blog de Cyril Deguet | Beancount ou la comptabilité pour les hackers](https://cyril.deguet.com/fr/2015/09/03/beancount-comptabilite-pour-hackers/)
- [Leo's Blog | No-Bullshit Beancount Introduction](https://blog.leononame.dev/2019/08/beancount/)

`Plain text accounting` means doing accounting with plain text data formats and scriptable software

Beancount does not represent time, only dates. The minimal time interval is one day.

Currencies must be entirely in capital letters (allowing numbers and some special characters, like “_” or “-”). Currency symbols (such as $ or €) are not supported. The syntax for a currency is a word all in capital letters like "USD, CAD, MSFT"

In beancount, a comment is declared by a semicolon `;`. Any text on a line after the character `;` is ignored.

Syntax directives
- Open a new account. Accounts must be opened before being referenced.
  ```text
  2018-09-27 open Assets:EUR:Cash
  ```
- Close an account. No transactions may post here after this date.
  ```text
  2017-02-28 close Assets:EUR:BankAccount
  ```
- Transactions
  - A basic transaction `txn` looks like this. Each line below a transaction is called a `posting`.
  ```text
  2019-08-05 txn "Coffee"
    Assets:EUR:Cash     -1.20 EUR
    Expenses:Coffee     1.20 EUR
  ```
  - The sum of all postings must be 0. You may leave out one amount which will automatically get calculated
  ```text
  2019-08-12 txn "Supermarket"
    Assets:EUR:Cash     -17.85 EUR
    Expenses:Groceries
  ```
  - Instead of the keyword `txn`, you may use a flag to indicate a transaction. There are two available flags `*` and `!`
  ```text
  ; This is a complete transaction
  2019-08-13 * "Train to work"
    Assets:EUR:Cash                 -2.50 EUR
    Expenses:Transportation:Train
    
  ; This is an incomplete transaction
  2019-08-13 ! "Bus to Susan's House"
    Assets:EUR:Bank                 -2.00 EUR
    Expenses:Transportation:Bus
  ```
  - It’s also possible to flag a single `posting` in a transaction:
  ```text
  2019-07-28 * "Concert Ticket Gorillaz"
    ! Assets:EUR:Bank                 -47.00 EUR
    Expenses:Entertainment
  ```
- Define the price of a commodity for a given date
  ```text
  2019-08-06 price A0MW0M 5.41 EUR
  ```
- Transactions can also be linked together
  ```text
  2014-02-05 * "Invoice for January" ^invoice-pepe-studios-jan14
  Income:Clients:PepeStudios           -8450.00 USD
  Assets:AccountsReceivable

  2014-02-20 * "Check deposit - payment from Pepe" ^invoice-pepe-studios-jan14
  Assets:BofA:Checking                  8450.00 USD
  Assets:AccountsReceivable
  ```
- A `Note` directive is used to attach a dated comment to the journal of a particular account
  ```text
  2013-11-03 note Liabilities:CreditCard "Called about fraudulent card."
  ```
- A `Document` directive can be used to attach an external file to the journal of an account
  ```text
  2013-11-03 document Liabilities:CreditCard "/home/joe/stmts/apr-2014.pdf"
  ```

We can rename the account name
```text
; Options pour renommer les catégories de base
option "name_assets" "Actif"
option "name_liabilities" "Passif"
option "name_equity" "Capital"
option "name_income" "Recettes"
option "name_expenses" "Depenses"
option "account_previous_balances" "SoldeOuverture"
option "account_previous_earnings" "Benefice:Precedents"
option "account_current_earnings" "Benefice:Courant"
```
So the printed balance sheet would be displayed as follows.
![beancount-renamed](https://cyril.deguet.com/images/beancount-bilan.png){max-width: 300px, display: block, margin: 0 auto}

Formatting is critical
- Indent the second and following lines of each transaction. The first line of each transaction needs to be flush left.
- you need at least two spaces between the category ”Expenses:Household,” below) and the amount of the transaction (“20.00 USD”)
  ```text
  2017/01/15 Acme
  Expenses:Household[space][space]$20.00
  Liabilities:CreditCard
  ```

## Related resources:

- [Awesome Beancount | curated list of resources for Beancount](https://awesome-beancount.com/)
- [Hacker News | Beancount: Double-entry accounting from text files](https://news.ycombinator.com/item?id=30138434)
- [Hacker News | Simple Personal Finance Tracking with GnuCash](https://news.ycombinator.com/item?id=23237687)
- [GUI interface for Beancount](https://beancount.github.io/fava/)
- [Beancount Language Syntax](https://beancount.github.io/docs/beancount_language_syntax.html)
- [Beancount | Command-line Accounting Cookbook](https://beancount.github.io/docs/command_line_accounting_cookbook.html)
- [Don't Sink Your First Attempts at Plaintext Accounting ](https://github.com/plaintextaccounting/plaintextaccounting/wiki/Don't-Sink-Your-First-Attempts-at-Plaintext-Accounting)