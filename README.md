# 🏙️ Mietpreis-Vorhersage für Berlin: Ein End-to-End Machine Learning Projekt

![Python](https://img.shields.io/badge/Python-3.9%2B-blue?style=for-the-badge&logo=python)
![Scikit-Learn](https://img.shields.io/badge/scikit--learn-%23F7931E?style=for-the-badge&logo=scikit-learn)
![Pandas](https://img.shields.io/badge/pandas-%23150458.svg?style=for-the-badge&logo=pandas)
![LightGBM](https://img.shields.io/badge/LightGBM-2B2E34?style=for-the-badge&logo=lightgbm)

Ein Data-Science-Projekt zur Vorhersage von Wohnungskaltmieten in Berlin. Der gesamte Workflow von der Datenbereinigung über das Modelltraining bis zur Interpretation wird mit modernen, robusten Methoden abgedeckt.

## 🎯 Projektübersicht

Dieses Projekt entwickelt ein Machine-Learning-Modell, das die Kaltmiete (`baseRent`) einer Wohnung in Berlin basierend auf ihren Eigenschaften (Wohnfläche, Alter, Zustand, Lage etc.) vorhersagt. Ein besonderer Fokus liegt auf einem methodisch sauberen Vorgehen durch den Einsatz von `scikit-learn`-Pipelines, um Data Leakage zu verhindern, sowie auf der Interpretation des finalen Modells mit SHAP, um die wichtigsten Preistreiber zu identifizieren.

---

## 🎓 Abgabeinformationen

**Projekt für:** Unternehmenssoftware
**Abgabedatum:** 25.07.2025, 23:59:59
**Gruppennummer:** 1
**Gruppenmitglieder:**
*   Adnan Salem
*   Leif Stöhr
*   Luka Kovacev
*   Ha Kevin Tran

### 📂 Inhalt des Repositories

*   **`main_analysis.ipynb`**: Das zentrale Jupyter Notebook, das den gesamten Analyseprozess von der Datenladung bis zur finalen Modellinterpretation enthält.
*   **`data/immo_data.csv`**: Der Rohdatensatz, der für die Analyse verwendet wird.
*   **`requirements.txt`**: Eine Liste aller Python-Bibliotheken, die zur Ausführung des Notebooks benötigt werden.
*   **`README.md`**: Diese Datei.
*   **`presentation.pdf`**: Die finale Präsentation (wird am Tag der Präsentation hochgeladen).

### 🔗 Datenquelle

*   **URL:** [Kaggle - Apartment Rental Offers in Germany](https://www.kaggle.com/datasets/corrieaar/apartment-rental-offers-in-germany/data)

---

## 🛠️ Technischer Workflow & Finale Ergebnisse

Unser Ansatz folgt einem strukturierten End-to-End-Prozess, um robuste und interpretierbare Ergebnisse zu gewährleisten.

1.  **Datenaufbereitung & Feature Engineering:**
    *   Der Rohdatensatz wurde auf ca. 10.000 Berliner Wohnungsangebote gefiltert und von Ausreißern bereinigt.
    *   Aus den Rohdaten wurden aussagekräftige Features wie das **Gebäudealter (`age`)**, ein **Neubau-Indikator (`isNew`)** und der **Berliner Bezirk (`bezirk`)** abgeleitet, um dem Modell entscheidenden Kontext zu geben.
    *   Die Zielvariable (`baseRent`) wurde **log-transformiert**, um die rechtsschiefe Verteilung zu normalisieren und die Modellleistung zu verbessern.

2.  **Systematischer Modellvergleich:**
    *   Acht verschiedene Modelle (von linear bis zu komplexen Ensembles) wurden mittels 5-facher Kreuzvalidierung systematisch verglichen.
    *   **Klares Ergebnis:** Gradient-Boosting-Modelle (`LightGBM`, `XGBoost`) zeigten mit einem **R² > 0.76** die mit Abstand höchste Leistungsfähigkeit.

3.  **Hyperparameter-Optimierung & Finale Evaluierung:**
    *   Das beste Modell (`LightGBM`) wurde mit `RandomizedSearchCV` gezielt optimiert.
    *   Auf einem ungesehenen Test-Set erreichte unser optimiertes Modell ein **Bestimmtheitsmaß (R²) von 0.79**.
    *   Das bedeutet, **79% der Varianz in den Mietpreisen** können durch unser Modell erklärt werden.
    *   Der durchschnittliche absolute Fehler (**MAE**) liegt bei **162,15 €**, was die praktische Anwendbarkeit des Modells unterstreicht.

### ✅ Wichtigste Preistreiber (laut SHAP-Analyse):

Die Interpretation des finalen Modells mit SHAP zeigt klar, welche Faktoren den größten Einfluss auf den Mietpreis haben und bestätigt die logischen Zusammenhänge:

1.  **Wohnfläche (`livingSpace`):** Der mit Abstand wichtigste Faktor. Größere Wohnungen sind erwartungsgemäß teurer.
2.  **Lage (`bezirk`):** Der Bezirk, in dem sich die Wohnung befindet, ist der zweitwichtigste Treiber. Dies bestätigt die enorme Bedeutung der Makrolage.
3.  **Gebäudealter (`age`):** Das Alter hat einen signifikanten, nicht-linearen Einfluss. Sehr alte (Altbau) und sehr neue Wohnungen sind tendenziell teurer.
4.  **Ausstattung (`hasKitchen`, `lift`):** Das Vorhandensein einer Einbauküche und eines Aufzugs sind ebenfalls wichtige, preistreibende Merkmale.

---

## 🚀 Erste Schritte

Befolgen Sie diese Schritte, um das Projekt lokal auszuführen:

1.  **Repository klonen:**
    ```bash
    git clone https://github.com/adnansalem1/berlin_rent_prediction.git
    cd berlin_rent_prediction
    ```

2.  **Virtuelle Umgebung erstellen (Empfohlen):**
    ```bash
    python3 -m venv venv
    ```

3.  **Umgebung aktivieren:**
    *   **macOS/Linux:** `source venv/bin/activate`
    *   **Windows:** `.\venv\Scripts\activate`

4.  **Abhängigkeiten installieren:**
    ```bash
    pip install -r requirements.txt
    ```

5.  **Jupyter Notebook starten:**
    ```bash
    jupyter lab
    ```
    Navigieren Sie zu `main_analysis.ipynb` und führen Sie die Zellen aus.

---

<details>
<summary>🇬🇧 Click here for the English version of this README</summary>

---

# 🏙️ Berlin Rent Prediction: An End-to-End Machine Learning Project

![Python](https://img.shields.io/badge/Python-3.9%2B-blue?style=for-the-badge&logo=python)
![Scikit-Learn](https://img.shields.io/badge/scikit--learn-%23F7931E?style=for-the-badge&logo=scikit-learn)
![Pandas](https://img.shields.io/badge/pandas-%23150458.svg?style=for-the-badge&logo=pandas)
![LightGBM](https://img.shields.io/badge/LightGBM-2B2E34?style=for-the-badge&logo=lightgbm)

A data science project for predicting apartment rental prices in Berlin. The entire workflow, from data cleaning and model training to interpretation, is covered using modern and robust methods.

## 🎯 Project Overview

This project develops a machine learning model that predicts the base rent (`baseRent`) of an apartment in Berlin based on its characteristics (living space, age, condition, location, etc.). A special focus is placed on a methodologically sound approach using `scikit-learn` pipelines to prevent data leakage, as well as on interpreting the final model with SHAP to identify the most important price drivers.

---

## 🎓 Submission Information

**Project for:** Unternehmenssoftware (Enterprise Software)
**Submission Date:** July 25, 2025, 23:59:59
**Group Number:** 1
**Group Members:**
*   Adnan Salem
*   Leif Stöhr
*   Luka Kovacev
*   Ha Kevin Tran

### 📂 Repository Contents

*   **`main_analysis.ipynb`**: The central Jupyter Notebook containing the entire analysis process, from data loading to final model interpretation.
*   **`data/immo_data.csv`**: The raw dataset used for the analysis.
*   **`requirements.txt`**: A list of all Python libraries required to run the notebook.
*   **`README.md`**: This file.
*   **`presentation.pdf`**: The final presentation (to be uploaded on the day of the presentation).

### 🔗 Data Source

*   **URL:** [Kaggle - Apartment Rental Offers in Germany](https://www.kaggle.com/datasets/corrieaar/apartment-rental-offers-in-germany/data)

---

## 🛠️ Technical Workflow & Final Results

Our approach follows a structured end-to-end process to ensure robust and interpretable results.

1.  **Data Preparation & Feature Engineering:**
    *   The raw dataset was filtered to approx. 10,000 apartment listings in Berlin and cleaned of outliers.
    *   Meaningful features such as **building age (`age`)**, a **new construction indicator (`isNew`)**, and the **Berlin district (`bezirk`)** were derived from the raw data to provide the model with crucial context.
    *   The target variable (`baseRent`) was **log-transformed** to normalize its right-skewed distribution and improve model performance.

2.  **Systematic Model Comparison:**
    *   Eight different models (from linear to complex ensembles) were systematically compared using 5-fold cross-validation.
    *   **Clear Result:** Gradient Boosting models (`LightGBM`, `XGBoost`) showed by far the highest performance with an **R² > 0.76**.

3.  **Hyperparameter-Tuning & Final Evaluation:**
    *   The best model (`LightGBM`) was specifically optimized using `RandomizedSearchCV`.
    *   On an unseen test set, our optimized model achieved a **Coefficient of Determination (R²) of 0.79**.
    *   This means **79% of the variance in rental prices** can be explained by our model.
    *   The **Mean Absolute Error (MAE)** is **€162.15**, highlighting the model's practical applicability.

### ✅ Key Price Drivers (according to SHAP analysis):

The interpretation of the final model with SHAP clearly shows which factors have the greatest impact on the rental price and confirms logical relationships:

1.  **Living Space (`livingSpace`):** By far the most important factor. Larger apartments are, as expected, more expensive.
2.  **Location (`bezirk`):** The district where the apartment is located is the second most important driver, confirming the enormous significance of the macro-location.
3.  **Building Age (`age`):** Age has a significant, non-linear impact. Very old (pre-war) and very new buildings tend to be more expensive.
4.  **Amenities (`hasKitchen`, `lift`):** The presence of a fitted kitchen and an elevator are also important, price-driving features.

---

## 🚀 Getting Started

Follow these steps to run the project locally:

1.  **Clone the repository:**
    ```bash
    git clone https://github.com/adnansalem1/berlin_rent_prediction.git
    cd berlin_rent_prediction
    ```

2.  **Create a virtual environment (Recommended):**
    ```bash
    python3 -m venv venv
    ```

3.  **Activate the environment:**
    *   **macOS/Linux:** `source venv/bin/activate`
    *   **Windows:** `.\venv\Scripts\activate`

4.  **Install dependencies:**
    ```bash
    pip install -r requirements.txt
    ```

5.  **Start Jupyter Notebook:**
    ```bash
    jupyter lab
    ```
    Navigate to `main_analysis.ipynb` and run the cells.

</details>