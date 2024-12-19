# **Options Analysis with Greeks**

This script provides a comprehensive framework for analyzing options contracts, filtering based on Strike/Greek type, and calculating various financial metrics including the Greeks (Delta, Gamma, Vega, Theta, Rho). Additionally, it generates interactive plots to visualize the changes in Greeks over time for different strike prices.

---

## **Key Features**
- **User Inputs**:
  - Ticker Symbol
  - Option Type (*Call* or *Put*)
  - Bounds for Strike Prices (as a percentage of the current stock price)

- **Filters Applied**:
  - Options within a specific strike price range.
  - Expiry dates up to 16 weeks from the current date.
  - Excludes options with 0 days to expiry.

- **Calculated Metrics**:
  - **Intrinsic Value**: Value if the option is in-the-money (ITM).
  - **Premium Per Day (Extrinsic)**: Theta decay over the option's lifetime.
  - **Return on Capital as %**: Profitability for option sellers.
  - **Moneyness**: Classification as *In-the-Money* (ITM) or *Out-of-the-Money* (OTM).

- **Greeks Calculations**:
  - Delta, Gamma, Vega, Theta, and Rho were calculated analytically using `py_vollib`.

- **Simulated Greeks**:
  - Interactive visualizations showing how Greeks evolve with time to expiry.
  - Highlighted days representing actual option data.

---

## **Setup Instructions**
1. **Install Required Libraries**:

- %%capture !pip install py_vollib

2. **Import Necessary Packages**:
The script uses libraries like:
- `py_vollib`
- `pandas`, `numpy`
- `yfinance`
- `plotly.graph_objects`
- `matplotlib.pyplot`

3. **Set a Risk-Free Rate**:
- Default: **0.04**
- Can be adjusted directly in the `r` variable.

---

## **How to Use**
1. **Provide Inputs**:
- **Ticker Symbol**: Input a valid stock ticker symbol.
- **Option Type**: Choose `c` for Call or `p` for Put.
- **Bounds**: Define upper and lower strike price bounds as a percentage (e.g., `0.20` for ±20%).

2. **Run the Script**:
- The script automatically fetches option chains using `yfinance` and applies filters.

3. **Analyze Outputs**:
- **Filtered Options Table**: Includes metrics like last price, volume, open interest, implied volatility, Greeks, and more.
- **Interactive Plot**: Simulated Greeks plotted against days to expiry, with dropdowns to filter by strike price or specific Greeks.

---

## **Core Functions**
- **`filter_opts_within_range()`**:
Filter options based on user-defined strike price range and expiry date limits.

- **`calculate_intrinsic_value()`**:
Computes the intrinsic value of each option contract.

- **`greeks()`**:
Calculates Delta, Gamma, Vega, Theta, and Rho for each option using `py_vollib`.

- **`simulate_greeks_with_highlighted_days()`**:
Simulates Greek values for fixed and actual expiry days, visualizing changes interactively.

---

## **Visualizations**
- Interactive plots using `plotly.graph_objects`:
- Greeks vs. Days to Expiry (with inverted x-axis for clarity).
- Dropdown menus to filter by strike price or individual Greeks.

---

## **Customizations**
- **Adjust Risk-Free Rate**:
Modify the `r` variable to reflect current market rates.

- **Modify Filters**:
- Change the expiry limit (`max_expiry_date`).
- Adjust bounds for strike prices (`lower_bound`, `upper_bound`).

---

## **Dependencies**
- **Python Libraries**:
- `py_vollib`
- `yfinance`
- `pandas`
- `numpy`
- `plotly`
- `matplotlib`
- `scipy`

---

## **Example Output**
- Filtered options table with calculated metrics.
- Interactive plot showing Greek values and their day-over-day percentage changes.

**Note**: This script is tailored for Google Colab and includes `%capture` to suppress installation outputs.
