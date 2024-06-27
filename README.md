# Equities Scraper

Get the most recent equities data from Alpha Vantage Api

- Scraping Supports
  - Income Statements
  - Balance Sheets
  - Cash Flow Statements

---

### Setup

1. Clone git repository: `git clone https://github.com/PrimalFinance/EquitiesScraper.git`
2. Configure the "config.json" file.

```
    {
        "data_export_path": "D:\\PATH TO EXPORT DATA"
    }

```

3. Install the projects requirements with `pip install -r requirements.txt`

### Instructions

- Create a class instance.

```
    e = EquityScraper("Alpha Vantage Api Key Here")
```

###### Income Statement

- Get the quarterly income statement for Apple Inc. (AAPL).
- Force update to local data with `e.update_income_statement(ticker, period)`

```
    e.get_income_statement("AAPL", "q")


    # Output
        2023-03-31   2023-06-30   2023-09-30    2023-12-31   2024-03-31
    reportedCurrency                           USD          USD          USD           USD          USD
    grossProfit                        41976000000  36413000000  40427000000   54855000000  42271000000
    totalRevenue                       94836000000  80799000000  88496000000  119575000000  90753000000
    costOfRevenue                      59061000000  51357000000  55222000000   71506000000  54950000000
    costofGoodsAndServicesSold         52860000000  45384000000  49071000000   64720000000  48482000000
    operatingIncome                    28318000000  22998000000  26969000000   40373000000  27900000000
    sellingGeneralAndAdministrative     6201000000   5973000000   6151000000    6786000000   6468000000
    researchAndDevelopment              7457000000   7442000000   7307000000    7696000000   7903000000
    operatingExpenses                  13658000000  13415000000  13458000000   14482000000  14371000000
    investmentIncomeNet                       None    980000000    984000000          None         None
    netInterestIncome                    -12000000   -998000000  -1002000000          None         None
    interestIncome                        12000000     18000000     18000000          None         None
    interestExpense                      930000000    998000000   1002000000    1002000000         None
    nonInterestIncome                  94836000000  81797000000  89498000000  119575000000  90753000000
    otherNonOperatingIncome               76000000   -247000000     47000000          None         None
    depreciation                              None         None         None          None         None
    depreciationAndAmortization         2898000000   3052000000   2653000000    2848000000   2836000000
    incomeBeforeTax                    28382000000  22733000000  26998000000   40323000000  28058000000
    incomeTaxExpense                    4222000000   2852000000   4042000000    6407000000   4422000000
    interestAndDebtExpense                    None    998000000   1002000000          None         None
    netIncomeFromContinuingOperations  24160000000  19881000000  22956000000   33916000000  23636000000
    comprehensiveIncomeNetOfTax        25326000000  19826000000  23305000000   35990000000  24054000000
    ebit                               29312000000  23731000000  28000000000   40373000000  27900000000
    ebitda                             31216000000  26050000000  29622000000   43221000000  30736000000
    netIncome                          24160000000  19881000000  22956000000   33916000000  23636000000
```

###### Balance Sheet

- Get the quarterly balance sheet for Apple Inc. (AAPL). Use "A" for annual data.
- Force update to local data with `e.update_balance_sheet(ticker, period)`

```
    e.get_balance_sheet("AAPL", "q")

    # Output

        2023-03-31    2023-06-30    2023-09-30    2023-12-31    2024-03-31
    index
    reportedCurrency                                 USD           USD           USD           USD           USD
    totalAssets                             332160000000  335038000000  352583000000  353514000000  337411000000
    totalCurrentAssets                      112913000000  122659000000  143566000000  143692000000  128416000000
    cashAndCashEquivalentsAtCarryingValue    24687000000   28408000000   29965000000   40760000000   32695000000
    cashAndShortTermInvestments              24687000000   62482000000   61555000000   73100000000   67150000000
    inventory                                 7482000000    7351000000    6331000000    6511000000    6232000000
    currentNetReceivables                            NaN   39186000000   60985000000   50102000000   41150000000
    totalNonCurrentAssets                   219247000000  212379000000  209017000000  209822000000  208995000000
    ......
    shortLongTermDebtTotal                  109615000000  109293000000  111088000000  107998000000  104597000000
    otherCurrentLiabilities                  56425000000   58897000000   58829000000   54611000000   57298000000
    otherNonCurrentLiabilities               52886000000   51730000000   49848000000   50353000000   47564000000
    totalShareholderEquity                   62158000000   60274000000   62146000000   74100000000   74194000000
    treasuryStock                                    NaN           NaN           NaN           NaN           NaN
    retainedEarnings                          4336000000    1408000000    -214000000    8242000000    4339000000
    commonStock                              69568000000   70667000000   73812000000   75236000000   78815000000
    commonStockSharesOutstanding             15723406000   15647868000   15550061000   15460223000   15337686000
```

###### Cash Flow

- Get the quarterly cash flow statement for Apple Inc. (AAPL). Use "A" for annual data.
- Force update to local data with `e.update_cash_flow(ticker, period)`

```
    e.get_cash_flow("AAPL", "q")

    # Output

            2023-03-31.1     2023-06-30     2023-09-30     2023-12-31     2024-03-31
    index
    reportedCurrency                                              USD            USD            USD            USD            USD
    operatingCashflow                                     28560000000    26380000000    21598000000    39895000000    22690000000
    paymentsForOperatingActivities                                NaN            NaN     3113000000            NaN            NaN
    proceedsFromOperatingActivities                               NaN            NaN            NaN            NaN            NaN
    changeInOperatingLiabilities                         -16821000000     5203000000    14946000000    -8407000000   -11740000000
    changeInOperatingAssets                              -17052000000     4454000000    21006000000    -9530000000    -5976000000
    depreciationDepletionAndAmortization                   2898000000     3052000000     2653000000     2848000000     2836000000
    ......
    dividendPayoutCommonStock                              3650000000     3849000000     3758000000     3825000000     3710000000
    dividendPayoutPreferredStock                                  NaN            NaN            NaN            NaN            NaN
    proceedsFromIssuanceOfCommonStock                             NaN              0              0            NaN            NaN
    proceedsFromIssuanceOfLongTermDebtAndCapitalSec...            NaN              0              0              0              0
    proceedsFromIssuanceOfPreferredStock                          NaN            NaN            NaN            NaN            NaN
    proceedsFromRepurchaseOfEquity                       -19594000000              0   -21003000000   -20139000000   -23205000000
    proceedsFromSaleOfTreasuryStock                               NaN            NaN            NaN            NaN            NaN
    changeInCashAndCashEquivalents                         5155000000     2769000000      839000000            NaN            NaN
    changeInExchangeRate                                          NaN            NaN            NaN            NaN            NaN
    netIncome                                             24160000000    19881000000    22956000000    33916000000    23636000000
    freeCashflow                                        25644000000.0  24287000000.0  19435000000.0  37503000000.0  20694000000.0
```
