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

+ atmega z doklejonym modułem LoRa [link](https://nettigo.pl/products/modul-lora32u4-ii-v1-3-lora-sx1276-i-atmega32u4)
+ nagi moduł LoRa [link](https://techfun.sk/pl/produkt/modu%C5%82-komunikacyjny-sx1276-lora-433-868-915-mhz/), [dokumentacja](https://cdn.sparkfun.com/assets/learn_tutorials/8/0/4/RFM95_96_97_98W.pdf)

### Nadajnik

W wersji minimalnej to będzie arduino i LoRa, ale myślę że fajnie by to było zespolić z raspberry albo czymś podobnym. Dało by to znacznie więcej możliwości szczególnie że po [ELRS](https://www.expresslrs.org/) można wysyłać telemetrie, grzech nie skorzystać.

Firmware
+ [OpenTX](https://www.open-tx.org/)
+ [EdgeTX](https://edgetx.org/about/) *fork OpenTX, ma mieć dotadkowe funkcje i szybszy rozwój*

### Odbiornik

w zasadzie to będzie niemal symetryczny z nadajnikiem, w wypadku wersji do drona trzeba będzie się postarać żeby to możliwie mało ważyło. Tak jak atmega z modułem na stałe wydaje się być słabym wyjściem do nadajnika tak do obiornika może być w sam raz.

Firmware
+ [iNav](https://github.com/iNavFlight/inav) *imo najlepszy na nasze zastosowania* otwarty
+ [ArduPilot](https://ardupilot.org/) *podobno cięższy w ogarnięciu* otwarty
+ [Betaflight](https://betaflight.com/) zamknięty, typowo pod sportowe zastosowania

## Hardware
### preferowany (na ten moment) FC

+ [MATEK H743-WING](https://rcmaniak.pl/pl/p/MATEK-H743-WING-V3-AIO-OSD-H7-Flight-Controller/5071) 7x UARTs, 2x I2C, 1xCAN, 13x PWM outputs, 3x BEC, PDB, current sensor

+ [SpeedyBee F405 V4](https://www.speedybee.com/speedybee-f405-v4-bls-55a-30x30-fc-esc-stack/) 4 x UARTs for your receiver + VTX + camera + GPS

##
[Film](https://www.youtube.com/watch?v=5BfRg9CUMYI&t=552s) gdzie gość robi coś podobnego

## Dalszy rozwój

Istnieje coś takiego jak [Meshstatic](https://meshtastic.org/docs/introduction/) (open source), jest to (z tego co rozumiem) protokół meshowy wykorzystujący (ko by się spodziewał) [LoRa](https://lora-alliance.org/). Można by to wykorzystać do zbudowania roju dronów, o ile przepustowość samych modułów jest w stanie to udźwignąć. 
