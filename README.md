# Pilot ostateczny

## Założenia:
Generyczny polot *o niepojętej mocy* mający służć za generyczny pilot do czegokowiek, działający z równie generycznym odbiornikiem.

Wstępnie wybór padł na wykorzystanie modułów [LoRa](https://lora-alliance.org/), ze względu na dość dobre właściwości i niskie koszta


## Nadajnik

Cały pomysł urodził się na bazie [ExpressLRS](https://www.expresslrs.org/) który ma służyć jako protokół do kontrolowana dronów (nie tylko latających) w czasie rzeczywistym.Z tego co widziałem wspiera telemetrie i przesyłąnie obrazu (i jest open source)

atmega z doklejonym modułem LoRa [link](https://nettigo.pl/products/modul-lora32u4-ii-v1-3-lora-sx1276-i-atmega32u4)

nagi moduł LoRa [link](https://techfun.sk/pl/produkt/modu%C5%82-komunikacyjny-sx1276-lora-433-868-915-mhz/) [dokumentacja](https://cdn.sparkfun.com/assets/learn_tutorials/8/0/4/RFM95_96_97_98W.pdf)

## Odbiornik

w zasadzie to będzie niemal symetryczny z nadajnikiem, w wypadku wersji do drona trzeba będzie się postarać żeby to możliwie mało ważyło. Tak jak atmega z modułem na stałe wydaje się być słabym wyjściem do nadajnika tak do obiornika może być w sam raz.


## Dalszy rozwój

Istnieje coś takiego jak [Meshstatic](https://meshtastic.org/docs/introduction/) (open source), jest to (z tego co rozumiem) protokół meshowy wykorzystujący (ko by się spodziewał) [LoRa](https://lora-alliance.org/). Można by to wykorzystać do zbudowania roju dronów, o ile przepustowość samych modułów jest w stanie to udźwignąć. 
