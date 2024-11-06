# **VWAP Calculation for Bitcoin Trades across Multiple Exchanges**

## **Requirements**

This code requires the following Python libraries to be installed:

- `os`
- `datetime` (from `datetime`)
- `numpy` (imported as `np`)
- `pandas` (imported as `pd`)
- `IPython.display` (imported as `display` and `clear_output`)
- `plotly.graph_objects` (imported as `go`)

## **Installation Instructions**

You can install the required libraries using pip. 

```bash
pip install -r requirements.txt
```

---

## **Project Overview**

This project calculates the **Volume Weighted Average Price (VWAP)** for Bitcoin trades across different cryptocurrency exchanges, using hourly intervals. VWAP is an essential metric for traders and analysts, as it provides the average price of an asset, weighted by its trading volume, during a given time period.

The project involves several key steps:
1. **Data Import** – Read trade data from CSV files for various exchanges.
2. **Data Transformation** – Manipulate the data to prepare it for VWAP calculation, including merging data from different files.
3. **VWAP Calculation** – Compute the VWAP for each exchange and for the global market.
4. **Result Export** – Output the results as a CSV file for further analysis or reporting.

The project is developed using Python, and the results are presented in a Jupyter Notebook.

---

## **Features**

- **VWAP Calculation**: Compute VWAP for each exchange and globally across all exchanges, based on hourly intervals.
- **Handling Missing Values**: Address missing or incomplete data during processing.
- **Additional Metrics**: Optionally, calculate other related metrics, such as:
  - Volume Weighted Median Price
  - Standard Deviation of the VWAP
  - OHLC (Open, High, Low, Close)
- **Flexible Calculation Intervals**: VWAP can also be calculated for other time intervals like 5 and 30 minutes.

---

## **Steps in the Project**

### 1. **Input Data**

The input consists of CSV files containing Bitcoin trade data from multiple exchanges. Each file contains the following columns:

- **Timestamp**: Date and time of the trade.
- **Price**: Price of Bitcoin at the time of the trade.
- **Volume**: Volume of Bitcoin traded.

### 2. **Data Manipulation**

The data is imported and processed to:
- Merge data from different exchange CSV files.
- Convert timestamps to a uniform datetime format.
- Group data by hour and exchange.

Key steps involved:
- Import necessary libraries (`pandas`, `numpy`).
- Read CSV files using `pandas`.
- Convert timestamps to datetime format for easier manipulation.
- Aggregate the data by hour for each exchange.

### 3. **VWAP Calculation**

The core calculation applies the VWAP formula:

$$
\text{VWAP} = \frac{\sum_{j} P_j Q_j}{\sum_{j} Q_j}
$$

Where:
- \( Pj \) is the price of trade \( j \).
- \( Qj \) is the volume of trade \( j \).
- The summation runs over all trades \( j \) within each hourly interval for each exchange.

VWAP is calculated for each exchange and globally across all exchanges.


### 4. **Export Results**

Results are exported as a CSV file, where:
- Each row represents a one-hour interval.
- Each column represents the VWAP for a specific exchange and the global VWAP.

The CSV file is indexed by the timestamp (hour) and includes the following columns:
- **Timestamp** (Index)
- **VWAP_Exchange_1**
- **VWAP_Exchange_2**
- ...
- **VWAP_Global**

---

## **Additional Metrics**

In addition to VWAP, the following metrics can be calculated:
- **Volume Weighted Median Price**: A robust measure of the average price that incorporates volume weighting.
- **Standard Deviation**: Measure the volatility of the VWAP.
- **OHLC**: Calculate the Open, High, Low, and Close for each hourly period.

---

## **Project Structure**

The project is organized into three main sections in the Jupyter Notebook:

1. **Input**: 
   - Read and load the data from CSV files.
   - Preview the data and perform initial cleaning.

2. **Data Manipulation**: 
   - Merge files and group data by hour.
   - Handle missing data and ensure the integrity of the dataset.

3. **VWAP Calculation**: 
   - Apply the VWAP formula.
   - Calculate VWAP for each exchange and globally.
   - Optionally, compute additional metrics (e.g., Volume Weighted Median Price, Standard Deviation, OHLC).

---

## **Conclusion**

This project demonstrates how to process, analyze, and calculate the VWAP for Bitcoin trades across different exchanges. The resulting VWAP metric is a valuable tool for analyzing price movements and making trading decisions.

---

## **License**

This project is open-source and can be freely used and modified under the [MIT License](LICENSE).

