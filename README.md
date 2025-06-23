# Berlin Rent Prediction Project

Dieses Repository enthält ein Jupyter Notebook zur Vorhersage von Mietpreisen in Berlin. Der Datensatz basiert auf Mietangeboten aus Deutschland, die auf Kaggle verfügbar sind und für Berlin gefiltert werden.

## Inhalt des Repositories

-   `data/`: Enthält den Rohdatensatz (`immo_data.csv`).
-   `notebooks/`: Enthält das Haupt-Jupyter-Notebook (`berlin_rent_prediction.ipynb`) mit der Datenanalyse, Vorverarbeitung und dem Modelltraining.
-   `src/` (optional): Enthält Python-Skripte für modularen Code (z.B. für Feature Engineering oder Modell-Dienstprogramme).
-   `.gitignore`: Definiert Dateien und Ordner, die von der Versionskontrolle ausgeschlossen werden sollen (z.B. virtuelle Umgebungen, temporäre Dateien).
-   `README.md`: Diese Datei.
-   `requirements.txt`: Liste der Python-Bibliotheken, die für dieses Projekt benötigt werden.
-   `environment.yml` (optional): Conda-Umgebungsdefinition.

## Datensatz

Der verwendete Datensatz "Apartment rental offers in Germany" stammt von Kaggle:
[https://www.kaggle.com/datasets/corrieaar/apartment-rental-offers-in-germany/data](https://www.kaggle.com/datasets/corrieaar/apartment-rental-offers-in-germany/data)

**Wichtiger Hinweis:** Laden Sie die Datei `immo_data.csv` herunter und legen Sie sie im Ordner `data/` ab, bevor Sie das Notebook ausführen.

## Einrichtung und Ausführung

Befolgen Sie diese Schritte, um das Projekt lokal einzurichten und das Notebook auszuführen:

1.  **Repository klonen (falls auf GitHub):**
	```bash
    git clone [https://github.com/IhrBenutzername/berlin_rent_prediction.git](https://github.com/IhrBenutzername/berlin_rent_prediction.git)
    cd berlin_rent_prediction
    ```
	(Wenn Sie dieses Projekt von Grund auf neu erstellen, überspringen Sie diesen Schritt und erstellen Sie den Ordner `berlin_rent_prediction` manuell.)

2.  **Datensatz herunterladen:**
	Stellen Sie sicher, dass `immo_data.csv` im Ordner `data/` liegt. Siehe den Abschnitt "Datensatz" oben für Download-Anweisungen.

3.  **Python-Umgebung erstellen:**
	Es wird dringend empfohlen, eine virtuelle Umgebung zu verwenden.
	```bash
    python -m venv venv
    ```

4.  **Virtuelle Umgebung aktivieren:**
	-   **Linux/macOS:**
		```bash
        source venv/bin/activate
        ```
	-   **Windows:**
		```bash
        .\venv\Scripts\activate
        ```

5.  **Notwendige Bibliotheken installieren:**
	```bash
    pip install -r requirements.txt
    ```

6.  **Jupyter Notebook starten:**
	```bash
    jupyter notebook
    ```
	Ihr Webbrowser sollte sich öffnen und das Jupyter-Dashboard anzeigen.

7.  **Notebook öffnen und ausführen:**
	Navigieren Sie im Jupyter-Dashboard zum Ordner `notebooks/` und öffnen Sie `berlin_rent_prediction.ipynb`. Führen Sie die Zellen der Reihe nach aus, um die Analyse und das Modell zu sehen.

## Projektziele

-   **Datenbereinigung und Vorverarbeitung:** Handhabung fehlender Werte, Datentypkonvertierung.
-   **Explorative Datenanalyse (EDA):** Visualisierung von Trends und Mustern in den Berliner Mietdaten.
-   **Feature Engineering:** Erstellung neuer Merkmale aus bestehenden Daten zur Verbesserung der Modellleistung.
-   **Modellauswahl und Training:** Anwendung verschiedener Regressionstechniken zur Vorhersage der Mietpreise.
-   **Modellbewertung:** Messung der Leistung des Modells anhand geeigneter Metriken.

## Nächste Schritte

-   Experimentieren mit weiteren Feature-Engineering-Techniken.
-   Implementierung fortgeschrittenerer Modelle (z.B. Random Forest, Gradient Boosting, Neuronale Netze).
-   Hyperparameter-Optimierung.
-   Einsatz von Kreuzvalidierung.
-   Erstellung einer einfachen Web-Anwendung zur Mietpreisvorhersage.


---