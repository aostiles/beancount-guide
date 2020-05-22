# Adding Transactions

Now that our folders and accounts are created, we're finally ready to model
our finances for the month of May.

Let's pretend this is the situation:

- We went into May with $200 in our checking account (true on May 2nd)
- We bought groceries for $75 on May 5th.
- We got paid $100 on May 15th.
- We bough a sandbag for $50 on May 20th.

By the end of May, we should have $175 in our checking account:

```
200 - 75 + 100 - 50 = 175
```

## Starting with $200

As you recall, we put
```
2020-05-02 balance Assets:Checking           200.00 USD
```
in our `main.bean` file. This is a balance statement and is read like this:
"On May 5th, 2020, at the _beginning of day_, the 'Assets:Checking' account has $200."

We put the balance statement in our `main.bean` file because it reflects the balance of our checking account _at the start of time_. However, I find it useful to put balance statements pertaining to a month and account in the corresponding file for that month + account.
It doesn't hurt to repeat balance statements twice.

Let's open up `2020/05/wf_checking.bean` and put in the balance statement:
```
2020-05-02 balance Assets:Checking 200.00 USD
```
If we run `bean-check main.bean`, we should see no error.

## Buying Groceries for $75

Let's add a transaction to `wf_checking.bean` to represent our grocery purchase on May 5th:
```
2020-05-05 * "grocery outlet"
    Expenses:Food:Groceries 75.00 USD
    Assets:Checking
```
Let's break down that transaction a bit. It starts with a date. The `*` is a "posting" feature of Beancount I don't use. Let's not worry about that.  
We then see a note: apparently we bought these groceries at Grocery Outlet.  

Indented, are the two "legs" of the transaction. Every transaction has two legs. Such is the principle of double-entry accounting. **If money is going into an account, it must be coming out of another.**

We're taking $75 from our checking account and "adding" it to one of our expense accounts. We could equivalently write:
```
2020-05-05 * "grocery outlet"
    Assets:Checking -75.00 USD
    Expenses:Food:Groceries
```

Whichever way you prefer to write transactions is up to you. You can even mix & match.  
Run `bean-check main.bean` again and see no error.

## Getting Paid

I represent paychecks by deductions from my `Income:Salary` account and additions to my `Assets:Checking` account.

The more salary I accumulate over my lifetime, the more negative `Income:Salary` goes. The difference between `-1 * Income:Salary` and `Assets:Checking + Assets:Savings` depresses me.

Let's get paid:

```
2020-05-15 * "paycheck"
    Assets:Checking 100.00 USD
    Income:Salary
```

Again, `bean-check main.bean` should produce no error.

## Buying a Sandbag

That $100 is burning a hole in our pocket and COVID-19 is burning our lungs. We need to train:
```
2020-05-20 * "sandbag"
    Expenses:Fitness 50.00 USD
    Assets:Checking
```

# Wrapping Up

My `wf_checking.bean` file now looks like this:
```
2020-05-02 balance Assets:Checking 200.00 USD

2020-05-05 * "grocery outlet"
    Expenses:Food:Groceries 75.00 USD
    Assets:Checking

2020-05-15 * "paycheck"
    Assets:Checking 100.00 USD
    Income:Salary

2020-05-20 * "sandbag"
    Expenses:Fitness 50.00 USD
    Assets:Checking
```
`bean-check main.bean` produces no errors. If you change any of the dollar values in `wf_checking.bean` and re-run `bean-check main.bean`, you should see an error.

We _could_ add another balance assertion on 05-31 or 06-01 to reflect the $175 in our checking account.  
In the next section, we'll instead use the reporting features of Beancount to get the same information.