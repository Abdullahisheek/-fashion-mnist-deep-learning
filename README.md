# -fashion-mnist-deep-learning

# Fashion MNIST – Bildklassificering med Deep Learning

## Projektöversikt

Detta projekt handlar om bildklassificering med hjälp av deep learning och datasetet Fashion MNIST.  
Målet var att bygga och jämföra olika neurala nätverksmodeller som kan klassificera klädesplagg baserat på gråskalebilder.

Projektet utvecklades med TensorFlow och Keras.

---

# Dataset

Vi använde Fashion MNIST-datasetet från Keras:

- 70 000 gråskalebilder
- Bildstorlek: 28x28 pixlar
- 10 olika klädeskategorier

Exempel på kategorier:
- T-shirt/top
- Byxor
- Pullover
- Klänning
- Kappa
- Sandal
- Sneaker
- Väska
- Ankelboot

Datasetet laddades in med:

from tensorflow.keras.datasets import fashion_mnist

---

# Teknologier

- Python
- TensorFlow / Keras
- NumPy
- Matplotlib
- Jupyter Notebook

---

# Projektets innehåll

Projektet innehåller:

1. Inläsning och visualisering av datasetet
2. Preprocessing av data
3. Dense-modell
4. CNN-modell
5. Träning och utvärdering av modeller
6. Jämförelse mellan modeller
7. Analys och slutsats

---

# Fokusområde – Input och Preprocessing

Vårt fokusområde var Input och Preprocessing.

Vi undersökte hur preprocessing påverkar modellernas prestanda och resultat.

Följande preprocessing-tekniker användes:

- normalisering av pixelvärden
- reshaping av bilddata för CNN
- jämförelse mellan olika inputformat

## Normalisering

Pixelvärdena skalades från intervallet 0–255 till 0–1 med hjälp av:

x_train_norm = x_train.astype('float32') / 255.0
x_test_norm = x_test.astype('float32') / 255.0

Normalisering gjorde träningen stabilare och hjälpte modellerna att lära sig snabbare.

## Reshape för CNN

CNN-modeller kräver tredimensionell bilddata:

x_train_cnn = x_train_norm.reshape(-1, 28, 28, 1)
x_test_cnn = x_test_norm.reshape(-1, 28, 28, 1)

Detta gjorde det möjligt för CNN-modellen att analysera bildens spatiala struktur.

---

# Modeller

## Dense-modell

Dense-modellen använder flattenad bilddata och fully connected-lager.

Fördelar:
- enklare arkitektur
- snabbare träning

Nackdelar:
- förlorar spatial information
- mindre effektiv för bildklassificering

---

## CNN-modell

CNN-modellen använder convolution-lager för att analysera mönster i bilder.

Fördelar:
- bättre feature extraction
- högre accuracy
- bättre för bilddata

Nackdelar:
- mer komplex modell
- längre träningstid

---

# Resultat

CNN-modellen gav bättre resultat jämfört med Dense-modellen.

Vi observerade att:

- normalisering förbättrade träningsstabiliteten
- preprocessing förbättrade accuracy
- CNN fungerade bättre för bildklassificering
- reshape var nödvändigt för CNN-modeller

---

# Analys

Vi jämförde Dense-modellen och CNN-modellen för att undersöka hur preprocessing påverkar modellernas prestanda.

Först användes normalisering där pixelvärdena skalades från intervallet 0–255 till 0–1. Detta gjorde träningen stabilare och hjälpte modellerna att lära sig snabbare.

Vi reshapes också bilderna till formatet (28, 28, 1) för CNN-modellen. Detta var viktigt eftersom CNN-modeller behöver spatial bildinformation för att kunna identifiera mönster som kanter, former och detaljer.

Resultaten visade att CNN-modellen gav högre validation accuracy och lägre loss jämfört med Dense-modellen.

Dense-modellen fungerade bra som en grundmodell, men CNN-modellen kunde analysera bilddata mer effektivt eftersom convolution-lager är specifikt utvecklade för bildigenkänning.

Vi såg också att preprocessing hade stor påverkan på modellernas resultat. Utan korrekt preprocessing blev träningen mindre stabil och modellerna presterade sämre.

---

# Slutsats

I detta projekt lärde vi oss hur preprocessing och modellarkitektur påverkar deep learning-modeller för bildklassificering.

Vi såg att normalisering förbättrade både träningsstabilitet och accuracy genom att göra inputvärdena mindre och mer jämna.

Vi lärde oss också att CNN-modeller fungerar bättre än Dense-modeller för bilddata eftersom CNN kan bevara och analysera spatial information i bilderna.

Projektet hjälpte oss att förstå hur viktiga preprocessing-tekniker är inom deep learning och hur olika val påverkar modellernas prestanda.

Om projektet skulle vidareutvecklas skulle vi vilja testa fler preprocessing-metoder och mer avancerade CNN-arkitekturer för att ytterligare förbättra resultaten.

---

# Framtida förbättringar

Möjliga framtida förbättringar:

- testa data augmentation
- använda djupare CNN-arkitekturer
- hyperparameter tuning
- experimentera med dropout och regularisering

---

# Författare Grupp 6