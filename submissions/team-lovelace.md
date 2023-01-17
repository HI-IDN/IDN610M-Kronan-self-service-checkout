# Example: Classification for fruits and vegetables

* Almar
* Margrét
* Elínborg


Here are some photos from Krónan of a customer using the self-service check-out. Look at the images and what are they telling us? 
### Why is this an interesting classification problem?

Þetta er áhugavert flokkunarverkefni að því leytinu til að sjálfsafgreiðslukassinn kemur upp með tillögur að ávöxtum og grænmeti þegar viðskiptavinurinn vigtar vöruna. Þar af leiðandi þarf viðskiptavinurinn ekki að leita í kerfinu að þeim ávöxt eða grænmeti sem verið er að vigta heldur þarf hann aðeins að velja hann á skjánum úr hópi nokkurra matvæla.

### What is the instance space x∈X?
Hér erum við með lit, lögun og þyngd. Því væri ílagsrúmið þrívítt rúm með öllum ávöxtum og grænmeti (og önnur matvæli) ásamt samsetningum af lit, lögun og þyngd. Hægt er að skipta ílagsrúminu upp í vandamálarúm og eiginleikarúm. Vandamálarúmið inniheldur allar vörur sem tilheyra þessu kerfi (aðallega grænmeti og ávextir) og eru fáanlegt úr Krónunni. Eiginleikarúmið inniheldur upplýsingar varðandi vandamálarúmið, svo sem litur, lögun og þyngd.

### What are the concepts c(x) ?
Hugtökin eru vörur sem krónan er með í kerfinu og er að selja, sem eru ávextir og grænmeti í flestum tilfellum og koma upp á skjánum.

### What hypothesis h(x) can we use?
Tilgátan tekur inn þrjú gildi, lit, lögun og þyngd og myndi þá skila lista af vörum með líkindadreifingu á hve líklegt tilgátan telur að um sé að ræða þessa vöru. Þessi listi yrði síðan tekinn og birt væru á skjánum þær 12 vörur sem fá hæstar líkur, þó að það virðist vera ákveðin þröskuldur til að komast á skjáinn þar sem það eru ekki alltaf 12 vörur birtar.

### What is this target distribution D?
Markdreifing D er föst líkindadreifing yfir X. Hægt væri að búa til líkindadreifingu með því að nota sölugögn og því ákvarða hverjar líkurnar eru á því að keypt sé tiltekin gerð af matvæli. Jafnframt væri hægt að setja það fram á þann hátt að fyrir gefna vigt, lit og lögun hverjar eru líkurnar á því að tiltekinn fjöldi af ákveðnu matvæli hafi þessa vigt og komi fyrir á skjánum. 

### What is the oracle EX[c,D]?
Véfréttin EX[c,D] væri aðferð eða fall sem myndi skila pari, (x,y) þar sem c(x) = y. T.d. sem dæmi myndi véfréttin geta skilað (x,y), x:{þyngd:0,250kg, litur:”gulur”, lögun: Bananaleg lögun} og y: Banani. Véfréttin er því aðferðin sem tekur inn ílag úr eiginleikarúminu.

### How do we measure the error?
Við myndum þurfa sett af prófunartilvikum (af vörum) sem við gætum keyrt í gegnum vélina. Hægt væri að mæla skekkjuna með því að skoða hvort að þessi tiltekni ávöxtur eða grænmeti sem var vigtaður kemur fyrir á skjánum. Ekki þarf að gera greinamun á því hvar þetta birtist á skjánum heldur aðeins hvort þetta komi fyrir á skjánum eða ekki. 

### How can we take this project further? 

Hægt væri að bæta við annarri myndavél til þess að tryggja aukið nákvæmni við mat á lögun en þá þarf að taka tillit til þess að það taki lengri tíma vegna þess að bera þarf saman myndirnar. Þá þarf að taka mið af því að upplifun notenda mun hraka og er það því ekki endilega þess virði að hafa aðra myndavél. 

Það væri hægt að hafa verðflokka, þar sem viðskiptavinur gæti verið líklegri til að velja vörur sem eru innan ákveðins flokks, t.d. ef hann kaupir dýrari gerð af ákveðinni vöru þá er hann líklegri til að velja dýrari gerð af öðrum vörum. Einnig væri hægt að hafa fylgni milli vara inn í líkaninu sem er notað, þar sem ef að viðskiptavinur kaupir ákveðna vörur þá er líklegt að hann kaupi vörur sem að er algengt að séu keyptar með.
