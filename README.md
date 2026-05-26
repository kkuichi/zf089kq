# Analýza a predikcia podvodov v online finančných transakciách

Tento repozitár obsahuje zdrojové súbory k bakalárskej práci s názvom **Analýza a predikcia podvodov v online finančných transakciách**. Práca sa zameriava na analýzu, predspracovanie a modelovanie podvodných finančných transakcií pomocou metód strojového učenia.

Cieľom praktickej časti bolo porovnať viaceré klasifikačné modely v prostredí výrazne nevyvážených dát a vyhodnotiť ich nielen pomocou klasifikačných metrík, ale aj pomocou ekonomicky orientovanej metriky očakávanej finančnej straty.

## Obsah repozitára

Repozitár obsahuje:

- Jupyter Notebook s experimentmi bez časovo agregovaných príznakov,
- Jupyter Notebook s experimentmi rozšírenými o časovo agregované príznaky,
- README súbor slúžiaci ako stručná systémová príručka.

Štruktúra repozitára:

    .
    ├── creditcard_final_without_time.ipynb
    ├── creditcard_final_with_time.ipynb
    └── README.md

## Dataset

V práci bol použitý verejne dostupný dataset **Credit Card Fraud Detection** z platformy Kaggle.

Dataset nie je súčasťou repozitára z dôvodu veľkostného obmedzenia repozitára. Pred spustením notebookov je potrebné stiahnuť súbor `creditcard.csv` z pôvodného zdroja a uložiť ho do rovnakého priečinka ako notebooky.

Pôvodný zdroj datasetu:

https://www.kaggle.com/datasets/mlg-ulb/creditcardfraud

Dataset obsahuje:

- 284 807 transakcií,
- 31 stĺpcov,
- cieľovú premennú `Class`,
- hodnotu `0` pre legitímne transakcie,
- hodnotu `1` pre podvodné transakcie.

Dataset je výrazne nevyvážený, keďže podvodné transakcie predstavujú iba 492 prípadov.

## Použité knižnice

Experimenty boli realizované v jazyku Python v prostredí Jupyter Notebook. Použité boli najmä tieto knižnice:

- pandas,
- numpy,
- matplotlib,
- seaborn,
- scikit-learn,
- imbalanced-learn,
- xgboost,
- tensorflow,
- keras.

## Popis notebookov

### `creditcard_final_without_time.ipynb`

Notebook obsahuje experimenty realizované na pôvodných atribútoch datasetu bez doplnenia časovo agregovaných príznakov. Slúži ako porovnávacia verzia na overenie vplyvu časových príznakov.

Obsahuje najmä:

- načítanie datasetu,
- kontrolu chýbajúcich hodnôt a duplicitných záznamov,
- základnú exploračnú analýzu dát,
- predspracovanie dát,
- škálovanie vstupných premenných,
- riešenie nevyváženosti tried pomocou váhovania tried a SMOTE,
- trénovanie modelov logistickej regresie, XGBoost a deep learning,
- vyhodnotenie modelov pomocou metrík návratnosť, presnosť pozitívnych predikcií, F1-skóre a EFL.

### `creditcard_final_with_time.ipynb`

Notebook obsahuje rozšírenú verziu experimentov, v ktorej boli do datasetu doplnené časovo agregované príznaky odvodené z atribútu `Time`.

Doplnené boli najmä tieto príznaky:

- `Hour`,
- `Transactions_per_hour`,
- `Avg_amount_per_hour`.

Notebook slúži ako hlavná experimentálna verzia použitá v praktickej časti práce.

Obsahuje najmä:

- načítanie a kontrolu dát,
- tvorbu časových príznakov,
- predspracovanie a škálovanie dát,
- aplikáciu SMOTE na trénovaciu množinu,
- trénovanie modelov logistickej regresie, XGBoost a deep learning,
- optimalizáciu modelu XGBoost,
- úpravu rozhodovacieho prahu,
- vykreslenie ROC a Precision–Recall kriviek,
- porovnanie výsledkov modelov,
- výpočet očakávanej finančnej straty.

## Spustenie notebookov

Pre spustenie experimentov je potrebné mať nainštalované prostredie Python a Jupyter Notebook.

Postup spustenia:

1. Stiahnuť dataset `creditcard.csv` z platformy Kaggle.
2. Uložiť súbor `creditcard.csv` do rovnakého priečinka ako notebooky.
3. Otvoriť notebooky v prostredí Jupyter Notebook alebo JupyterLab.
4. Spustiť jednotlivé bunky notebookov postupne od začiatku.

## Výstupy experimentov

Modely boli hodnotené pomocou týchto metrík:

- návratnosť,
- presnosť pozitívnych predikcií,
- F1-skóre,
- očakávaná finančná strata,
- ROC krivka,
- Precision–Recall krivka.

V práci boli porovnané najmä tieto modely:

- logistická regresia,
- XGBoost,
- XGBoost s metódou SMOTE,
- optimalizovaný XGBoost,
- deep learning model.

Najlepší celkový výsledok z hľadiska očakávanej finančnej straty dosiahol optimalizovaný model XGBoost.

## Autor

Zuzana Fabianová  
Bakalárska práca  
Technická univerzita v Košiciach  
Fakulta elektrotechniky a informatiky  
Študijný program: Hospodárska informatika