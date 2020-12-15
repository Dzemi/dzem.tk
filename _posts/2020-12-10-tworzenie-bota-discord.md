---
layout:     post
comments: true
title:      Jak stworzyć bota discord
date:       2020-12-12 1:00
summary:    Tworzenie bota discord
categories: Bot
thumbnail: zembatka
tags:
 - bot 
 - discord
---

## Pierwsze kroki
Udaj się do portalu botów Discord i stwórz nową aplikację.
<img src="https://i.imgur.com/1BlIs18.png" alt="Obraz">
Będziesz chciał zanotować identyfikator klienta i sekret (oczywiście, że powinieneś zachować tajemnicę).
Jednak to nie jest bot, tylko "Aplikacja". Musisz dodać bota pod zakładką "Bot".
<img src="https://i.imgur.com/qRAU5ih.png" alt="Obraz">
Zanotuj również token i zachowaj go w tajemnicy. W żadnym wypadku nie należy przypisywać tego klucza 
do Github. Twój bot zostanie zhakowany prawie natychmiast.
## Instalacja

Aby uruchomić kod JavaScript poza stroną internetową, potrzebujesz węzła. Pobierz, zainstaluj i upewnij się, że działa w terminalu (lub w wierszu poleceń, ponieważ wszystko to powinno działać w systemach Windows). Domyślne polecenie to "węzeł".

Zalecamy również zainstalowanie narzędzia nodemon. Jest to aplikacja wiersza poleceń, która monitoruje kod twojego bota i automatycznie uruchamia się po zmianach. Możesz go zainstalować, uruchamiając następujące polecenie:

```
npm i -g nodemon
```
Potrzebujesz edytora tekstu. Możesz po prostu użyć notatnika, ale zalecamy Atom lub Visuald Studio Code.

Oto nasz "Hello World":
<img src="https://i.imgur.com/qN6hr72.png" alt="Obraz">

```
const Discord = require('discord.js');
const client = new Discord.Client(); 

client.on ("ready", () => console.log("Zalogowano jako $ client.user.tag!"););

client.on('message', msg => if (msg.content === 'ping') 
msg.reply('pong');); 
 
client.login ("token");
```
Ten kod pochodzi z przykładu discord.js. Złam to.

Pierwsze dwie linie to konfiguracja klienta. Pierwszy wiersz importuje moduł do obiektu o nazwie "Discord", a wiersz 2 inicjuje obiekt klienta.
The ```client.on ("gotowe")``` blok zostanie uruchomiony, gdy bot się uruchomi. Tutaj jest skonfigurowany tak, aby rejestrować jego nazwę na terminalu.
The ```client.on ("wiadomość")``` blok będzie uruchamiany za każdym razem, gdy nowa wiadomość zostanie wysłana na dowolny kanał. Oczywiście musisz sprawdzić treść wiadomości i właśnie to Jeśli blokuje. Jeśli komunikat po prostu mówi "ping", to odpowie "Pong!"
Ostatni wiersz loguje się z tokenem z portalu botów. Oczywiście, token na zrzucie ekranu jest fałszywy. Nigdy nie publikuj swojego tokena w Internecie.
Skopiuj ten kod, wklej token u dołu i zapisz go jako ```index.js``` w dedykowanym folderze.

## Jak uruchomić Bot

Aby uruchomić bota wystarczy wpisać ```node index.js```.

## Jak zaprosić bota
Ta część jest trudniejsza niż powinna być. Musisz wziąć ten URL:
```https://discordapp.com/oauth2/authorize?client_id=CLIENTID&scope=bot```
Zastąp CLIENTID swoim identyfikatorem klienta, znajdującym się na karcie ogólnych informacji na stronie aplikacji. Gdy to zrobisz, możesz podać link do znajomych, aby dodać ich do swoich serwerów.
<img src="https://i.imgur.com/jAo3USG.png" alt="Obraz">

<a href="https://pl.if-koubou.com/articles/how-to/how-to-make-your-own-discord-bot.html">Źródło</a>
