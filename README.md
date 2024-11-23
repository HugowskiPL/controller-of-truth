# Pilot ostateczny

## Założenia:
Generyczny polot *o niepojętej mocy* mający służć za kontroler do czegokowiek, działający z równie generycznym odbiornikiem.

Wstępnie wybór padł na wykorzystanie modułów [LoRa](https://lora-alliance.org/), ze względu na dość dobre właściwości i niskie koszta

### Tak ja to sobie wyobrażam
![zaiste potężny pilot](https://a.allegroimg.com/s512/11b53a/f7985157427ab788c5b41778c997/Rozdzielacz-do-zurawia-HDS-sterowanie-radiowe-SCANRECO-pilot-z-joystickami-Numer-katalogowy-czesci-1122)

## Komunikacja

Cały pomysł urodził się na bazie [ExpressLRS](https://www.expresslrs.org/) który ma służyć jako protokół do kontrolowana dronów (nie tylko latających) w czasie rzeczywistym. Z tego co widziałem wspiera telemetrie (i jest open source)

LoRa przewiduje nadawanie na 433MHz *(ELRS nie wspiera)*, 868MHz, i 2,4GHz.
Na potrzeby takiego pilota najlepsze powinno być pasmo 868MHz, da ono dość dobry zasięg (poniesie może z 2 km w mieście)
>[!IMPORTANT]
>Fajnie było by dorwać kilka takich modułów i zrobć rzeczwyiste pomiary jaki zasięg będzie to w stanie wyciągnąć.

atmega z doklejonym modułem LoRa [link](https://nettigo.pl/products/modul-lora32u4-ii-v1-3-lora-sx1276-i-atmega32u4)

nagi moduł LoRa [link](https://techfun.sk/pl/produkt/modu%C5%82-komunikacyjny-sx1276-lora-433-868-915-mhz/), [dokumentacja](https://cdn.sparkfun.com/assets/learn_tutorials/8/0/4/RFM95_96_97_98W.pdf)

### Nadajnik

W wersji minimalnej to będzie arduino i LoRa, ale myślę że fajnie by to było zespolić z raspberry albo czymś podobnym. Dało by to znacznie więcej możliwości szczególnie że po [ELRS](https://www.expresslrs.org/) można wysyłać telemetrie, grzech nie skorzystać.

>[!IMPORTANT]
>Z tego co widze to ELRS nie jest całkowicie samodzielny i działa z dodatkowym sofrwarem

[OpenTX](https://www.open-tx.org/) *soft do nadajnika?*
[Betaflight](https://betaflight.com/) *soft odbiornika*

>Prerequisites
>You should be comfortable navigating through your Radio Handset firmware (OpenTX/EdgeTX) and setting up models, as the guide on this website mainly covers setting up your radio for you to be able to use ExpressLRS.
>Likewise, you should also be comfortable with your Flight Controller firmware (Betaflight, INAV, etc), as the guide only covers setting up your ExpressLRS receiver to work with your flight controller firmware.

### Odbiornik

w zasadzie to będzie niemal symetryczny z nadajnikiem, w wypadku wersji do drona trzeba będzie się postarać żeby to możliwie mało ważyło. Tak jak atmega z modułem na stałe wydaje się być słabym wyjściem do nadajnika tak do obiornika może być w sam raz.

##
[Film](https://www.youtube.com/watch?v=5BfRg9CUMYI&t=552s) gdzie gość robi coś podobnego

## Dalszy rozwój

Istnieje coś takiego jak [Meshstatic](https://meshtastic.org/docs/introduction/) (open source), jest to (z tego co rozumiem) protokół meshowy wykorzystujący (ko by się spodziewał) [LoRa](https://lora-alliance.org/). Można by to wykorzystać do zbudowania roju dronów, o ile przepustowość samych modułów jest w stanie to udźwignąć. 
