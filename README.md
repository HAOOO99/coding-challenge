# RewardPay Coding Challenge


## Program running 
- First run `npm install` to install the necessary libraries of the application
- Use `npm run dev` to start the application the final result will show through the terminal 
- Use `npm run test` to start the unit test process.


## Calculations

Use the formulas below to calculate your values:

### Revenue

This should be calculated by adding up all the values under `total_value` where the `account_category` field is set to `revenue`

### Expenses

This should be calculated by adding up all the values under `total_value` where the `account_category` field is set to `expense`

### Gross Profit Margin

This is calculated in two steps: first by adding all the `total_value` fields where the `account_type` is set to `sales` and the `value_type` is set to `debit`; then dividing that by the `revenue` value calculated earlier to generate a percentage value.

### Net Profit Margin

This metric is calculated by subtracting the `expenses` value from the `revenue` value and dividing the remainder by `revenue` to calculate a percentage.

### Working Capital Ratio

This is calculated dividing the `assets` by the `liabilities` creating a percentage value where `assets` are calculated by:

- adding the `total_value` from all records where the `account_category` is set to `assets`, the `value_type` is set to `debit`, and the `account_type` is one of `current`, `bank`, or `current_accounts_receivable`
- subtracting the `total_value` from all records where the `account_category` is set to `assets`, the `value_type` is set to `credit`, and the `account_type` is one of `current`, `bank`, or `current_accounts_receivable`

and liabilities are calculated by:

- adding the `total_value` from all records where the `account_category` is set to `liability`, the `value_type` is set to `credit`, and the `account_type` is one of `current` or `current_accounts_payable`
- subtracting the `total_value` from all records where the `account_category` is set to `liability`, the `value_type` is set to `debit`, and the `account_type` is one `current` or `current_accounts_payable`

## Formatting

All currency figures must be formatted as follows:
- The value is prefixed with a `$` sign
- A comma is used to separate every 3 digits in the thousands, millions, billions, and trillions
- Cents are removed

All percentage values must be formatted to one decimal digit and be prefixed with a `%` sign.  Don't forget to multiply by 100 each time you're tasked with calculating a percentage value.

## Example

Below is what a typical output should look like.  Please note this is *not* the output of the challenge but a mere example.

```
$ ./myChallenge
Revenue: $519,169
Expenses: $411,664
Gross Profit Margin: 22%
Net Profit Margin: 21%
Working Capital Ratio: 95%
```

