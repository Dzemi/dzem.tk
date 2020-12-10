---
layout:     post
title:      Jak stworzyć bota discord.
date:       2020-12-10
summary:    Tworzenie bota discord.
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

## Font Awesome

If jekyll can't find a corresponding image in your `thumbnail.yml` file then it
will assume you want to use a Font Awesome icon instead. You can find the full
list of Font Awesome icons [here][4].

So for example if your article is about android and you want to use the [android icon][5]
from font awesome you can just specify the following in your frontmatter.

```
thumbnail: android
```

Then in the future if you decide you want to use your own android icon you can just
add it to `_data/thumbnails.yml` which will override it for all articles using
the android thumbnail.

[1]: http://jekyllrb.com/docs/frontmatter/
[2]: http://fortawesome.github.io/Font-Awesome/
[3]: http://imgur.com/
[4]: http://fortawesome.github.io/Font-Awesome/icons/
[5]: http://fortawesome.github.io/Font-Awesome/icon/android/
