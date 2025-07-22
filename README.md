
# 🏙️ Mietpreis-Vorhersage für Berlin

![Python](https://img.shields.io/badge/Python-3.9%2B-blue?style=for-the-badge&logo=python )
![Scikit-Learn](https://img.shields.io/badge/scikit--learn-%23F7931E?style=for-the-badge&logo=scikit-learn )
![Pandas](https://img.shields.io/badge/pandas-%23150458.svg?style=for-the-badge&logo=pandas )
![XGBoost](https://img.shields.io/badge/xgboost-%23313884.svg?style=for-the-badge&logo=xgboost )

Dieses Projekt entwickelt ein robustes Machine-Learning-Modell zur Vorhersage von Wohnungskaltmieten in Berlin und deckt dabei den gesamten Data-Science-Workflow ab.

## 🎯 Projektübersicht

Das Kernziel ist die Entwicklung eines präzisen Regressionsmodells zur Schätzung der Kaltmiete (`baseRent`) basierend auf Wohnungseigenschaften. Ein besonderer Fokus liegt auf einem methodisch sauberen Vorgehen:

-   **Robuste Vorverarbeitung:** Einsatz von `scikit-learn`-Pipelines, um Data Leakage zu verhindern.
-   **Fortgeschrittene Modellierung:** Training und Optimierung eines `XGBoost`-Modells mittels `RandomizedSearchCV`.
-   **Tiefe Modell-Interpretation:** Analyse der wichtigsten Preistreiber mit der SHAP-Bibliothek.

## 🚀 Erste Schritte

Folgen Sie diesen Schritten, um das Projekt lokal auszuführen:

<details>
<summary><strong>Klicken Sie hier für die detaillierte Installationsanleitung</strong></summary>

1.  **Repository klonen:**
	```bash
    git clone https://github.com/adnansalem1/berlin_rent_prediction.git
    cd berlin_rent_prediction
    ```

2.  **Datensatz herunterladen:**
	Der Datensatz stammt von Kaggle: [Apartment Rental Offers in Germany](https://www.kaggle.com/datasets/corrieaar/apartment-rental-offers-in-germany/data ).
	Laden Sie `immo_data.csv` herunter und legen Sie die Datei im Ordner `data/` ab.

3.  **Virtuelle Umgebung erstellen (Empfohlen):**
	```bash
    python3 -m venv venv
    ```

4.  **Umgebung aktivieren:**
	-   **macOS/Linux:** `source venv/bin/activate`
	-   **Windows:** `.\venv\Scripts\activate`

5.  **Abhängigkeiten installieren:**
	```bash
    pip install -r requirements.txt
    ```

6.  **Jupyter Notebook starten:**
	```bash
    jupyter lab
    ```
	Navigieren Sie zu `berlin_rent_prediction.ipynb` und führen Sie die Zellen aus.
</details>

## 🛠️ Technischer Workflow

Das Projekt folgt einem strukturierten, sechsstufigen Prozess:

1.  **Datenladung & Exploration (EDA):** Verstehen der Datenverteilungen und fehlender Werte.
2.  **Feature Engineering:** Erstellung neuer Merkmale wie `age` und Anwendung der Log-Transformation.
3.  **Pipeline-basierte Vorverarbeitung:** Kapselung von Imputation, Skalierung und Encoding.
4.  **Modelltraining & Hyperparameter-Tuning:** Optimierung eines `XGBoost`-Modells mit `RandomizedSearchCV`.
5.  **Robuste Evaluierung:** Bewertung der Leistung auf einem Test-Set mittels MAE, RMSE und R².
6.  **Modell-Interpretation:** Erklärung der Vorhersagen und Feature-Einflüsse mit SHAP.

## ✅ Ergebnisse & Erreichte Ziele

Das Projekt hat alle gesetzten Ziele erfolgreich umgesetzt und ein leistungsstarkes Vorhersagemodell hervorgebracht.

-   **Finale Modellleistung (auf Testdaten):**
	-   **MAE (Durchschnittlicher Fehler):** ca. 184.30 €
	-   **R² (Bestimmtheitsmaß):** > 0.83 
    -   **RMSE (Quadratischer Mittelwertfehler):** ca. 273.36 €
    -   **Modell:** `XGBoostRegressor` mit optimierten Hyperparametern. 
    -   **Feature-Importances:** Visualisierung der wichtigsten Merkmale, die die Miete beeinflussen.
    -   **SHAP-Analyse:** Detaillierte Erklärung der Modellvorhersagen und Identifikation der wichtigsten Einflussfaktoren.
    -   **Pipeline-basierte Vorverarbeitung:** Sicherstellung der Robustheit und Wiederholbarkeit des Modells.
    -   **Kreuzvalidierung:** Verwendung von `cv=5` für eine zuverlässige Modellbewertung.
    -   **Hyperparameter-Optimierung:** Effiziente Suche nach den besten Modellparametern mit `RandomizedSearchCV`.
    -   **Modell-Interpretation:** Einsatz der SHAP-Bibliothek zur Erklärung der Modellergebnisse.
    -   **Feature Engineering:** Erstellung von `age` (Alter der Wohnung) und Anwendung der Log-Transformation zur Normalisierung der Daten.
    -   **Explorative Datenanalyse (EDA):** Visualisierung von Verteilungen, Korrelationen und fehlenden Werten zur fundierten Analyse.
    -   **Datenbereinigung & Vorverarbeitung:** Systematische Behandlung fehlender Werte und Datentyp-Konvertierung innerhalb einer `scikit-learn`-Pipeline.
    -   **Einsatz fortgeschrittener Modelle:** Training und Evaluierung von Ensemble-Methoden wie `Random Forest` und `XGBoost`.
    -   **Robuste Modellbewertung:** Einsatz von Kreuzvalidierung (`cv=5`) während des gesamten Optimierungsprozesses.
    -   **Hyperparameter-Optimierung:** Effiziente Suche nach den besten Modellparametern mit `RandomizedSearchCV`.

    
-   **Wichtigste Preistreiber (laut SHAP-Analyse):**
	1. **`livingSpace` (Wohnfläche):** Der mit Abstand wichtigste Faktor. Größere Wohnflächen führen zu deutlich höheren Preisen.
    2. **`hasKitchen` (Einbauküche vorhanden):** Wohnungen mit Einbauküche erzielen höhere Preise.
    3. **`age` (Alter):** Neuere Wohnungen sind tendenziell teurer, ältere Objekte drücken den Preis.
    4. **`lift` (Aufzug vorhanden):** Der Preis steigt, wenn ein Aufzug vorhanden ist.
    5. **`condition` & `interiorQual` (Zustand & Ausstattung):** Hochwertig sanierte oder gut erhaltene Wohnungen (z. B. „mint condition“, „sophisticated“) wirken sich positiv auf den Preis aus.

<details>
<summary><strong>Detaillierte Übersicht der erreichten Ziele</strong></summary>

| Zielsetzung                       | Status      | Implementierung                                                                                             |
| :-------------------------------- | :---------- | :---------------------------------------------------------------------------------------------------------- |
| **Datenbereinigung & Vorverarbeitung** | ✅ Erledigt | Systematische Behandlung fehlender Werte und Datentyp-Konvertierung innerhalb einer `scikit-learn`-Pipeline. |
| **Explorative Datenanalyse (EDA)**     | ✅ Erledigt | Visualisierung von Verteilungen, Korrelationen und fehlenden Werten zur fundierten Analyse.                 |
| **Feature Engineering**           | ✅ Erledigt | Erstellung von `age` und Anwendung der Log-Transformation zur Normalisierung der Daten.                       |
| **Einsatz fortgeschrittener Modelle** | ✅ Erledigt | Training und Evaluierung von Ensemble-Methoden wie `Random Forest` und `XGBoost`.                           |
| **Robuste Modellbewertung**       | ✅ Erledigt | Einsatz von Kreuzvalidierung (`cv=5`) während des gesamten Optimierungsprozesses.                             |
| **Hyperparameter-Optimierung**    | ✅ Erledigt | Effiziente Suche nach den besten Modellparametern mit `RandomizedSearchCV`.                                 |
| **Modell-Interpretation**         | ✅ Erledigt | Analyse der wichtigsten Preistreiber mit der SHAP-Bibliothek zur Erklärung der Modellergebnisse.            |

</details>
