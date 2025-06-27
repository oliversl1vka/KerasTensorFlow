# Klasifikácia sentimentu pomocou Keras a TensorFlow

**Autori:** Oliver Slivka, Viliam Ráčay  
**Škola:** Vysoká škola ekonomická v Prahe (VŠE)  
**Predmet:** Umelá inteligencia a jej aplikácie  
**Akad. rok:** 2024/2025  

---

## 🧠 O projekte

Táto semestrálna práca sa zaoberá binárnou klasifikáciou sentimentu textových recenzií (pozitívny/negatívny) pomocou neurónových sietí implementovaných v knižniciach **Keras** a **TensorFlow**. Cieľom bolo navrhnúť, implementovať a porovnať tri rôzne modely s rôznymi architektúrami, aktivačnými funkciami a optimalizačnými stratégiami.

---

## 📊 Dataset

Použitý dataset: [`yelp_labelled.csv`](./yelp_labelled.csv)  
- 1000 textových recenzií z platformy Yelp  
- Každá recenzia je ohodnotená binárne (1 = pozitívna, 0 = negatívna)  
- Rozdelenie datasetu: 60 % tréning, 20 % validácia, 20 % test

**Príklad vstupu:**  
`"Wow... Loved this place." → 1`  
`"Crust is not good." → 0`

---

## ⚙️ Použité techniky

- Predspracovanie textu: TF-IDF (max 2000 tokenov)
- Modely implementované v TensorFlow/Keras
- Evaluácia: accuracy, loss, confusion matrix, vlastná „nákladová metrika“

---

## 🧪 Experimenty

Trénovali sme 3 modely:

1. **Model 1** – 1 skrytá vrstva (64 ReLU) + Adam  
2. **Model 2** – 3 skryté vrstvy (32 tanh) + RMSprop  
3. **Model 3** – 2 skryté vrstvy (128 a 64 ReLU) + SGD s exponenciálnym decay  

### 📈 Výsledky

| Model | Test Accuracy | Test Loss | FN | FP | „Cena modelu“ |
|-------|---------------|-----------|----|----|----------------|
| 1     | 80.0 %        | 0.4478    | 20 | 21 | 247            |
| 2     | 81.0 %        | 0.8900    | 20 | 17 | 218            |
| 3     | **82.5 %**    | 1.0315    | 22 | 17 | **215**        |

---

## 📌 Závery

- Najlepší model (Model 3) využíva **SGD** optimalizátor s **exponenciálnym znižovaním learning rate**.
- Model 1 má najnižšiu náchylnosť na overfitting.
- Model 2 dosahuje slušné výsledky, ale trpí preučením.

---

## 🤖 Využitie generatívnej AI

Počas spracovania práce boli využité nástroje **ChatGPT** (GPT-4o-mini) a **DeepSeek-V2** pre konzultácie, štylistiku, tvorbu kódu a návrh experimentov. Prompty a využitie sú podrobne popísané v dokumentácii.

---

## 📂 Súbory v repozitári

- `semestralna_praca.ipynb` – hlavný Jupyter notebook s implementáciou modelov a analýzou  
- `yelp_labelled.csv` – dataset  
- `README.md` – tento súbor  

---

## 🛠️ Ako spustiť

1. Naklonuj repozitár:
   ```bash
   git clone https://github.com/oliversl1vka/KerasTensorFlow.git
   cd KerasTensorFlow
Spusť súbor semestralna_praca.ipynb v Jupyter Notebooku.

---

## 📚 Referencie

Chollet, F. (2021). Deep Learning with Python. Manning Publications.
Yelp Open Dataset: https://www.yelp.com/dataset
TensorFlow Documentation: https://www.tensorflow.org