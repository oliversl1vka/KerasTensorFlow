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
| 1     | **80.0 %**        | 0.4497    | 19 | 21 | 147            |
| 2     | 75.5 %        | 0.4715    | 21 | 22 | 238          |
| 3     | 77.5 %    | 0.4663    | 13 | 23 | 171        |

---

## 📌 Závery

- Najlepší model (Model 1) využíva štandardný **ADAM** optimalizátor s **defaultným learning_rate=0.001**.
- Model 1 má najnižšiu náchylnosť na overfitting.
- Modely 2 a 3 dosahujú tiež slušné výsledky, ale model 2 má výrazne vyššiu cenu modelu.

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
2. Spusť súbor semestralna_praca.ipynb v Jupyter Notebooku.

---

## 📚 Referencie

Chollet, F. (2021). Deep Learning with Python. Manning Publications.
Yelp Open Dataset: https://www.yelp.com/dataset
TensorFlow Documentation: https://www.tensorflow.org
