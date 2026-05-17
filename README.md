# FINC3011 Group 12 Supporting Workings

## Project Title

Currency Strategies Under Changing Market Conditions  
International Financial Management, FINC3011  
University of Sydney  
Semester 1, 2026

## Group Members

- Jonas Bateman
- Marwan Ferreira Da Silva
- Max Huttary
- Luca Vecchio

## Purpose of This Folder

This folder contains the supporting workings for the FINC3011 group assignment. The analysis investigates whether monthly movements in the AUD/USD exchange rate, defined as S(USD/AUD), are consistent with Uncovered Interest Parity (UIP) and Purchasing Power Parity (PPP), and whether deviations from UIP can support a monthly currency carry trade strategy.

The final written report is submitted separately as a PDF. The files in this folder document the data cleaning, calculations, regressions, figures, tables, and strategy results used in the report.

## Currency Pair and Sample Period

The selected currency pair is AUD/USD, defined as:

S(USD/AUD) = U.S. dollars per one Australian dollar

An increase in S(USD/AUD) represents an appreciation of the Australian dollar against the U.S. dollar.

The full sample period is January 2009 to December 2023.

| Period | Use |
|---|---|
| January 2009 to December 2019 | In-sample analysis and strategy design |
| January 2020 to December 2023 | Out-of-sample strategy evaluation |

## Main Analysis Files

The notebooks should be read and run in the following order:

### 1. `01_part1_uip_ppp_visuals.ipynb`

Constructs the Part I visual analysis.

Main outputs:

- UIP scatter plot with 45-degree line
- PPP scatter plot with 45-degree line
- UIP actual vs model-implied time-series plot
- PPP actual vs model-implied time-series plot
- UIP deviation plot
- PPP deviation plot
- Descriptive statistics table

### 2. `02_part2_uip_ppp_regressions.ipynb`

Estimates UIP and PPP regressions over the in-sample period.

Main outputs:

- Regression specification table
- Compact UIP and PPP regression results table
- Full UIP regression output
- Full PPP regression output
- Restriction tests for α = 0 and β = 1

### 3. `03_part3_carry_trade_audusd.ipynb`

Constructs and evaluates the monthly carry trade strategy.

The strategy:

- Goes long the higher-interest-rate currency
- Goes short the lower-interest-rate currency
- Rebalances monthly
- Uses lagged interest rate differentials to avoid look-ahead bias

Main outputs:

- Strategy design table
- Lagged interest rate differential figure
- In-sample cumulative return figure
- Out-of-sample cumulative return figure
- Rolling 12-month return figure
- Performance summary table
- Yearly return figures
- Key sub-period tables
- Out-of-sample notional P/L checkpoints
- Return decomposition table

## Data Sources

| Variable | Source |
|---|---|
| Spot exchange rate S(USD/AUD) | Yahoo Finance, AUDUSD=X |
| U.S. short-term interest rate | FRED, 1-month U.S. Treasury yield |
| Australian short-term interest rate | Reserve Bank of Australia, F1 Money Market Rates |
| U.S. CPI | University of Sydney course CPI dataset |
| Australian CPI | University of Sydney course CPI dataset |

## Key Variable Transformations

| Variable | Transformation |
|---|---|
| Realised exchange rate change | Monthly log change in S(USD/AUD) |
| UIP-implied change | U.S. short-term rate minus Australian short-term rate |
| PPP-implied change | U.S. inflation minus Australian inflation |
| Strategy signal | Lagged interest rate differential |
| Strategy return | Exchange rate movement plus carry component, adjusted for long/short position |
| Rebalancing | Monthly |

## Folder Structure

```text
data/
  raw/
  processed/

figures/
  part1/
  part3/

outputs/
  part1/
  part2/
  part3/

notebooks/
  01_part1_uip_ppp_visuals.ipynb
  02_part2_uip_ppp_regressions.ipynb
  03_part3_carry_trade_audusd.ipynb