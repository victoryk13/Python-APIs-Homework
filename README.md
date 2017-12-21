

```python
import pandas as pd
import numpy as np
import json
import requests as req
import matplotlib.pyplot as plt
import seaborn
import citipy
from citipy import citipy
```


```python
cities = []
latitudes = np.random.uniform(-90, 90, 1500)
longitudes = np.random.uniform(-180, 180, 1500)

for i in range(len(latitudes)-1):
    city = citipy.nearest_city(latitudes[i],longitudes[i]).city_name
    if city not in cities:
        cities.append(city)
```


```python
api_key = "eb1466db7ae3a93e6f626541f5ba5d90"
url = "http://api.openweathermap.org/data/2.5/weather?"
units = "Imperial"
query_url = url + "units=" + units + "&appid=" + api_key + "&q="

weather_data = []
count = 1

print("Beginning Data Retrieval")
print("-----------------------------")

for city in cities:
    print("Processing Record " + str(count) + " of Set 1 | " + city)
    count = count + 1
    print(query_url + city)
    response = req.get(query_url + city).json()
    if response["cod"] == 200:
        weather_data.append(response)
    else:
        print("City not found in OpenWeatherMap API.")

print("-----------------------------")
print("Data Retrieval Complete")
print("-----------------------------")
```

    Beginning Data Retrieval
    -----------------------------
    Processing Record 1 of Set 1 | busselton
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=busselton
    Processing Record 2 of Set 1 | rikitea
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=rikitea
    Processing Record 3 of Set 1 | port alfred
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=port alfred
    Processing Record 4 of Set 1 | cidreira
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=cidreira
    Processing Record 5 of Set 1 | zharkent
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=zharkent
    Processing Record 6 of Set 1 | talaya
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=talaya
    Processing Record 7 of Set 1 | kloulklubed
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=kloulklubed
    Processing Record 8 of Set 1 | vardo
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=vardo
    Processing Record 9 of Set 1 | bluff
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=bluff
    Processing Record 10 of Set 1 | mataura
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=mataura
    City not found in OpenWeatherMap API.
    Processing Record 11 of Set 1 | noyabrsk
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=noyabrsk
    Processing Record 12 of Set 1 | dire dawa
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=dire dawa
    Processing Record 13 of Set 1 | bathsheba
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=bathsheba
    Processing Record 14 of Set 1 | sentyabrskiy
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=sentyabrskiy
    City not found in OpenWeatherMap API.
    Processing Record 15 of Set 1 | wakefield
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=wakefield
    Processing Record 16 of Set 1 | pafos
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=pafos
    City not found in OpenWeatherMap API.
    Processing Record 17 of Set 1 | cervo
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=cervo
    Processing Record 18 of Set 1 | hobart
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=hobart
    Processing Record 19 of Set 1 | gizo
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=gizo
    Processing Record 20 of Set 1 | georgetown
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=georgetown
    Processing Record 21 of Set 1 | nakambala
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=nakambala
    Processing Record 22 of Set 1 | iqaluit
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=iqaluit
    Processing Record 23 of Set 1 | puerto ayora
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=puerto ayora
    Processing Record 24 of Set 1 | ushuaia
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=ushuaia
    Processing Record 25 of Set 1 | bardiyah
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=bardiyah
    Processing Record 26 of Set 1 | taolanaro
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=taolanaro
    City not found in OpenWeatherMap API.
    Processing Record 27 of Set 1 | yellowknife
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=yellowknife
    Processing Record 28 of Set 1 | hermanus
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=hermanus
    Processing Record 29 of Set 1 | juneau
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=juneau
    Processing Record 30 of Set 1 | jamestown
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=jamestown
    Processing Record 31 of Set 1 | zyryanka
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=zyryanka
    Processing Record 32 of Set 1 | progreso
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=progreso
    Processing Record 33 of Set 1 | pandan
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=pandan
    Processing Record 34 of Set 1 | castro
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=castro
    Processing Record 35 of Set 1 | albany
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=albany
    Processing Record 36 of Set 1 | arraial do cabo
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=arraial do cabo
    Processing Record 37 of Set 1 | kodiak
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=kodiak
    Processing Record 38 of Set 1 | avarua
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=avarua
    Processing Record 39 of Set 1 | butaritari
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=butaritari
    Processing Record 40 of Set 1 | kapaa
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=kapaa
    Processing Record 41 of Set 1 | tazovskiy
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=tazovskiy
    Processing Record 42 of Set 1 | leningradskiy
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=leningradskiy
    Processing Record 43 of Set 1 | illoqqortoormiut
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=illoqqortoormiut
    City not found in OpenWeatherMap API.
    Processing Record 44 of Set 1 | bredasdorp
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=bredasdorp
    Processing Record 45 of Set 1 | kimbe
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=kimbe
    Processing Record 46 of Set 1 | cherskiy
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=cherskiy
    Processing Record 47 of Set 1 | puerto escondido
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=puerto escondido
    Processing Record 48 of Set 1 | upernavik
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=upernavik
    Processing Record 49 of Set 1 | catuday
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=catuday
    Processing Record 50 of Set 1 | road town
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=road town
    Processing Record 51 of Set 1 | saint-andre-avellin
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=saint-andre-avellin
    Processing Record 52 of Set 1 | vaitupu
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=vaitupu
    City not found in OpenWeatherMap API.
    Processing Record 53 of Set 1 | plettenberg bay
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=plettenberg bay
    Processing Record 54 of Set 1 | metehara
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=metehara
    City not found in OpenWeatherMap API.
    Processing Record 55 of Set 1 | rabo de peixe
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=rabo de peixe
    Processing Record 56 of Set 1 | ngukurr
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=ngukurr
    City not found in OpenWeatherMap API.
    Processing Record 57 of Set 1 | saquarema
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=saquarema
    Processing Record 58 of Set 1 | vila franca do campo
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=vila franca do campo
    Processing Record 59 of Set 1 | rawson
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=rawson
    Processing Record 60 of Set 1 | san antonio
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=san antonio
    Processing Record 61 of Set 1 | punta arenas
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=punta arenas
    Processing Record 62 of Set 1 | qaanaaq
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=qaanaaq
    Processing Record 63 of Set 1 | avera
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=avera
    City not found in OpenWeatherMap API.
    Processing Record 64 of Set 1 | lebu
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=lebu
    Processing Record 65 of Set 1 | tevriz
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=tevriz
    Processing Record 66 of Set 1 | inderborskiy
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=inderborskiy
    City not found in OpenWeatherMap API.
    Processing Record 67 of Set 1 | bethel
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=bethel
    Processing Record 68 of Set 1 | pevek
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=pevek
    Processing Record 69 of Set 1 | mendahara
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=mendahara
    City not found in OpenWeatherMap API.
    Processing Record 70 of Set 1 | bara
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=bara
    Processing Record 71 of Set 1 | narsaq
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=narsaq
    Processing Record 72 of Set 1 | vaini
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=vaini
    Processing Record 73 of Set 1 | tual
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=tual
    Processing Record 74 of Set 1 | broome
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=broome
    Processing Record 75 of Set 1 | dabou
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=dabou
    Processing Record 76 of Set 1 | khatanga
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=khatanga
    Processing Record 77 of Set 1 | hilo
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=hilo
    Processing Record 78 of Set 1 | cape town
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=cape town
    Processing Record 79 of Set 1 | severo-kurilsk
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=severo-kurilsk
    Processing Record 80 of Set 1 | staraya poltavka
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=staraya poltavka
    Processing Record 81 of Set 1 | portales
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=portales
    Processing Record 82 of Set 1 | chokurdakh
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=chokurdakh
    Processing Record 83 of Set 1 | phuket
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=phuket
    Processing Record 84 of Set 1 | barentsburg
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=barentsburg
    City not found in OpenWeatherMap API.
    Processing Record 85 of Set 1 | port macquarie
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=port macquarie
    Processing Record 86 of Set 1 | uray
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=uray
    Processing Record 87 of Set 1 | atuona
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=atuona
    Processing Record 88 of Set 1 | hirado
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=hirado
    Processing Record 89 of Set 1 | zaragoza
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=zaragoza
    Processing Record 90 of Set 1 | bambous virieux
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=bambous virieux
    Processing Record 91 of Set 1 | yar-sale
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=yar-sale
    Processing Record 92 of Set 1 | agadir
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=agadir
    Processing Record 93 of Set 1 | bereda
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=bereda
    City not found in OpenWeatherMap API.
    Processing Record 94 of Set 1 | thompson
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=thompson
    Processing Record 95 of Set 1 | faanui
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=faanui
    Processing Record 96 of Set 1 | berlevag
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=berlevag
    Processing Record 97 of Set 1 | pimentel
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=pimentel
    Processing Record 98 of Set 1 | mar del plata
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=mar del plata
    Processing Record 99 of Set 1 | szeged
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=szeged
    Processing Record 100 of Set 1 | azrow
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=azrow
    City not found in OpenWeatherMap API.
    Processing Record 101 of Set 1 | ormara
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=ormara
    Processing Record 102 of Set 1 | saleaula
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=saleaula
    City not found in OpenWeatherMap API.
    Processing Record 103 of Set 1 | flin flon
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=flin flon
    Processing Record 104 of Set 1 | saskylakh
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=saskylakh
    Processing Record 105 of Set 1 | riyadh
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=riyadh
    Processing Record 106 of Set 1 | saldanha
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=saldanha
    Processing Record 107 of Set 1 | harer
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=harer
    Processing Record 108 of Set 1 | chara
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=chara
    Processing Record 109 of Set 1 | lasa
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=lasa
    Processing Record 110 of Set 1 | nizhneyansk
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=nizhneyansk
    City not found in OpenWeatherMap API.
    Processing Record 111 of Set 1 | kapoeta
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=kapoeta
    Processing Record 112 of Set 1 | port elizabeth
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=port elizabeth
    Processing Record 113 of Set 1 | labuan
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=labuan
    Processing Record 114 of Set 1 | manyana
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=manyana
    Processing Record 115 of Set 1 | grand-lahou
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=grand-lahou
    Processing Record 116 of Set 1 | okha
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=okha
    Processing Record 117 of Set 1 | kot addu
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=kot addu
    Processing Record 118 of Set 1 | geraldton
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=geraldton
    Processing Record 119 of Set 1 | barberton
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=barberton
    Processing Record 120 of Set 1 | fort nelson
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=fort nelson
    Processing Record 121 of Set 1 | caravelas
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=caravelas
    Processing Record 122 of Set 1 | fort walton beach
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=fort walton beach
    Processing Record 123 of Set 1 | airai
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=airai
    City not found in OpenWeatherMap API.
    Processing Record 124 of Set 1 | henties bay
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=henties bay
    City not found in OpenWeatherMap API.
    Processing Record 125 of Set 1 | coahuayana
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=coahuayana
    Processing Record 126 of Set 1 | dordrecht
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=dordrecht
    Processing Record 127 of Set 1 | cruzeiro do sul
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=cruzeiro do sul
    Processing Record 128 of Set 1 | langenburg
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=langenburg
    Processing Record 129 of Set 1 | ancud
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=ancud
    Processing Record 130 of Set 1 | mount gambier
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=mount gambier
    Processing Record 131 of Set 1 | tumannyy
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=tumannyy
    City not found in OpenWeatherMap API.
    Processing Record 132 of Set 1 | general cepeda
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=general cepeda
    Processing Record 133 of Set 1 | san patricio
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=san patricio
    Processing Record 134 of Set 1 | melfort
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=melfort
    Processing Record 135 of Set 1 | kaitangata
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=kaitangata
    City not found in OpenWeatherMap API.
    Processing Record 136 of Set 1 | mahroni
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=mahroni
    Processing Record 137 of Set 1 | yanan
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=yanan
    City not found in OpenWeatherMap API.
    Processing Record 138 of Set 1 | constitucion
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=constitucion
    Processing Record 139 of Set 1 | oussouye
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=oussouye
    Processing Record 140 of Set 1 | eirunepe
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=eirunepe
    Processing Record 141 of Set 1 | tsihombe
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=tsihombe
    City not found in OpenWeatherMap API.
    Processing Record 142 of Set 1 | komsomolskiy
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=komsomolskiy
    Processing Record 143 of Set 1 | mengcheng
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=mengcheng
    City not found in OpenWeatherMap API.
    Processing Record 144 of Set 1 | dikson
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=dikson
    Processing Record 145 of Set 1 | hopelchen
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=hopelchen
    Processing Record 146 of Set 1 | mys shmidta
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=mys shmidta
    City not found in OpenWeatherMap API.
    Processing Record 147 of Set 1 | maarianhamina
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=maarianhamina
    City not found in OpenWeatherMap API.
    Processing Record 148 of Set 1 | santiago del estero
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=santiago del estero
    Processing Record 149 of Set 1 | aasiaat
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=aasiaat
    Processing Record 150 of Set 1 | villanueva
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=villanueva
    Processing Record 151 of Set 1 | hirara
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=hirara
    Processing Record 152 of Set 1 | neepawa
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=neepawa
    Processing Record 153 of Set 1 | cabo san lucas
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=cabo san lucas
    Processing Record 154 of Set 1 | monte cristi
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=monte cristi
    City not found in OpenWeatherMap API.
    Processing Record 155 of Set 1 | mackenzie
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=mackenzie
    Processing Record 156 of Set 1 | north bend
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=north bend
    Processing Record 157 of Set 1 | vanavara
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=vanavara
    Processing Record 158 of Set 1 | partizansk
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=partizansk
    Processing Record 159 of Set 1 | luderitz
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=luderitz
    Processing Record 160 of Set 1 | goderich
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=goderich
    Processing Record 161 of Set 1 | klyuchi
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=klyuchi
    Processing Record 162 of Set 1 | yirol
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=yirol
    City not found in OpenWeatherMap API.
    Processing Record 163 of Set 1 | greenfield
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=greenfield
    Processing Record 164 of Set 1 | mount isa
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=mount isa
    Processing Record 165 of Set 1 | kizema
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=kizema
    Processing Record 166 of Set 1 | langelsheim
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=langelsheim
    Processing Record 167 of Set 1 | barrow
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=barrow
    Processing Record 168 of Set 1 | joshimath
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=joshimath
    Processing Record 169 of Set 1 | umm lajj
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=umm lajj
    Processing Record 170 of Set 1 | amderma
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=amderma
    City not found in OpenWeatherMap API.
    Processing Record 171 of Set 1 | havre-saint-pierre
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=havre-saint-pierre
    Processing Record 172 of Set 1 | lerwick
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=lerwick
    Processing Record 173 of Set 1 | barcelos
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=barcelos
    Processing Record 174 of Set 1 | hailar
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=hailar
    Processing Record 175 of Set 1 | codrington
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=codrington
    Processing Record 176 of Set 1 | taylor
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=taylor
    Processing Record 177 of Set 1 | meulaboh
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=meulaboh
    Processing Record 178 of Set 1 | toliary
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=toliary
    City not found in OpenWeatherMap API.
    Processing Record 179 of Set 1 | karratha
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=karratha
    Processing Record 180 of Set 1 | nuuk
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=nuuk
    Processing Record 181 of Set 1 | ha tinh
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=ha tinh
    Processing Record 182 of Set 1 | chuy
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=chuy
    Processing Record 183 of Set 1 | umm kaddadah
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=umm kaddadah
    City not found in OpenWeatherMap API.
    Processing Record 184 of Set 1 | wittingen
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=wittingen
    Processing Record 185 of Set 1 | torbay
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=torbay
    Processing Record 186 of Set 1 | oktyabrskoye
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=oktyabrskoye
    Processing Record 187 of Set 1 | vostok
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=vostok
    Processing Record 188 of Set 1 | dragoman
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=dragoman
    Processing Record 189 of Set 1 | port hardy
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=port hardy
    Processing Record 190 of Set 1 | estelle
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=estelle
    Processing Record 191 of Set 1 | tiznit
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=tiznit
    Processing Record 192 of Set 1 | norman wells
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=norman wells
    Processing Record 193 of Set 1 | nantucket
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=nantucket
    Processing Record 194 of Set 1 | tamandare
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=tamandare
    Processing Record 195 of Set 1 | rocha
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=rocha
    Processing Record 196 of Set 1 | east london
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=east london
    Processing Record 197 of Set 1 | hithadhoo
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=hithadhoo
    Processing Record 198 of Set 1 | harper
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=harper
    Processing Record 199 of Set 1 | provideniya
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=provideniya
    Processing Record 200 of Set 1 | sitka
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=sitka
    Processing Record 201 of Set 1 | dobson
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=dobson
    Processing Record 202 of Set 1 | filadelfia
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=filadelfia
    Processing Record 203 of Set 1 | mahebourg
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=mahebourg
    Processing Record 204 of Set 1 | indianola
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=indianola
    Processing Record 205 of Set 1 | pitimbu
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=pitimbu
    Processing Record 206 of Set 1 | yarim
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=yarim
    Processing Record 207 of Set 1 | ribeira grande
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=ribeira grande
    Processing Record 208 of Set 1 | gua
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=gua
    Processing Record 209 of Set 1 | gat
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=gat
    City not found in OpenWeatherMap API.
    Processing Record 210 of Set 1 | labuhan
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=labuhan
    Processing Record 211 of Set 1 | praia da vitoria
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=praia da vitoria
    Processing Record 212 of Set 1 | zelenogorskiy
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=zelenogorskiy
    Processing Record 213 of Set 1 | gravdal
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=gravdal
    Processing Record 214 of Set 1 | makakilo city
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=makakilo city
    Processing Record 215 of Set 1 | tezu
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=tezu
    Processing Record 216 of Set 1 | zheleznodorozhnyy
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=zheleznodorozhnyy
    Processing Record 217 of Set 1 | saint-philippe
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=saint-philippe
    Processing Record 218 of Set 1 | hay river
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=hay river
    Processing Record 219 of Set 1 | la crosse
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=la crosse
    Processing Record 220 of Set 1 | guerrero negro
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=guerrero negro
    Processing Record 221 of Set 1 | naze
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=naze
    Processing Record 222 of Set 1 | great yarmouth
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=great yarmouth
    Processing Record 223 of Set 1 | lubango
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=lubango
    Processing Record 224 of Set 1 | lolua
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=lolua
    City not found in OpenWeatherMap API.
    Processing Record 225 of Set 1 | ilulissat
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=ilulissat
    Processing Record 226 of Set 1 | amga
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=amga
    Processing Record 227 of Set 1 | yumbe
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=yumbe
    Processing Record 228 of Set 1 | cabras
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=cabras
    Processing Record 229 of Set 1 | husavik
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=husavik
    Processing Record 230 of Set 1 | linhai
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=linhai
    Processing Record 231 of Set 1 | udachnyy
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=udachnyy
    Processing Record 232 of Set 1 | winneba
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=winneba
    Processing Record 233 of Set 1 | vieste
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=vieste
    Processing Record 234 of Set 1 | kurikka
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=kurikka
    Processing Record 235 of Set 1 | kalmar
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=kalmar
    Processing Record 236 of Set 1 | bitung
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=bitung
    Processing Record 237 of Set 1 | hami
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=hami
    Processing Record 238 of Set 1 | carbonia
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=carbonia
    Processing Record 239 of Set 1 | utiroa
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=utiroa
    City not found in OpenWeatherMap API.
    Processing Record 240 of Set 1 | mandalgovi
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=mandalgovi
    Processing Record 241 of Set 1 | kropotkin
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=kropotkin
    Processing Record 242 of Set 1 | sungaipenuh
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=sungaipenuh
    Processing Record 243 of Set 1 | phan rang
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=phan rang
    City not found in OpenWeatherMap API.
    Processing Record 244 of Set 1 | la libertad
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=la libertad
    Processing Record 245 of Set 1 | meadow lake
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=meadow lake
    Processing Record 246 of Set 1 | baoqing
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=baoqing
    Processing Record 247 of Set 1 | prainha
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=prainha
    Processing Record 248 of Set 1 | aykhal
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=aykhal
    Processing Record 249 of Set 1 | jerome
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=jerome
    Processing Record 250 of Set 1 | victoria
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=victoria
    Processing Record 251 of Set 1 | otofuke
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=otofuke
    Processing Record 252 of Set 1 | ruteng
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=ruteng
    Processing Record 253 of Set 1 | palmer
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=palmer
    Processing Record 254 of Set 1 | mingshui
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=mingshui
    Processing Record 255 of Set 1 | attawapiskat
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=attawapiskat
    City not found in OpenWeatherMap API.
    Processing Record 256 of Set 1 | cayenne
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=cayenne
    Processing Record 257 of Set 1 | fallon
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=fallon
    Processing Record 258 of Set 1 | shelburne
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=shelburne
    Processing Record 259 of Set 1 | winslow
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=winslow
    Processing Record 260 of Set 1 | turayf
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=turayf
    Processing Record 261 of Set 1 | ballina
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=ballina
    Processing Record 262 of Set 1 | almaznyy
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=almaznyy
    Processing Record 263 of Set 1 | yichun
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=yichun
    Processing Record 264 of Set 1 | erzin
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=erzin
    Processing Record 265 of Set 1 | santa catarina de tepehuanes
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=santa catarina de tepehuanes
    Processing Record 266 of Set 1 | souillac
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=souillac
    Processing Record 267 of Set 1 | bairiki
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=bairiki
    City not found in OpenWeatherMap API.
    Processing Record 268 of Set 1 | edd
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=edd
    Processing Record 269 of Set 1 | la ronge
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=la ronge
    Processing Record 270 of Set 1 | paragominas
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=paragominas
    Processing Record 271 of Set 1 | buchanan
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=buchanan
    Processing Record 272 of Set 1 | pitelino
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=pitelino
    Processing Record 273 of Set 1 | reading
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=reading
    Processing Record 274 of Set 1 | karaul
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=karaul
    City not found in OpenWeatherMap API.
    Processing Record 275 of Set 1 | seminole
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=seminole
    Processing Record 276 of Set 1 | kahului
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=kahului
    Processing Record 277 of Set 1 | crab hill
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=crab hill
    City not found in OpenWeatherMap API.
    Processing Record 278 of Set 1 | terenos
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=terenos
    Processing Record 279 of Set 1 | lorengau
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=lorengau
    Processing Record 280 of Set 1 | mets masrik
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=mets masrik
    Processing Record 281 of Set 1 | shuiji
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=shuiji
    Processing Record 282 of Set 1 | kavieng
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=kavieng
    Processing Record 283 of Set 1 | aktau
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=aktau
    Processing Record 284 of Set 1 | emilio carranza
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=emilio carranza
    City not found in OpenWeatherMap API.
    Processing Record 285 of Set 1 | tecoanapa
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=tecoanapa
    Processing Record 286 of Set 1 | el campo
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=el campo
    Processing Record 287 of Set 1 | licheng
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=licheng
    Processing Record 288 of Set 1 | mercedes
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=mercedes
    Processing Record 289 of Set 1 | hunza
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=hunza
    City not found in OpenWeatherMap API.
    Processing Record 290 of Set 1 | san jeronimo
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=san jeronimo
    Processing Record 291 of Set 1 | lagoa
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=lagoa
    Processing Record 292 of Set 1 | nguiu
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=nguiu
    City not found in OpenWeatherMap API.
    Processing Record 293 of Set 1 | kruisfontein
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=kruisfontein
    Processing Record 294 of Set 1 | tuktoyaktuk
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=tuktoyaktuk
    Processing Record 295 of Set 1 | tiksi
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=tiksi
    Processing Record 296 of Set 1 | san cristobal
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=san cristobal
    Processing Record 297 of Set 1 | presidente olegario
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=presidente olegario
    Processing Record 298 of Set 1 | kuching
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=kuching
    Processing Record 299 of Set 1 | tasiilaq
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=tasiilaq
    Processing Record 300 of Set 1 | aliartos
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=aliartos
    Processing Record 301 of Set 1 | skagastrond
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=skagastrond
    City not found in OpenWeatherMap API.
    Processing Record 302 of Set 1 | ust-bolsheretsk
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=ust-bolsheretsk
    City not found in OpenWeatherMap API.
    Processing Record 303 of Set 1 | marsh harbour
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=marsh harbour
    Processing Record 304 of Set 1 | along
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=along
    Processing Record 305 of Set 1 | nome
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=nome
    Processing Record 306 of Set 1 | ambilobe
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=ambilobe
    Processing Record 307 of Set 1 | salalah
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=salalah
    Processing Record 308 of Set 1 | cockburn town
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=cockburn town
    Processing Record 309 of Set 1 | belushya guba
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=belushya guba
    City not found in OpenWeatherMap API.
    Processing Record 310 of Set 1 | koslan
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=koslan
    Processing Record 311 of Set 1 | lodja
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=lodja
    Processing Record 312 of Set 1 | deputatskiy
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=deputatskiy
    Processing Record 313 of Set 1 | zwedru
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=zwedru
    Processing Record 314 of Set 1 | olafsvik
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=olafsvik
    City not found in OpenWeatherMap API.
    Processing Record 315 of Set 1 | teguldet
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=teguldet
    Processing Record 316 of Set 1 | wewak
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=wewak
    Processing Record 317 of Set 1 | esperance
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=esperance
    Processing Record 318 of Set 1 | new norfolk
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=new norfolk
    Processing Record 319 of Set 1 | isangel
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=isangel
    Processing Record 320 of Set 1 | pangnirtung
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=pangnirtung
    Processing Record 321 of Set 1 | ialibu
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=ialibu
    Processing Record 322 of Set 1 | springdale
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=springdale
    Processing Record 323 of Set 1 | pozo colorado
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=pozo colorado
    City not found in OpenWeatherMap API.
    Processing Record 324 of Set 1 | necochea
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=necochea
    Processing Record 325 of Set 1 | ilhabela
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=ilhabela
    Processing Record 326 of Set 1 | palma del rio
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=palma del rio
    Processing Record 327 of Set 1 | newport
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=newport
    Processing Record 328 of Set 1 | praya
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=praya
    Processing Record 329 of Set 1 | ayan
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=ayan
    Processing Record 330 of Set 1 | palabuhanratu
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=palabuhanratu
    City not found in OpenWeatherMap API.
    Processing Record 331 of Set 1 | westport
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=westport
    Processing Record 332 of Set 1 | matane
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=matane
    Processing Record 333 of Set 1 | sola
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=sola
    Processing Record 334 of Set 1 | floro
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=floro
    Processing Record 335 of Set 1 | la baule-escoublac
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=la baule-escoublac
    Processing Record 336 of Set 1 | kabinda
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=kabinda
    Processing Record 337 of Set 1 | roblin
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=roblin
    Processing Record 338 of Set 1 | alofi
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=alofi
    Processing Record 339 of Set 1 | pisz
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=pisz
    Processing Record 340 of Set 1 | clyde river
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=clyde river
    Processing Record 341 of Set 1 | chumikan
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=chumikan
    Processing Record 342 of Set 1 | santa cruz do capibaribe
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=santa cruz do capibaribe
    Processing Record 343 of Set 1 | itarema
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=itarema
    City not found in OpenWeatherMap API.
    Processing Record 344 of Set 1 | chapais
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=chapais
    Processing Record 345 of Set 1 | ganzhou
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=ganzhou
    Processing Record 346 of Set 1 | valparaiso
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=valparaiso
    Processing Record 347 of Set 1 | novaya zaimka
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=novaya zaimka
    Processing Record 348 of Set 1 | carnarvon
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=carnarvon
    Processing Record 349 of Set 1 | nikolskoye
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=nikolskoye
    City not found in OpenWeatherMap API.
    Processing Record 350 of Set 1 | hovd
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=hovd
    Processing Record 351 of Set 1 | tabiauea
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=tabiauea
    City not found in OpenWeatherMap API.
    Processing Record 352 of Set 1 | chany
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=chany
    Processing Record 353 of Set 1 | mezen
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=mezen
    Processing Record 354 of Set 1 | sept-iles
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=sept-iles
    Processing Record 355 of Set 1 | pisco
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=pisco
    Processing Record 356 of Set 1 | sao filipe
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=sao filipe
    Processing Record 357 of Set 1 | dandong
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=dandong
    Processing Record 358 of Set 1 | huarmey
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=huarmey
    Processing Record 359 of Set 1 | kwinana
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=kwinana
    Processing Record 360 of Set 1 | lircay
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=lircay
    City not found in OpenWeatherMap API.
    Processing Record 361 of Set 1 | seydisehir
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=seydisehir
    Processing Record 362 of Set 1 | mayo
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=mayo
    Processing Record 363 of Set 1 | formoso do araguaia
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=formoso do araguaia
    City not found in OpenWeatherMap API.
    Processing Record 364 of Set 1 | strezhevoy
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=strezhevoy
    Processing Record 365 of Set 1 | smoky lake
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=smoky lake
    Processing Record 366 of Set 1 | asau
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=asau
    Processing Record 367 of Set 1 | bilibino
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=bilibino
    Processing Record 368 of Set 1 | mokhsogollokh
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=mokhsogollokh
    Processing Record 369 of Set 1 | salinopolis
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=salinopolis
    Processing Record 370 of Set 1 | arman
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=arman
    Processing Record 371 of Set 1 | camopi
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=camopi
    Processing Record 372 of Set 1 | bud
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=bud
    Processing Record 373 of Set 1 | lamu
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=lamu
    Processing Record 374 of Set 1 | waipawa
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=waipawa
    Processing Record 375 of Set 1 | vanimo
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=vanimo
    Processing Record 376 of Set 1 | hualmay
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=hualmay
    Processing Record 377 of Set 1 | nambucca heads
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=nambucca heads
    Processing Record 378 of Set 1 | great bend
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=great bend
    Processing Record 379 of Set 1 | tsagan aman
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=tsagan aman
    Processing Record 380 of Set 1 | katsuura
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=katsuura
    Processing Record 381 of Set 1 | aden
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=aden
    Processing Record 382 of Set 1 | longyearbyen
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=longyearbyen
    Processing Record 383 of Set 1 | nanortalik
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=nanortalik
    Processing Record 384 of Set 1 | nhulunbuy
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=nhulunbuy
    Processing Record 385 of Set 1 | clarence town
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=clarence town
    Processing Record 386 of Set 1 | manzhouli
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=manzhouli
    Processing Record 387 of Set 1 | faya
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=faya
    City not found in OpenWeatherMap API.
    Processing Record 388 of Set 1 | byron bay
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=byron bay
    Processing Record 389 of Set 1 | klaksvik
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=klaksvik
    Processing Record 390 of Set 1 | stromness
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=stromness
    Processing Record 391 of Set 1 | laguna
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=laguna
    Processing Record 392 of Set 1 | kamenskoye
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=kamenskoye
    City not found in OpenWeatherMap API.
    Processing Record 393 of Set 1 | hasaki
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=hasaki
    Processing Record 394 of Set 1 | yulara
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=yulara
    Processing Record 395 of Set 1 | beringovskiy
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=beringovskiy
    Processing Record 396 of Set 1 | ostrovnoy
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=ostrovnoy
    Processing Record 397 of Set 1 | ouadda
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=ouadda
    Processing Record 398 of Set 1 | kutum
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=kutum
    Processing Record 399 of Set 1 | salvador
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=salvador
    Processing Record 400 of Set 1 | chebsara
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=chebsara
    Processing Record 401 of Set 1 | varberg
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=varberg
    Processing Record 402 of Set 1 | riohacha
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=riohacha
    Processing Record 403 of Set 1 | iglesias
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=iglesias
    Processing Record 404 of Set 1 | gusinoye ozero
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=gusinoye ozero
    Processing Record 405 of Set 1 | tuy hoa
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=tuy hoa
    Processing Record 406 of Set 1 | nemuro
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=nemuro
    Processing Record 407 of Set 1 | yatou
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=yatou
    Processing Record 408 of Set 1 | mao
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=mao
    Processing Record 409 of Set 1 | taoudenni
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=taoudenni
    Processing Record 410 of Set 1 | jaru
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=jaru
    Processing Record 411 of Set 1 | kisangani
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=kisangani
    Processing Record 412 of Set 1 | dumka
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=dumka
    Processing Record 413 of Set 1 | leshukonskoye
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=leshukonskoye
    Processing Record 414 of Set 1 | paka
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=paka
    Processing Record 415 of Set 1 | ladozhskaya
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=ladozhskaya
    Processing Record 416 of Set 1 | adrar
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=adrar
    Processing Record 417 of Set 1 | oistins
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=oistins
    Processing Record 418 of Set 1 | namatanai
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=namatanai
    Processing Record 419 of Set 1 | lata
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=lata
    Processing Record 420 of Set 1 | buguruslan
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=buguruslan
    Processing Record 421 of Set 1 | chiredzi
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=chiredzi
    Processing Record 422 of Set 1 | ponta do sol
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=ponta do sol
    Processing Record 423 of Set 1 | khash
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=khash
    Processing Record 424 of Set 1 | fortuna
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=fortuna
    Processing Record 425 of Set 1 | hambantota
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=hambantota
    Processing Record 426 of Set 1 | kayunga
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=kayunga
    Processing Record 427 of Set 1 | conceicao do araguaia
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=conceicao do araguaia
    Processing Record 428 of Set 1 | kuche
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=kuche
    City not found in OpenWeatherMap API.
    Processing Record 429 of Set 1 | svetlyy
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=svetlyy
    Processing Record 430 of Set 1 | talcahuano
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=talcahuano
    Processing Record 431 of Set 1 | khani
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=khani
    City not found in OpenWeatherMap API.
    Processing Record 432 of Set 1 | sabang
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=sabang
    Processing Record 433 of Set 1 | riobamba
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=riobamba
    Processing Record 434 of Set 1 | bengkulu
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=bengkulu
    Processing Record 435 of Set 1 | fonte boa
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=fonte boa
    Processing Record 436 of Set 1 | ciras
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=ciras
    City not found in OpenWeatherMap API.
    Processing Record 437 of Set 1 | saint george
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=saint george
    Processing Record 438 of Set 1 | semnan
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=semnan
    Processing Record 439 of Set 1 | touros
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=touros
    Processing Record 440 of Set 1 | liverpool
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=liverpool
    Processing Record 441 of Set 1 | grand gaube
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=grand gaube
    Processing Record 442 of Set 1 | khuzdar
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=khuzdar
    Processing Record 443 of Set 1 | sokolo
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=sokolo
    Processing Record 444 of Set 1 | marystown
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=marystown
    Processing Record 445 of Set 1 | moengo
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=moengo
    Processing Record 446 of Set 1 | kismayo
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=kismayo
    City not found in OpenWeatherMap API.
    Processing Record 447 of Set 1 | jijiga
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=jijiga
    Processing Record 448 of Set 1 | mattru
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=mattru
    City not found in OpenWeatherMap API.
    Processing Record 449 of Set 1 | grindavik
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=grindavik
    Processing Record 450 of Set 1 | belmonte
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=belmonte
    Processing Record 451 of Set 1 | karkaralinsk
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=karkaralinsk
    City not found in OpenWeatherMap API.
    Processing Record 452 of Set 1 | florencia
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=florencia
    Processing Record 453 of Set 1 | camacha
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=camacha
    Processing Record 454 of Set 1 | didwana
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=didwana
    Processing Record 455 of Set 1 | santa lucia
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=santa lucia
    Processing Record 456 of Set 1 | sinop
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=sinop
    Processing Record 457 of Set 1 | san quintin
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=san quintin
    Processing Record 458 of Set 1 | port-gentil
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=port-gentil
    Processing Record 459 of Set 1 | zhigansk
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=zhigansk
    Processing Record 460 of Set 1 | wajima
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=wajima
    Processing Record 461 of Set 1 | shingu
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=shingu
    Processing Record 462 of Set 1 | gualaceo
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=gualaceo
    Processing Record 463 of Set 1 | atar
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=atar
    Processing Record 464 of Set 1 | pahrump
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=pahrump
    Processing Record 465 of Set 1 | dingle
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=dingle
    Processing Record 466 of Set 1 | belaya gora
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=belaya gora
    Processing Record 467 of Set 1 | tres lagoas
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=tres lagoas
    Processing Record 468 of Set 1 | talnakh
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=talnakh
    Processing Record 469 of Set 1 | cap-aux-meules
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=cap-aux-meules
    Processing Record 470 of Set 1 | abadan
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=abadan
    Processing Record 471 of Set 1 | lazaro cardenas
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=lazaro cardenas
    Processing Record 472 of Set 1 | bydgoszcz
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=bydgoszcz
    Processing Record 473 of Set 1 | morant bay
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=morant bay
    Processing Record 474 of Set 1 | doha
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=doha
    Processing Record 475 of Set 1 | taman
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=taman
    Processing Record 476 of Set 1 | lakes entrance
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=lakes entrance
    Processing Record 477 of Set 1 | biltine
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=biltine
    Processing Record 478 of Set 1 | maragogi
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=maragogi
    Processing Record 479 of Set 1 | te anau
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=te anau
    Processing Record 480 of Set 1 | general roca
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=general roca
    Processing Record 481 of Set 1 | sioux lookout
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=sioux lookout
    Processing Record 482 of Set 1 | samusu
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=samusu
    City not found in OpenWeatherMap API.
    Processing Record 483 of Set 1 | shushenskoye
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=shushenskoye
    Processing Record 484 of Set 1 | dzhebariki-khaya
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=dzhebariki-khaya
    Processing Record 485 of Set 1 | dubbo
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=dubbo
    Processing Record 486 of Set 1 | fuling
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=fuling
    Processing Record 487 of Set 1 | lincoln
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=lincoln
    Processing Record 488 of Set 1 | north platte
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=north platte
    Processing Record 489 of Set 1 | saint-francois
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=saint-francois
    Processing Record 490 of Set 1 | port lincoln
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=port lincoln
    Processing Record 491 of Set 1 | yeppoon
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=yeppoon
    Processing Record 492 of Set 1 | namibe
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=namibe
    Processing Record 493 of Set 1 | tarudant
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=tarudant
    City not found in OpenWeatherMap API.
    Processing Record 494 of Set 1 | varkaus
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=varkaus
    Processing Record 495 of Set 1 | kumasi
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=kumasi
    Processing Record 496 of Set 1 | fairbanks
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=fairbanks
    Processing Record 497 of Set 1 | nabire
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=nabire
    Processing Record 498 of Set 1 | port blair
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=port blair
    Processing Record 499 of Set 1 | kashi
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=kashi
    Processing Record 500 of Set 1 | orlik
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=orlik
    Processing Record 501 of Set 1 | port hedland
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=port hedland
    Processing Record 502 of Set 1 | bubaque
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=bubaque
    Processing Record 503 of Set 1 | xuddur
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=xuddur
    Processing Record 504 of Set 1 | eastbourne
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=eastbourne
    Processing Record 505 of Set 1 | mildura
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=mildura
    Processing Record 506 of Set 1 | umzimvubu
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=umzimvubu
    City not found in OpenWeatherMap API.
    Processing Record 507 of Set 1 | isla mujeres
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=isla mujeres
    Processing Record 508 of Set 1 | murray bridge
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=murray bridge
    Processing Record 509 of Set 1 | kem
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=kem
    Processing Record 510 of Set 1 | sibolga
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=sibolga
    Processing Record 511 of Set 1 | gazni
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=gazni
    City not found in OpenWeatherMap API.
    Processing Record 512 of Set 1 | palmares do sul
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=palmares do sul
    Processing Record 513 of Set 1 | nouadhibou
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=nouadhibou
    Processing Record 514 of Set 1 | haines junction
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=haines junction
    Processing Record 515 of Set 1 | veraval
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=veraval
    Processing Record 516 of Set 1 | taltal
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=taltal
    Processing Record 517 of Set 1 | cognac
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=cognac
    Processing Record 518 of Set 1 | nyandoma
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=nyandoma
    Processing Record 519 of Set 1 | shenzhen
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=shenzhen
    Processing Record 520 of Set 1 | san vicente
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=san vicente
    Processing Record 521 of Set 1 | baiyin
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=baiyin
    Processing Record 522 of Set 1 | denia
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=denia
    Processing Record 523 of Set 1 | bogdanovich
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=bogdanovich
    Processing Record 524 of Set 1 | rokytne
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=rokytne
    Processing Record 525 of Set 1 | reconquista
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=reconquista
    Processing Record 526 of Set 1 | eldorado
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=eldorado
    Processing Record 527 of Set 1 | solwezi
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=solwezi
    Processing Record 528 of Set 1 | zholymbet
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=zholymbet
    Processing Record 529 of Set 1 | zhadovka
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=zhadovka
    Processing Record 530 of Set 1 | stornoway
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=stornoway
    Processing Record 531 of Set 1 | lixourion
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=lixourion
    Processing Record 532 of Set 1 | quthing
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=quthing
    Processing Record 533 of Set 1 | iquique
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=iquique
    Processing Record 534 of Set 1 | dunedin
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=dunedin
    Processing Record 535 of Set 1 | gravelbourg
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=gravelbourg
    Processing Record 536 of Set 1 | pacific grove
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=pacific grove
    Processing Record 537 of Set 1 | benguela
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=benguela
    Processing Record 538 of Set 1 | shitanjing
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=shitanjing
    Processing Record 539 of Set 1 | ambodifototra
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=ambodifototra
    City not found in OpenWeatherMap API.
    Processing Record 540 of Set 1 | aspindza
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=aspindza
    Processing Record 541 of Set 1 | guiratinga
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=guiratinga
    Processing Record 542 of Set 1 | saint-augustin
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=saint-augustin
    Processing Record 543 of Set 1 | kuryk
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=kuryk
    Processing Record 544 of Set 1 | coquimbo
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=coquimbo
    Processing Record 545 of Set 1 | hirna
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=hirna
    Processing Record 546 of Set 1 | srandakan
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=srandakan
    Processing Record 547 of Set 1 | villacarrillo
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=villacarrillo
    Processing Record 548 of Set 1 | aguimes
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=aguimes
    Processing Record 549 of Set 1 | ranau
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=ranau
    Processing Record 550 of Set 1 | bandarbeyla
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=bandarbeyla
    Processing Record 551 of Set 1 | hokitika
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=hokitika
    Processing Record 552 of Set 1 | jawhar
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=jawhar
    Processing Record 553 of Set 1 | pak phanang
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=pak phanang
    Processing Record 554 of Set 1 | port maria
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=port maria
    Processing Record 555 of Set 1 | buala
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=buala
    Processing Record 556 of Set 1 | canico
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=canico
    Processing Record 557 of Set 1 | palaiokomi
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=palaiokomi
    Processing Record 558 of Set 1 | asosa
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=asosa
    Processing Record 559 of Set 1 | guiglo
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=guiglo
    Processing Record 560 of Set 1 | kiknur
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=kiknur
    Processing Record 561 of Set 1 | mizdah
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=mizdah
    Processing Record 562 of Set 1 | tautira
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=tautira
    Processing Record 563 of Set 1 | irati
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=irati
    Processing Record 564 of Set 1 | coihaique
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=coihaique
    Processing Record 565 of Set 1 | kununurra
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=kununurra
    Processing Record 566 of Set 1 | sobolevo
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=sobolevo
    City not found in OpenWeatherMap API.
    Processing Record 567 of Set 1 | pamekasan
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=pamekasan
    Processing Record 568 of Set 1 | wattegama
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=wattegama
    Processing Record 569 of Set 1 | pasewalk
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=pasewalk
    Processing Record 570 of Set 1 | vaovai
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=vaovai
    City not found in OpenWeatherMap API.
    Processing Record 571 of Set 1 | kirakira
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=kirakira
    Processing Record 572 of Set 1 | acapulco
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=acapulco
    City not found in OpenWeatherMap API.
    Processing Record 573 of Set 1 | saint andrews
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=saint andrews
    Processing Record 574 of Set 1 | lompoc
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=lompoc
    Processing Record 575 of Set 1 | lambari
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=lambari
    Processing Record 576 of Set 1 | moerai
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=moerai
    Processing Record 577 of Set 1 | whitehorse
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=whitehorse
    Processing Record 578 of Set 1 | totness
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=totness
    Processing Record 579 of Set 1 | anadyr
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=anadyr
    Processing Record 580 of Set 1 | marcona
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=marcona
    City not found in OpenWeatherMap API.
    Processing Record 581 of Set 1 | show low
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=show low
    Processing Record 582 of Set 1 | tuatapere
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=tuatapere
    Processing Record 583 of Set 1 | hinton
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=hinton
    Processing Record 584 of Set 1 | atbasar
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=atbasar
    Processing Record 585 of Set 1 | ixtapa
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=ixtapa
    Processing Record 586 of Set 1 | prata
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=prata
    Processing Record 587 of Set 1 | mantua
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=mantua
    Processing Record 588 of Set 1 | kangavar
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=kangavar
    Processing Record 589 of Set 1 | kamenka
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=kamenka
    Processing Record 590 of Set 1 | feijo
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=feijo
    Processing Record 591 of Set 1 | satitoa
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=satitoa
    City not found in OpenWeatherMap API.
    Processing Record 592 of Set 1 | imelda
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=imelda
    Processing Record 593 of Set 1 | kieta
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=kieta
    Processing Record 594 of Set 1 | mahibadhoo
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=mahibadhoo
    Processing Record 595 of Set 1 | bhopal
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=bhopal
    Processing Record 596 of Set 1 | richards bay
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=richards bay
    Processing Record 597 of Set 1 | bideford
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=bideford
    Processing Record 598 of Set 1 | bantogon
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=bantogon
    Processing Record 599 of Set 1 | ayr
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=ayr
    Processing Record 600 of Set 1 | marienburg
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=marienburg
    Processing Record 601 of Set 1 | paita
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=paita
    Processing Record 602 of Set 1 | porbandar
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=porbandar
    Processing Record 603 of Set 1 | yerbogachen
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=yerbogachen
    Processing Record 604 of Set 1 | ribeira brava
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=ribeira brava
    Processing Record 605 of Set 1 | alpena
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=alpena
    Processing Record 606 of Set 1 | olds
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=olds
    Processing Record 607 of Set 1 | loanda
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=loanda
    Processing Record 608 of Set 1 | saint-georges
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=saint-georges
    Processing Record 609 of Set 1 | beloha
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=beloha
    Processing Record 610 of Set 1 | roma
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=roma
    Processing Record 611 of Set 1 | we
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=we
    City not found in OpenWeatherMap API.
    Processing Record 612 of Set 1 | batagay-alyta
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=batagay-alyta
    Processing Record 613 of Set 1 | muros
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=muros
    Processing Record 614 of Set 1 | naftah
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=naftah
    City not found in OpenWeatherMap API.
    Processing Record 615 of Set 1 | saint-pacome
    http://api.openweathermap.org/data/2.5/weather?units=Imperial&appid=eb1466db7ae3a93e6f626541f5ba5d90&q=saint-pacome
    City not found in OpenWeatherMap API.
    -----------------------------
    Data Retrieval Complete
    -----------------------------
    


```python
name_data = [data.get("name") for data in weather_data]
clouds_data = [data.get("clouds").get("all") for data in weather_data]
country_data = [data.get("sys").get("country") for data in weather_data]
dt_data = [data.get("dt") for data in weather_data]
humidity_data = [data.get("main").get("humidity") for data in weather_data]
lat_data = [data.get("coord").get("lat") for data in weather_data]
lon_data = [data.get("coord").get("lon") for data in weather_data]
temp_max_data = [data.get("main").get("temp_max") for data in weather_data]
wind_speed_data = [data.get("wind").get("speed") for data in weather_data]

weather_data_pd = {"City": name_data, "Cloudiness": clouds_data, "Country": country_data, "Date": dt_data, "Humidity": humidity_data, "Lat": lat_data, "Lng": lon_data, "Max Temp": temp_max_data, "Wind Speed": wind_speed_data}
weather_data_pd = pd.DataFrame(weather_data_pd)
weather_data_pd.count()
```




    City          542
    Cloudiness    542
    Country       542
    Date          542
    Humidity      542
    Lat           542
    Lng           542
    Max Temp      542
    Wind Speed    542
    dtype: int64




```python
weather_data_pd.to_csv("Resources/weather_data.csv")
weather_data_pd.head()
```




<div>
<style>
    .dataframe thead tr:only-child th {
        text-align: right;
    }

    .dataframe thead th {
        text-align: left;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>City</th>
      <th>Cloudiness</th>
      <th>Country</th>
      <th>Date</th>
      <th>Humidity</th>
      <th>Lat</th>
      <th>Lng</th>
      <th>Max Temp</th>
      <th>Wind Speed</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Busselton</td>
      <td>0</td>
      <td>AU</td>
      <td>1513837529</td>
      <td>70</td>
      <td>-33.65</td>
      <td>115.33</td>
      <td>79.62</td>
      <td>7.20</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Rikitea</td>
      <td>64</td>
      <td>PF</td>
      <td>1513837218</td>
      <td>100</td>
      <td>-23.12</td>
      <td>-134.97</td>
      <td>77.46</td>
      <td>7.99</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Port Alfred</td>
      <td>0</td>
      <td>ZA</td>
      <td>1513837274</td>
      <td>83</td>
      <td>-33.59</td>
      <td>26.89</td>
      <td>72.06</td>
      <td>11.23</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Cidreira</td>
      <td>32</td>
      <td>BR</td>
      <td>1513837606</td>
      <td>98</td>
      <td>-30.18</td>
      <td>-50.21</td>
      <td>70.76</td>
      <td>8.66</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Zharkent</td>
      <td>0</td>
      <td>KZ</td>
      <td>1513837746</td>
      <td>61</td>
      <td>44.16</td>
      <td>80.00</td>
      <td>15.86</td>
      <td>1.61</td>
    </tr>
  </tbody>
</table>
</div>




```python
print("Latitude vs. Temperature Plot")
seaborn.set()
plt.scatter(weather_data_pd["Lat"], weather_data_pd["Max Temp"], marker="o", edgecolors="black")
plt.title("City Latitude vs. Max Temperature (12/20/17)")
plt.ylabel("Max Temperature (F)")
plt.ylim(-100, 150)
plt.xlabel("Latitude")
plt.xlim(-80, 100)
plt.grid(True)
plt.savefig("Resources/LatitudeVsTemperaturePlot.png")
plt.show()
```

    Latitude vs. Temperature Plot
    


![png](output_5_1.png)



```python
print("Latitude vs. Humidity Plot")
seaborn.set()
plt.scatter(weather_data_pd["Lat"], weather_data_pd["Humidity"], marker="o", edgecolors="black")
plt.title("City Latitude vs. Humidity (12/20/17)")
plt.ylabel("Humidity (%)")
plt.ylim(-20, 120)
plt.xlabel("Latitude")
plt.xlim(-80, 100)
plt.grid(True)
plt.savefig("Resources/LatitudeVsHumidityPlot.png")
plt.show()
```

    Latitude vs. Humidity Plot
    


![png](output_6_1.png)



```python
print("Latitude vs. Cloudiness Plot")
seaborn.set()
plt.scatter(weather_data_pd["Lat"], weather_data_pd["Cloudiness"], marker="o", edgecolors="black")
plt.title("City Latitude vs. Cloudiness (12/20/17)")
plt.ylabel("Cloudiness (%)")
plt.ylim(-20, 120)
plt.xlabel("Latitude")
plt.xlim(-80, 100)
plt.grid(True)
plt.savefig("Resources/LatitudeVsCloudinessPlot.png")
plt.show()
```

    Latitude vs. Cloudiness Plot
    


![png](output_7_1.png)



```python
print("Latitude vs. Wind Speed Plot")
seaborn.set()
plt.scatter(weather_data_pd["Lat"], weather_data_pd["Wind Speed"], marker="o", edgecolors="black")
plt.title("City Latitude vs. Wind Speed (12/20/17)")
plt.ylabel("Wind Speed (mph)")
plt.ylim(-5, 50)
plt.xlabel("Latitude")
plt.xlim(-80, 100)
plt.grid(True)
plt.savefig("Resources/LatitudeVsWindSpeedPlot.png")
plt.show()
```

    Latitude vs. Wind Speed Plot
    


![png](output_8_1.png)

