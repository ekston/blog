---
title: In Microsoft Teams Kanäle umbenennen
date: 2018-11-14
draft: false
---

![](https://cdn-images-1.medium.com/max/1200/1*XNYKxr4pCeAkE2W64iVr1A.png)

Ich wurde angefragt wie man einen Kanal in Microsoft Teams umbenennt. Einfach. Auf die Eigenschaften des Kanals gehen und entsprechenden Kanalnamen anpassen.   
Es wäre aber nicht Office 365 wenn es nicht ein bisschen komplexer wäre.

![](https://cdn-images-1.medium.com/max/1200/1*1UxgDgtyeySMGp4-cvsrUA.png)

Jedes Team hat eine “Office 365 Group” zur Basis. Diese Group hat SharePoint, Teams, Planner, Streams, etc. als Bestandteile.

Und jeder Kanal in Teams entspricht einem Ordner auf SharePoint. In dieser Ordner kommen Dateien, die per “Drag & Drop” im Teams Client hochgeladen werden, etc.

Wird der Kanalnamen nun geändert, bleibt diese Verknüpfung bestehen. Der Ordner heisst allerdings weiterhin wie der Kanal ursprünglich hiess. Vermutlich nicht der gewünschte Zustand. Man könnte versucht sein den Ordner und Kanal (der inzwischen richtig heisst) wieder zu löschen und neu zu erstellen. Das wird nicht gehen, weil Teams reklamiert es gäbe schon einen Kanal mit diesem Namen.   
Papierkorb sei Dank.

Im Papierkorb von Teams können Kanäle aber nur wiederhergestellt werden. Ein Leeren des Papierkorbs, und damit die Freigabe des Kanalnamens, ist nicht vorgesehen.   
Der Kniff ist also den Kanal mit der korrekten Bezeichnung wiederherzustellen. Dann wird der Kanal mit dem falschen Namen umbenannt und danach wieder gelöscht. Nun ist der Kanal mit dem falschen Namen blockiert und der korrekte Namen kann verwendet werden.   
Dann in SharePoint noch den alten Ordner löschen und man hat einen sauberen Zustand.

PS: Natürlich ginge es direkter, wenn man von Beginn weg den Kanal mit dem falschen Namen löscht. Ich denke aber die meisten werden kurz versuchen einen Rechtschreibfehler oder ähnliches zu korrigieren bevor sie den Kanal gleich löschen. Und für diese ist der Artikel :)