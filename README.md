# TFG - Suport a la Classificació d’Imatges Dermatoscòpiques mitjançant la Metodologia XAI Basada en Exemples

Aquest repositori conté els experiments realitzats com a part del Treball de Final de Grau (TFG), on s'aplica una metodologia XAI basada en exemples per donar suport a models de classificació d’imatges dermatoscòpiques. Els models han estat entrenats utilitzant la base de dades [HAM10000](https://www.kaggle.com/kmader/skin-cancer-mnist-ham10000).

Els experiments estan organitzats en diferents fitxers, cadascun amb una funció específica dins del pipeline experimental:

---

## 📁 Estructura dels Fitxers

### `EvaluacioArquitectures.py`
- Entrenament dels models de classificació.
- Per cada entrenament es crea una carpeta corresponent a Google Drive on es desen:
  - Els paràmetres d’entrenament
  - Els pesos del model entrenat
  - Els resultats obtinguts sobre el conjunt de test

### `Analisis.py`
- Càlcul de les mètriques d’avaluació a partir dels resultats de test guardats per cada model.

### `FeatureExtraction.py`
- Generació dels vectors de característiques de les imatges utilitzant els pesos dels models entrenats.
- Els vectors es guarden en fitxers `.txt` dins la carpeta associada als pesos utilitzats.

### `FeatureDistancesNew.py`
- Càlcul de les distàncies entre les imatges del conjunt de test i les del conjunt d’entrenament.
- Per cada imatge de test, es determinen les 5 imatges d'entrenament més properes (segons distància L2 o cosinus).
- Els resultats es desen en un fitxer `.txt` dins una carpeta corresponent a la mesura de distància.

### `ImageComparation.py`
- Generació d’exemples visuals de la metodologia XAI.
- Per a cada imatge de test, es mostra juntament amb les seves 5 imatges d'entrenament més similars.
- Els diagrames visuals es desen a les carpetes `L2` o `cosinus`, segons la mètrica utilitzada.

### `AnalisiDocDistancies.py`
- Anàlisi comparativa quantitativa entre les dues mesures de distància utilitzades (L2 i cosinus). Per fer aquesta s'ha utilitzat la moda.

---

## 🧠 Objectiu

Explorar com una metodologia XAI basada en exemples pot ajudar a interpretar els resultats dels models de classificació en dermatologia, proporcionant explicacions visuals mitjançant imatges similars del conjunt d'entrenament.

---

## 📂 Requisits

- Python 3.7+
- Pytorch
- NumPy, Matplotlib, Scikit-learn, etc.
---

## 📌 Notes Addicionals

- Es recomana tenir accés a Google Drive per a l’emmagatzematge dels models i resultats.
- L’estructura de carpetes i noms ha de mantenir-se coherent per garantir la correcta execució dels scripts.
- Els scripts no són independents, cal executar-los en l'ordre en que s'han explicat.
  

