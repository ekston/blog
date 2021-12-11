---
title: Office Custiomization Tool und eine Empfehlung zum Configuration Management
date: 2019-04-15
draft: false
---

Unternehmen haben beim Umstieg auf moderne Client Verwaltung oftmals Bedenken bei der Anpassung von Office. Klassischerweise werden viele Richtlinien im Office-Paket mitgegeben um es an die Anforderungen der Unternehmen anzupassen.

Dabei gibt es in der modernen Client Verwaltung ein unbekannts Juwel — das “[Office Customization Tool](https://config.office.com/)”. In der Weboberfläche werden die verschiedenen Konfiguration direkt vorgenommen. Diese Konfigurationen werden in einer XML-Datei gespeichert und können beim Setup so mitgegeben werden.

![](https://cdn-images-1.medium.com/max/800/1*M9Q9zbj6hznBAyk_o9IoSA.png)

Schauen wir uns das doch mal näher an. Im Minimum, und dies bietet das Tool schon länger, besteht die Konfiguration aus den Produkten die Office installieren soll (bspw. Access integriert oder nicht, etc.). Dann wählt man die Architektur (32 oder 64bit) und in welcher Häufigkeit die Updates aus welcher Quelle installiert werden sollen.

![](https://cdn-images-1.medium.com/max/1200/1*TpnGzU9rmuc15MWf101FaQ.png)

Danach wird es aber etwas schwieriger. Unter den Einstellungen für die Anwendungen begrüsst einen eine schier nicht enden wollende Liste:

![](https://cdn-images-1.medium.com/max/800/1*5uXJ6BHkdpM-bIyhW9s4Rg.png)

Suchfeld und Tags helfen zielgerichtet zu konfigurieren und seine vermutlich bestehenden Richtlinien in die moderne Welt zu übertragen. Jede Richtlinien ist auch mit einem Hilfetext kurz erklärt:

![](https://cdn-images-1.medium.com/max/800/1*HSO0Q0GbuI5ksrKfiTqaig.png)

### Export und Verwaltung der Konfiguration

Hat man die Konfiguration abgeschlossen, lässt sich die XML-Datei exportieren:

![](https://cdn-images-1.medium.com/max/1200/1*ybwQfGJHehonLTYKOhybMg.png)

Damit hat man aber erst die erste Hälfte des Spiels gewonnen. Die Weboberfläche bietet keine Versionierung oder gemeinsame Bearbeitung. Die XML-Datei muss also anderweitig gesichert und verwaltet werden.

Ich empfehle hierzu ein Werkzeug zur Verwaltung von Sourcecode, wie [Azure DevOps](https://azure.microsoft.com/en-us/services/devops/) oder [Github](https://github.com/). Beide bieten kostenlose Accounts mit genügendem Funktionsumfang an und beide lassen sich viel stärker in allfällig vorhandene Entwicklungs- und Verwaltungsworkflows einbinden.

Ich erstelle für die Verwaltung der Konfiguration ein neues Projekt, in meinem Beispiel in Azure DevOps:

![](https://cdn-images-1.medium.com/max/1200/1*vAsC6gIe9EjUEWvM-CiRsw.png)

In diesem Projekt importiere ich dann die im “Office Customization Tool” erstellte XML-Datei:

![](https://cdn-images-1.medium.com/max/1200/1*D69RZiTG1RKUdXPZujWcnA.png)

Diese Datei ist dann der Master unseres “Codes”. Mittels ebenfalls integriertem “Board” können Aufgaben zur Veränderung des Codes erstellt und zugeteilt werden:

![](https://cdn-images-1.medium.com/max/1200/1*TuOJGZYarx8ycFxHZC3uHA.png)

Die Anpassung an der XML-Datei kann direkt im Browser erfolgen oder wieder im “Office Customization Tool”. Ist man sich die Arbeit mit Code und Versionsverwaltung etwas gewöhnt, hat man vermutlich auch schon andere Werkzeuge mit entsprechender Integration (Visual Studio Code, o.ä.).

![](https://cdn-images-1.medium.com/max/1200/1*AdxkpFEFs6S4W6QADaxb-w.png)

Wird die Aufgabe dann erledigt, hat man eine nachvollziehbare Veränderung an der Konfiguration:

![](https://cdn-images-1.medium.com/max/1200/1*3LVvDeosf8UGPanBTcyh0Q.png)

Diese Konfiguration kann dann in Werkzeuge zur Office-Verteilung integriert werden. Sei dies ganz einfach das [Office Deployment Tool](https://docs.microsoft.com/en-us/deployoffice/overview-of-the-office-2016-deployment-tool) oder bereits ausgereifter Intune:

![](https://cdn-images-1.medium.com/max/1200/1*3Viyyu0inQkR5UiDxXvgJQ.png)

Die Lösung zur Verwaltung der Konfiguration ist noch nicht perfekt, aber schon viel besser als im Büro rumzurufen ob jetzt schon jemand Access aus der Suite genommen hat oder wer die Änderung vorgenommen habe.