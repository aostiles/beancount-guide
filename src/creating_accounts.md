# Creating Accounts

Beancount accounts are not like your bank accounts.  

The main types of Beancount accounts are:

- Equity
- Assets
- Liabilities
- Expenses
- Income

Open `main.bean` and insert:

```
option "operating_currency" "USD"
2020-05-01 open Equity:Opening-Balances USD
2020-05-01 open Assets:Checking USD
2020-05-01 open Income:Salary USD
2020-05-01 open Expenses:Food:Groceries USD
2020-05-01 open Expenses:Fitness USD
```

We've told Beancount that we're using US Dollars and created two expense accounts:

- Expenses:Food:Groceries
- Expenses:Fitness

Notice the two colons in `Expenses:Food:Groceries`. This is an expense account to track food purchases, specifically groceries. If we go to restaurants, we can create an additional `Expenses:Food:Restaurants` account. If we then want to know our total spending on groceries + restaurants, we can ask Beancount to sum all the `Expenses:Food` accounts.

We've also created three other accounts:

- Equity:Opening-Balances
- Assets:Checking
- Income:Salary

Now add the following two lines to `main.bean`:

```
2020-05-01 pad     Assets:Checking Equity:Opening-Balances
2020-05-02 balance Assets:Checking           200.00 USD
```

Replace `200.00` with the balance of your checking account.

We've used a `pad` "directive" to tell Beancount to take as much money as needed from the `Equity:Opening-Balances` account to make the balance statement true.

---

We're now going to move out of the `main.bean` file and use the month-specific folders we set up earlier.

First we have to _tell_ `main.bean` about those folders. Add the following line to `main.bean`:

```
include "2020/includes.bean"
```

This line tells `main.bean` to include all the statements and transactions we define in our `includes.bean` file inside our `2020` folder. The nice part about structuring our files & folders this way is that we only need to modify `main.bean` once per year.

Let's open up our `2020/includes.bean` file and add the following line:

```
include "05/wf_checking.bean"
```

Now the transactions and statements inside `2020/05/wf_checking.bean` will be checked when
we do `bean-check main.bean`. `main.bean` includes `2020/includes.bean` which in turn includes `05/wf_checking.bean`.
