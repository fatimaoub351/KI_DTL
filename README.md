# KI_DTL

# 1.BONUS

-------------------------------------------  Ist ein System wie ChatGPT “intelligent”--------------------------------------------

Nein, ChatGPT ist nicht im menschlichen Sinne intelligent.

-> Klassifizierung: Es ist ein Beispiel für Schwache KI, die auf eine spezifische Aufgabe (Textgenerierung) spezialisiert ist.

-> Fehlendes Bewusstsein: Das System besitzt kein Bewusstsein, kein echtes Verständnis oder eigene Überzeugungen.

-> Simulation: ChatGPT simuliert lediglich menschliche Intelligenz, indem es unglaublich kohärente und menschenähnliche Texte erzeugt.

---------------------------------------- Was ist der Kern des Systems --------------------------------------------------------------


-> Architektur: Es basiert auf der sogenannten Transformer-Architektur (daher das "T" in GPT: Generative Pre-trained Transformer).

-> Funktionsweise: Es wurde auf riesigen Textdatenmengen trainiert, um das statistisch wahrscheinlichste nächste Wort in einer gegebenen Sequenz vorherzusagen. Es verarbeitet Wörter als statistische Muster und Zusammenhänge, nicht als bedeutungstragende Konzepte.

-------------------------------------- Gibt es Systeme, die intelligent sind ------------------------------------------------------------
 
 Nein, derzeit gibt es keine Systeme, die im Sinne einer Starken KI (AGI) intelligent sind. Alle existierenden, kommerziell oder in der Forschung genutzten KI-Systeme sind Formen der Schwachen KI.

Was sie tun und wie sie arbeiten (Schwache KI):

1. Sie lösen spezifische Probleme (z. B. Bildklassifizierung, Empfehlungssysteme, medizinische Diagnosen).

2. Sie arbeiten hauptsächlich mit Methoden des Maschinellen Lernens, insbesondere Deep Learning und Neuronale Netze. Sie werden mit großen Datensätzen trainiert, um Muster zu erkennen und Vorhersagen zu treffen.

Beispiele:

-> Virtuelle Assistenten (Siri, Alexa): Verarbeiten Sprache und führen spezifische Befehle aus.

-> Autonome Fahrzeuge: Nutzen Bilderkennung, Sensorfusion und Entscheidungsalgorithmen.

-----------------------------------Brauchen wir wirklich Intelligenz in Systemen? Reicht auch schwache KI, d.h. reichen intelligent wirkende Systeme?-----------------

Für die Lösung der meisten gegenwärtigen Herausforderungen benötigen wir keine allgemeine menschliche Intelligenz in Maschinen, sondern spezialisierte, intelligent wirkende Systeme (Schwache KI), die die Aufgaben effizient und zuverlässig erfüllen, für die sie entwickelt wurden.

-----------------------------------Absicht vs. Auswirkung----------------------------------------------------------------

KI kann Menschen unterstützen und Risiken reduzieren 

Unfälle und Risiken:

Fehlentscheidungen durch Bias (z. B. diskriminierende Datensätze).

Fehlende Fairness oder Robustheit, z. B. durch falsche Korrelationen.

Missbrauch:

Spam, Phishing, Desinformation, Deepfakes.

Doppelte Verwendung (Dual Use):

Technologien, die für Forschung gedacht sind, können auch für Waffen, Überwachung oder Manipulation verwendet werden.

Bias:

Künstliche Intelligenz übernimmt oft die Vorurteile aus ihren Trainingsdaten, das kann Ungerechtigkeit und Diskriminierung verstärken.

# Entscheidungsbäume mit CAL3 und ID3

𝐻(𝑆)= − 4/7 * log_2 (4/7) - 3/7 * log_2 (3/7) ≈ 0,985228

Jetzt die Attribute jeweils berechnen:

------------------------------------------Attribut: Alter (Zweiteilung ≥35 / <35)-------------------------------------------------------------------

Gruppe1: 𝑆 ≥ 35 : 4 Personen ( O=2 , M=2) -> H = 1

Gruppe 2: 𝑆 <35  : 3 Personen ()(O=2,M=1) 

H = -2/3 * log_2(2/3) - 1/3 * log_2(1/3)

H≈0,918

Gewichtete Restentropie: 4/7*1 + 3/7 * 0,918 = 0.9798

Gewichtete Entropie:

IG(Alter) = 0,985 - 0.9798

IG(Alter)≈0,02024


---------------------------------------------Attribut: Einkommen (hoch / niedrig)--------------------------------------------------------

hoch (4 Personen): O=3,M=1 → H≈0,811278

niedrig (3 Personen): O=1,M=2 → H≈0,918296

Gewichtete Restentropie: 

4/7 ​* 0.811 + 3/7 * 0.918=0.857

Gewichtete Entropie: 

IG(Einkommen)= 0,985-0,857 ≈0,128085

-------------------------------------------Attribut: Bildung (Abitur / Master / Bachelor)--------------------------------------------

Abitur (3 Personen ): O=1,M=2 → H≈0,918296

Master (2 Personen): O=2,M=0 → H=0 

Bachelor (2): O=1,M=1 → H=1

Gewichtete Restentropie:

3/7 * 0.918 + 2/7 * 0 + 2/7 ​* 1 ≈ 0,67927

Gewichtete Entropie: 

IG(Bildung)≈0,30596

 höchster Informationsgewinn hat Bildung 0,306. ID3 wählt also Bildung als Wurzelattribut.

------------------------------------------------------ID3------------------------------------------------------------------------------------------

Fall 1: Bildung = Master

Daten: Nr. 2 und Nr. 5

→ Beide Kandidaten = O

→ Entropie = 0 (rein)

Blatt „O“

Fall 2: Bildung = Bachelor

Daten: Nr. 3 (M), Nr. 6 (O)
→ Entropie = 1 

 sucht ID3  das Attribut mit höchstem IG :

Mögliche Attribute: „Alter“, „Einkommen“

Einkommen: Hoch IG = 0

Alter unterscheidet sich:

≥35 → M

<35 → O

Erzeuge zwei Blätter:

Alter ≥ 35 → M

Alter < 35 → O

Fall 3: Bildung = Abitur

Daten: Nr. 1 (O), Nr. 4 (M), Nr. 7 (M)

→ Entropie ≈ 0.918 (gemischt)

 mögliche Attribute prüfen:

Split nach Einkommen:

hoch → Nr. 1 → O (rein)

niedrig → Nr. 4, Nr. 7 → beide M (rein)

Perfekte Trennung → Restentropie = 0

Split nach Alter:

liefert keine so gute Trennung

Erzeuge zwei Blätter:
 
Einkommen = hoch     → O

Einkommen = niedrig  → M

ENDERgebniss CAL3

Wurzel: Bildung 

Master -> O

Bachlor -> O

Abitur -> M

# DTL.02: Pruning
---------------------------------------------------Restaurant-Datensatz------------------------------------------------------------------------------

Baumstruktur

GÃ¤ste = Some: Yes (4.0)
GÃ¤ste = Full: No (6.0/2.0)
GÃ¤ste = None: No (2.0)

Fehlerrate auf Trainingssatz:

12 Instanzen insgesamt

10 korrekt klassifiziert → 2 Fehler → Fehlerrate = 16,7 %

=== Confusion Matrix ===

 a b   <-- classified as
 4 2 | a = Yes
 0 6 | b = No

Alle No-Instanzen korrekt vorhergesagt.

2 Yes-Instanzen wurden fälschlich als No klassifiziert.

Baum ist sehr einfach, trennt die Klassen hauptsächlich nach der Anzahl der Gäste.

-------------------------------------------------------------------Zoo---------------------------------------------------


feathers <= 0
|   milk <= 0
|   |   backbone <= 0
|   |   |   airborne <= 0
|   |   |   |   predator <= 0
|   |   |   |   |   legs <= 2: shellfish (2.0)
|   |   |   |   |   legs > 2: insect (2.0)
|   |   |   |   predator > 0: shellfish (8.0)
|   |   |   airborne > 0: insect (6.0)
|   |   backbone > 0
|   |   |   fins <= 0
|   |   |   |   tail <= 0: amphibian (3.0)
|   |   |   |   tail > 0: reptile (6.0/1.0)
|   |   |   fins > 0: fish (13.0)
|   milk > 0: mammal (41.0)
feathers > 0: bird (20.0)


Der Baum verwendet milk, feathers, backbone, airborne, predator, fins, tail, legs.

Jede Klasse (mammal, fish, bird, shellfish, insect, amphibian, reptile) wird an einem Blatt klassifiziert.

ehlerrate (10-fold cross-validation):

101 Instanzen, 93 korrekt → Fehlerrate ≈ 7,92 %


=== Confusion Matrix ===

  a  b  c  d  e  f  g   <-- classified as
  
 41  0  0  0  0  0  0 |  a = mammal
 
  0 13  0  0  0  0  0 |  b = fish
  
  0  0 20  0  0  0  0 |  c = bird
  
  0  0  0  8  2  0  0 |  d = shellfish
  
  0  0  0  3  5  0  0 |  e = insect
  
  0  0  0  0  0  3  1 |  f = amphibian
  
  0  1  0  0  1  0  3 |  g = reptile

Meiste Klassen sehr gut vorhergesagt (mammal, fish, bird perfekt).

Kleinere Fehler bei shellfish, insect, amphibian und reptile.

Der Baum nutzt mehrere Attribute, um Tiere korrekt zu klassifizieren.

-----------------------------------------------

2. Attributtypen

nominal

Diskrete Kategorien

Werte müssen vorher bekannt sein

Beispiel: {yes,no}, {low,medium,high}

ID3 funktioniert nur mit nominalen Attributen!

numeric (auch „ordinal“ genannt, manchmal nur „integer“ oder „real“)

Zahlenwerte, die geordnet sind oder Rechenoperationen zulassen

Beispiel: Alter, Anzahl Beine, Preis in Euro

ID3 kann numeric-Werte nicht direkt verwenden, J48 kann sie aber handhaben

string

Beliebige Zeichenketten, z. B. Tiername oder Restaurantname

ID3 kann string nicht verarbeiten

Muss ggf. in nominale Werte umgewandelt werden


@relation zoo

@attribute hair {0,1}

@attribute feathers {0,1}

@attribute eggs {0,1}

@attribute milk {0,1}

@attribute airborne {0,1}

@attribute aquatic {0,1}

@attribute predator {0,1}

@attribute domestic {0,1}

@attribute catsize {0,1}

@attribute type {1,2,3,4,5,6,7}

@data

1,0,0,1,0,0,1,0,1,1

1,0,0,1,0,0,1,0,0,1

0,1,1,0,1,0,0,0,0,3

0,0,1,0,0,1,0,0,0,4

0,1,0,0,1,0,0,1,0,3

1,0,0,1,0,0,1,1,1,1

0,0,1,0,0,0,0,0,0,4

0,0,0,1,0,1,0,1,1,2

1,0,0,1,0,0,0,0,1,1
...

------------

@relation restaurant

@attribute alternate {yes,no}

@attribute bar {yes,no}

@attribute fri_sat {0,1}        % 0=Nein, 1=Ja

@attribute hungry {yes,no}

@attribute patrons {none,some,full}

@attribute price {low,medium,high}

@attribute raining {yes,no}

@attribute reservation {yes,no}

@attribute type {french,italian,thai,burger}

@attribute wait_time {short,medium,long,very_long}

@attribute wait {yes,no}

@data

yes,no,1,yes,some,high,no,yes,french,short,yes

yes,no,0,yes,full,low,no,no,thai,medium,no

no,yes,0,no,some,low,no,no,burger,short,yes

yes,no,1,yes,full,low,no,no,thai,medium,yes

yes,no,0,yes,full,high,no,yes,french,very_long,no

no,yes,0,yes,some,medium,yes,yes,italian,short,yes

no,yes,0,no,none,low,yes,no,burger,short,no

no,no,1,yes,some,medium,yes,yes,thai,short,yes

no,yes,0,no,full,low,yes,no,burger,very_long,no

yes,yes,1,yes,full,high,no,yes,italian,medium,no

no,no,0,no,none,low,no,no,thai,short,no

yes,yes,1,yes,full,low,no,no,burger,medium,yes

ID3 benötigt nominale Attribute → ARFF notwendig

J48 kann CSV und ARFF verarbeiten

ID3 benötigt nominale Attribute → ARFF notwendig

J48 kann CSV und ARFF verarbeiten

Für einfache Datensätze (Restaurant) liefern beide Algorithmen identische Ergebnisse

Für komplexe Datensätze (Zoo) ist J48 durch Pruning kompakter, ID3 etwas größer, aber beide klassifizieren zuverlässig

Confusion Matrices zeigen, dass Fehler hauptsächlich bei kleinen Klassen auftreten



