## Forecasting Water Consumption Integrating Weather Parameters in Davao City

**An Experimental Comparative Study using Hybrid Neural Networks**

This repository contains the code and experimental notebooks for the thesis **“Forecasting Water Consumption Integrating Weather Parameters in Davao City: An Experimental Comparative Study using Hybrid Neural Networks.”** All experiments were originally developed and executed in Google Colab using Jupyter (`.ipynb`) notebooks.

The primary goal of this work is to build and compare neural network architectures for forecasting **monthly water consumption** in Davao City by incorporating **meteorological variables** (e.g., relative humidity and mean temperature) as explanatory features.

---

### Repository Contents

- **Jupyter notebooks (`.ipynb`)**:  
  End-to-end workflows for:
  - Data preprocessing and feature engineering  
  - Model definition and training for:
    - Baseline LSTM models  
    - CNN–LSTM models  
    - Hybrid Attention-Based CNN–LSTM models  
  - Genetic Algorithm–based hyperparameter optimization  
  - Evaluation, visualization, and comparative analysis of results  

- **Model variants** (by notebook folders / names, as applicable):
  - `Base LSTM` – baseline sequence models for water consumption forecasting  
  - `CNN-LSTM` – convolutional + recurrent hybrid architectures  
  - `Attention-Based CNN-LSTM` – hybrid models with an attention mechanism to better capture temporal and feature-wise importance  

> Note: Folder names and notebook titles may vary slightly; please refer to the notebook names in this repository for the exact structure.

---

### Data Availability

- **Data source**:  
  Monthly water consumption records and corresponding meteorological variables were obtained from relevant **government agencies in Davao City and the National Government**.

- **Data access**:  
  The raw datasets **are not publicly available** in this repository due to data-sharing agreements and confidentiality constraints.

- **Working with your own data**:  
  To reproduce or adapt this work:
  - Prepare a monthly time-series dataset with:
    - Water consumption (e.g., volume per month)  
    - Meteorological variables such as relative humidity, mean temperature, and other relevant climate indicators  
  - Match the input format and column naming expected by the preprocessing cells in the notebooks (see the early cells in each notebook for loading and preprocessing steps).  

---

### Methodology

- **Problem type**: Multivariate time-series forecasting of monthly water consumption.  
- **Input features**: Historical water consumption and selected meteorological parameters (e.g., relative humidity, temperature).  
- **Architectures compared**:
  - Traditional **LSTM** models  
  - **CNN–LSTM** hybrids  
  - **Attention-Based CNN–LSTM** hybrids (proposed model)  
- **Optimization**:
  - A **Genetic Algorithm (GA)** is used for hyperparameter optimization (e.g., number of units, learning rate, batch size, etc.).  
  - Performance of GA-based optimization is assessed using multi-objective indicators such as **Inverted Generational Distance (IGD)** and **Hyper-Volume (HV)**.  
- **Evaluation metrics**:
  - **Mean Absolute Error (MAE)**  
  - **Mean Absolute Percentage Error (MAPE)**  
  - **Root Mean Square Error (RMSE)**  

---

### Key Findings

- The **hybrid Attention-Based CNN–LSTM model** achieved **forecasting accuracy** compared to traditional LSTM and CNN–LSTM architectures, consistently yielding **lower MAE, MAPE, and RMSE**.  
- Integrating **meteorological factors**—particularly **relative humidity** and **mean temperature**—enabled the model to capture the influence of environmental conditions on water consumption trends, resulting in improved predictive performance.  
- The **Genetic Algorithm–based hyperparameter optimization** significantly enhanced both accuracy and efficiency, as supported by favorable **IGD** and **HV** values in the optimization process.  
- Overall, the study demonstrates that advanced hybrid neural architectures, combined with intelligent hyperparameter search, provide a **reliable framework for multivariate time-series forecasting** in urban water management contexts.  
- The proposed method offers practical value for **resource planning, demand management, and sustainability efforts** in Davao City and similar urban environments.

---

### Running the Notebooks

Because all experiments were originally developed in **Google Colab**, the simplest way to use this repository is to run the notebooks directly in Colab.

- **Option 1 – Run in Google Colab**
  1. Upload this repository (or the notebook folders you need) to a Git hosting service (e.g., GitHub) if not already there.  
  2. Open the desired notebook in GitHub and click **“Open in Colab”** (if available), or open it directly via `https://colab.research.google.com` by pointing to the GitHub URL / local upload.  
  3. Configure the runtime (e.g., GPU if needed).  
  4. Update the data-loading paths in the first cells so that they point to your data in Google Drive or an uploaded dataset.  
  5. Run cells sequentially to reproduce preprocessing, training, optimization, and evaluation.  

- **Option 2 – Run Locally (Jupyter)**
  1. Create and activate a Python environment (e.g., using `conda` or `venv`).  
  2. Install required libraries, such as (typical stack, adjust as needed):  
     - `numpy`, `pandas`, `matplotlib`, `seaborn`  
     - `scikit-learn`  
     - `tensorflow` / `keras` (or `torch` if used)  
     - `deap` / `pymoo` or another GA library (depending on what is imported in the notebooks)  
  3. Launch Jupyter:  
     ```bash
     jupyter notebook
     ```  
  4. Open the desired `.ipynb` file and adjust file paths and environment-specific settings as necessary.  

> Tip: If you plan to reuse this code extensively, consider extracting the core model and GA logic from the notebooks into reusable Python modules.

---

### Reproducibility Notes

- Random seeds may be set in the notebooks for partially reproducible results, but exact replication can still vary due to:
  - Differences in library versions (e.g., TensorFlow, CUDA, NumPy)  
  - Hardware and runtime environments (local vs. Colab)  
  - Stochastic behavior of training and GA search  
- For more stable comparisons, fix random seeds where possible and record the library versions used for the original experiments.

---

### Usage

For questions about reuse, collaboration, or access to the original (non-public) data, please contact the thesis author(s) or relevant supervising institution.

