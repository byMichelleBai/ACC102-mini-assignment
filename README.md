# Beauty-Related Companies Risk and Return Analysis


## 1. Problem & User
This project compares the historical risk and return performance of five beauty-related publicly traded companies: Estée Lauder Companies, Coty Inc., Inter Parfums, e.l.f. Beauty, and Ulta Beauty.

The problem is that beginner-level investors, business students, and market researchers may find it difficult to compare companies only by looking at stock prices. This project uses Python to provide a clearer comparison based on cumulative return, average monthly return, and volatility.


## 2. Data
The data were obtained from WRDS using the CRSP Monthly Stock File. The sample period is from January 2020 to December 2024.

The dataset includes five beauty-related publicly traded companies: Estée Lauder Companies (`EL`), Coty Inc. (`COTY`), Inter Parfums (`IPAR`), e.l.f. Beauty (`ELF`), and Ulta Beauty (`ULTA`).

The exported dataset is saved in `data/beauty_monthly_stock_data.csv`. The dataset contains 300 monthly observations. Each company has 60 monthly observations during the sample period.

The key fields used in the analysis are `date`, `ticker`, `comnam`, `prc`, and `ret`. In this project, `date` is the month-end date, `ticker` is the stock ticker symbol, `comnam` is the company name, `prc` is the month-end stock price, and `ret` is the monthly stock return.


## 3. Methods
The main analysis was completed in `beauty_risk_return_analysis.ipynb`.

First, the WRDS monthly stock dataset was loaded into Python using pandas. The dataset was checked for company coverage, data types, and missing values. In the data cleaning step, the `date` column was converted into datetime format, and the data were sorted by ticker and date so that the time-series analysis could be completed correctly.

After data preparation, the project calculated cumulative return, average monthly return, final cumulative return, and volatility for each company. Volatility was measured using the standard deviation of monthly returns.

The project then created several charts to compare company performance, including stock price trends, cumulative returns, volatility comparison, and a risk-return scatter plot.


## 4. Key Finding
- e.l.f. Beauty (`ELF`) had the strongest risk-return performance in this sample. It had the highest cumulative return and the highest average monthly return, while its volatility was high but not the highest.

- Coty Inc. (`COTY`) had the highest volatility among the five companies. However, its final cumulative return was negative, so the higher risk did not lead to a stronger return outcome during the sample period.

- Inter Parfums (`IPAR`) and Ulta Beauty (`ULTA`) showed more balanced results. Both companies had positive cumulative returns and relatively moderate volatility, but their return levels were much lower than e.l.f. Beauty.

- Estée Lauder Companies (`EL`) had the lowest volatility, but its return performance was negative. This shows that lower volatility alone does not always mean better performance.


## 5. How to run
Open `beauty_risk_return_analysis.ipynb` in Jupyter Notebook or JupyterLab.
Make sure the dataset is kept in the `data` folder with the following path:
```text
data/beauty_monthly_stock_data.csv
```
Then run the notebook from top to bottom. The notebook will load the dataset, clean and prepare the data, calculate return and volatility indicators, and generate the charts and summary table.

The output charts and summary file are saved in the `figures` folder.


## 6. Product link / Demo
The project files are organised in the GitHub repository. The repository includes the main notebook, the WRDS monthly stock dataset, saved figures, and the summary output.

GitHub repository: https://github.com/byMichelleBai/ACC102-mini-assignment
Demo video link: https://video.xjtlu.edu.cn/Mediasite/Play/b59de3dec9ce40d181348587e16d33881d

## 7. Limitations & next steps
This project has two limitations. The analysis only uses five selected beauty-related companies, so the result cannot represent the whole beauty or consumer sector. The project also mainly uses monthly stock price and return data, so it does not fully explain the business reasons behind the stock movements. Another limitation is that the analysis is based on historical data from January 2020 to December 2024. Therefore, the results describe past performance and should not be treated as a prediction of future stock performance.

For future improvement, the project could include more companies, financial statement data, or market benchmark data. It could also compare the companies with a wider consumer sector index to better understand whether their performance was company-specific or affected by the overall market.