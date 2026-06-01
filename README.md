# 🍕 Zomato Data Analysis & Insights

[![Open In Colab] https://colab.research.google.com/drive/1BdmEv-OijFAyF3gH0OHOAOqV6NNCM1j9#scrollTo=E41FlKqIWmvt

An end-to-end Exploratory Data Analysis (EDA) project designed to translate raw Zomato restaurant data into strategic business insights.

---

## 🎯 Project Objective
The food-tech industry is highly competitive. This project leverages Python to analyze thousands of data points to help understand:
* **Customer Behavior:** How do ordering modes (online vs. offline) influence user satisfaction?
* **Market Trends:** Which restaurant types dominate the platform?
* **Economic Strategy:** What is the optimal pricing "sweet spot" for target demographics?

---

## 🛠️ Tech Stack
* **Language:** Python
* **Data Processing:** Pandas, NumPy
* **Visualization:** Seaborn, Matplotlib
* **Environment:** Google Colab

---

## 📈 Key Insights
| Insight | Business Value |
| :--- | :--- |
| **Dining Dominance** | Identified that the "Dining" category holds the largest market share. |
| **Online Satisfaction** | Statistical analysis proves online-order-enabled restaurants receive significantly higher ratings. |
| **Pricing Optimization** | Revealed a massive pricing concentration at 300 INR, suggesting a high-demand "budget-friendly" segment. |

---

## 💻 Code Highlight: Data Cleaning
To ensure accurate visualizations, raw text data (like `"4.1/5"`) had to be mathematically parsed into clean floats. Here is a snippet of the preprocessing logic used:

```python
# Function to clean the 'rate' column
def handleRate(value):
    if pd.isna(value):
        return np.nan
    
    # Split the string and isolate the numerator
    value = str(value).split("/")[0].strip()
    
    try:
        return float(value)
    except ValueError:
        return np.nan

# Apply the cleaning function to the dataset
dataframe["rate"] = dataframe["rate"].apply(handleRate)
