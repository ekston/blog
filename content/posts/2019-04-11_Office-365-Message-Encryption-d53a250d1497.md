---
title: Office 365 Message Encryption
date: 2019-04-11
draft: false
---

![](https://cdn-images-1.medium.com/max/1200/1*sW6GcCXW5w23iF6OZAkkEQ.png)

Diese Woche gerade von zwei Kunden zum Thema “Office 365 Message Encryption” (OME) befragt worden. Wenn wohl auch zwei Schwalben noch keinen Frühling machen, möchte ich doch etwas zu OME und den Unterschieden zu “Azure Information Protection” (AIP) sagen.

Ein erster Unterschied ist die notwendige Lizenz. Während AIP nur über Microsoft 365, Enterprise Mobility & Security oder einer separaten AIP-Lizenz genutzt werden kann, ist OME bereits in Office 365 E3 enthalten.

OME wird im Exchange Admin Center als “Mailflow rule” konfiguriert. Dabei lässt sich der Schutz entsprechend automatisiert hinzufügen:

![](https://cdn-images-1.medium.com/max/800/1*Q2MACqjzQ8D8y5BzAddunQ.png)

Daneben gibt es auch die Möglichkeit den Anwendern die Möglichkeit zur Verschlüsselung zu geben.

![OME Verschlüsselung in der Outlook Web App](https://cdn-images-1.medium.com/max/1200/1*9g3ZHcvkuRYcU0ixxKpnNg.png)
OME Verschlüsselung in der Outlook Web App

Innerhalb einer Organisation ist der Schutz transparent und Anwender merken nichts von der Entschlüsselung der Nachricht.

Ist der Empfänger extern, erhält er folgende Meldungen:

![](https://cdn-images-1.medium.com/max/800/1*wAY3qccH7N683C0NIq9sSQ.png)
![](https://cdn-images-1.medium.com/max/800/1*g3IgvX9EjsqdWLM0NqDUJw.png)
![](https://cdn-images-1.medium.com/max/800/1*2oc_HpNDBboqJfgU-4F6zQ.png)
![](https://cdn-images-1.medium.com/max/800/1*ISTtGhTm6bI5Ta-hLllXQg.png)

Danach erhält der Anwender einen komplett im Browser stattfindenden Mailclient von Microsoft:

![](https://cdn-images-1.medium.com/max/1200/1*6Rod94FuQwIZ8Zxq-d8MIQ.png)

Hier fangen die Limitationen von OME an. Die Anmeldung ist für externe Empfänger sehr einfach. Das ist einerseits erfreulich, andererseits wäre eine Anmeldung mit Zwei-Faktor wünschenswert.   
Wie man im Screenshot sieht, ist die Verschlüsselung nur auf der E-Mail angewandt. Die Anlage kann problemlos weiter verwendet werden.

AIP ist kompletter auf den Schutz aller Informationen ausgelegt. So können mit AIP sowohl E-Mails als auch Dokumente geschützt werden. Eine Anlage erbt dabei die Klassifikation des E-Mails (ausser das Dokument ist schon höher klassifiziert). Auch komplexere Regeln mit “Azure ActiveDirectory Conditional Access” werden mit AIP möglich. Beispielsweise die Notwendigkeit seinen Account mit Zweifaktor-Authentisierung zu verifizieren bevor auf geschützte Informationen zugegriffen werden kann. Die Handhabung ist dabei für die Anwender sehr ähnlich und wird immer weiter in Office eingebaut.