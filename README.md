# FLARECAST: Forecasting Solar Flare Intensity with Transformers

**Goal:**  
Develop a transformer-based deep learning model to predict solar flare intensity using time series data of solar activity. The model will leverage attention mechanisms to capture long-range dependencies in solar magnetic field measurements and X-ray flux data. Performance will be compared against traditional methods such as LSTM networks and statistical forecasting techniques.

---

## **Core Datasets**

### 1. **NOAA/NASA GOES X-ray Flux**

- **Description:**  
  Time series measurements of soft X-ray flux (0.5–4 Å and 1–8 Å) from the GOES satellites, which directly correspond to solar flare intensities (A, B, C, M, X classes).

- **Role:**  
  - **Target variable:** flare intensity  
  - **Input time series:** recent X-ray flux history  
  - **Event labeling:** flare start/end times

- **Access:**  
  [NOAA GOES Data Access](https://www.ngdc.noaa.gov/stp/satellite/goes/dataaccess.html)

---

### 2. **SDO/HMI SHARP (Space-weather HMI Active Region Patches)**

- **Description:**  
  Vector magnetic field maps and derived parameters (e.g., total unsigned flux, magnetic shear, helicity) for active regions on the Sun, updated regularly.

- **Role:**  
  - **Input features:** magnetic complexity indicators  
  - **Capturing precursors:** physical conditions leading up to flares

- **Access:**  
  [JSOC SHARP Data](http://jsoc.stanford.edu/data/hmi/SHARP/)

---

## **Project Outline**

### 1. **Data Acquisition**

- Download GOES X-ray flux data covering at least one full solar cycle (~11 years).
- Download SHARP magnetic parameters for the same period.
- Align datasets temporally (e.g., 5-minute or hourly cadence).
- Label flare events using GOES event lists.

---

### 2. **Data Preprocessing**

- Clean and normalize time series data.
- Handle missing values and outliers.
- Engineer features from SHARP parameters.
- Create input sequences and corresponding targets for forecasting.

---

### 3. **Exploratory Data Analysis (EDA)**

- Visualize flare intensity distributions.
- Analyze temporal patterns and correlations.
- Investigate relationships between magnetic features and flare activity.

---

### 4. **Baseline Models**

- Implement traditional forecasting methods:
  - **ARIMA**
  - **LSTM**
  - **CNN-LSTM hybrid**

- Evaluate baseline performance using RMSE, MAE, and skill scores.

---

### 5. **Transformer Model Development**

- Design a transformer architecture for multivariate time series forecasting.
- Experiment with:
  - Input embeddings (X-ray + magnetic features)
  - Positional encoding
  - Model depth and attention heads
  - Sequence length (context window)

- Train and tune the model.

---

### 6. **Model Evaluation**

- Compare transformer performance against baselines.
- Use cross-validation and test on held-out flare events.
- Metrics:
  - RMSE, MAE
  - Precision/Recall for flare event classification (if applicable)
  - Lead time accuracy

---

### 7. **Interpretability**

- Visualize attention weights to identify influential time steps and features.
- Analyze model insights in the context of solar physics.

---

### 8. **Documentation and Reporting**

- Summarize methodology, results, and conclusions.
- Prepare visualizations and figures.
- Write final report and presentation.

---

## **References**

- [Predicting Solar Flares Using CNN and LSTM on Two Solar Cycles of Active Region Data](https://arxiv.org/abs/2010.03883)
- [Solar flare prediction model with the hybrid deep learning method](https://www.nature.com/articles/s41598-021-92927-0)

---

## **Contact**

**Author:** Carmine Shorette  
**Course:** Physics 361 — Machine Learning in Physics