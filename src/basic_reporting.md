# Basic Reporting

We can get a list of all our accounts' balances with the following command:
```
bean-report main.bean balances
```
If you've been following along, it should look like this:
```
Assets:Checking           175.00 USD
Equity:Opening-Balances  -200.00 USD
Expenses:Fitness           50.00 USD
Expenses:Food:Groceries    75.00 USD
Income:Salary            -100.00 USD
Liabilities
```
Our checking account has $175 as expected. We see that we've been paid $100 over our lifetime. We see the lifetime sums of our expense accounts. We have no liabilities (useful for credit cards). We see that we started with $200 before we began tracking our finances with Beancount.

For more interactive analysis, we can use Fava:
```
fava main.bean
```

# Conclusion

Thanks for following along. If you have scenarios you'd like to see covered,
<A HREF="&#109;&#97;&#105;&#108;&#116;&#111;&#58;%61%6E%64%72%65%77%40%61%6F%73%74%69%6C%2E%65%73">email me</A>.  
Better yet, submit a pull request at <http://aostiles.github.io/beancount-guide>.