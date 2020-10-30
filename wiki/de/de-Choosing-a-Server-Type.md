---
layout: wiki
title: "Auswählen eines Servertyps"
lang: "de"
permalink: "/wiki/Choosing-a-Server-Type"
---

# Servertypen

Du kannst einen Server in einem von drei "Modi" betreiben (entweder bei dir zu Hause oder auf einem 3rd-Party-Host):

### 1. Öffentlich
Dein Server wird in der Liste [Zentralserver](Central-Servers) aufgeführt, die Clients standardmäßig verwenden. Die Musiker können dann Ihren Server finden und sich mit ihm verbinden. Du musst keinen öffentlicher Server mehr aufsetzen, da viele andere Personen schon solche Server betreiben. Verbinde dich einfach mit einem Server mit geringer Latenz und beginne zu jammen.

![PublicServer](https://user-images.githubusercontent.com/4561747/79310856-7e0b2100-7ef4-11ea-9511-b2e3339cab6f.png)

Diesen Modus kannst du aktivieren, indem du das Kontrollkästchen "Meinen Server registrieren..." markierst und (optional) deine Serverinformationen eingibst.

Beim Betrieb ohne die Oberfläche ("headless") würde das Folgende einen öffentlichen Server konfigurieren:

~~~
Jamulus --nogui --server \
        --centralserver genreServer:port \
        --serverinfo "yourServerName;yourCity;[country ID]"
~~~

**Anmerkung**: Es ist **nicht** notwendig eine Portweiterleitung in deinem Router einzurichten um einen öffentlichen Server zu betreiben.

Siehe auch [Befehlszeilenoptionen](Command-Line-Options) für weitere Parameter, die du einstellen kannst.


### 2. Privat
Dieser Servertyp wird nicht in einer zentralen Serverliste aufgeführt. Du musst den Musikern deine Serveradresse geben, damit sie sich verbinden können. Auf der Seite zum [Ausführen eines privaten Servers](Running-a-Private-Server) findest du Informationen darüber, was zu tun ist, damit andere sich mit diesem Servertyp verbinden können.

![PrivateServer](https://user-images.githubusercontent.com/4561747/79310944-9f6c0d00-7ef4-11ea-9d8a-ecb0e668c22d.png)

Dieser Modus wird aktiviert, indem du den Haken bei "Meinen Server registrieren..." entfernst.

Beim Betrieb ohne die Oberfläche ("headless") kannst du einen privaten Server wie folgt konfigurieren:

```shell
Jamulus --nogui --server
```

Siehe auch [Befehlszeilenoptionen](Command-Line-Options) für weitere Parameter, die du einstellen kannst.

### 3. Zentral
Die Konfiguration eines Servers als Zentralserver muss nur unter besonderen Umständen (z.B. für Online-Veranstaltungen oder Musikvereine) vorgenommen werden. Die meisten Leute können diesen Typ ignorieren.

Um an einem benutzerdefinierten, zentralen Server registrierte Server anzuzeigen, müssen Musiker die Adresse des Zentralservers in das Einstellungsfeld "Benutzerdefinierter zentraler Server" ihres Clients eingeben. Sie sehen dann die Liste der an diesem zentralen Server registrierten Server.

Ein normaler Server kann sich auch an deinem zentralen Server registrieren, damit ihr Server in deiner Liste angezeigt wird. Dazu müssen sie ihren Server mit dem Flag `--centralserver` und deiner IP/Domain starten.

Der Server, der als zentraler Server konfiguriert werden soll, muss mit `--centralserver localhost` gestartet werden (d.h. der zentrale Server, an dem sich dieser Server anmeldet ist er selbst).

Wenn du steuern möchtest, welche Server sich bei deinem zentralen Server registrieren können, kannst du eine Whitelist mit der Option `--listfilter` aktivieren. Weitere Informationen zu dieser Funktion findest du auf der Seite [Kommandozeilen-Optionen](Command-Line-Options).

Siehe auch [Befehlszeilenoptionen](Command-Line-Options) für weitere Parameter, die Du einstellen kannst.
