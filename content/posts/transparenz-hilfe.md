---
title: Inventarisierung als Basis für Agilität und Sicherheit
date: 2020-08-13
draft: false
tags: 
categories:

---

Zwei Diskussionen sind weit oben auf der Tagesordnung jeder Informatik - ach generalisieren wir - Unternehmung.

Agilität um auf neue Geschäftsanforderungen reagieren zu können und die Sicherstellung der Informations- und Datensicherheit im Unternehmen.

Glaubt man der Berater- und Artikelschar, muss dazu nur ganz viel neues getan werden um in beiden Themen zu reüssieren. Persönlich halte ich aber eine recht altmodische Disziplin im Bereich Informatik für einen grundlegenden Erfolgsfaktor für beides: Inventarisierung.

Viele Jahre ist es her, da wurde dem jungen Architekten Philip Büchler die Software- und Systemkartographie nahe gebracht. Ein Unding von einem Werkzeug welches man befüttern musste, um seine Projekte in den Betrieb übergeben zu dürfen. Das übelste daran, es waren natürlich auch keine Umsysteme vorhanden die man gar nicht im Projekt einführte. Die Kartographierung respektive Modellierung dieser Systeme war also immer wie das Entwirren des gordischen Knotens. Doch es hat auch einen niederen Ordnungsinstinkt in mir angesprochen. Die Erfassung von Systemen und Abhängigkeiten fing an Spass zu machen. Auch wenn das Werkzeug nicht gerade grossartig war, machte es Spass die Diagramme dann in der Intranet-Publikation zu sehen und zu hoffen es möge der Nachwelt mal hilfreich sein.

Mit steigender Erfahrung wird einem dann auch die Notwendigkeit bewusster. Wie soll man agil auf Herausforderungen reagieren können, wenn man nicht weiss welche Abhängigkeiten davon betroffen sind? Losgelöste Systeme lassen sich sehr rasch verändern. Da steht auch niemand im Weg. Langsamkeit in Organisationen kommt dann, wenn Unsicherheit besteht was alles betroffen ist. Dies führt zu endlosen Diskussionen auf verschiedenen Ebenen, mit verschiedenen Meinung und Perspektiven.

Gleich verhält es sich mit Sicherheit. Da liest man die aktuellste Horrorstory über eine Verwundbarkeit von System XY mit einem Namen der ein Pokemon sein könnte. Und jetzt? Haben wir das im Einsatz? Sind wir davon betroffen? Wenn wir etwas aktualisieren müssen, welche Systeme sind zusätzlich betroffen? Unmöglich herauszufinden wenn keine Inventarisierung besteht. Und nun stellt man sich vor es ist nicht bloss eine Verwundbarkeit sondern sogar ein Angriff? Mit der Panik im Rücken wird man kaum mehr gute Entscheide treffen können wenn Systeme nicht transparent abgebildet sind.

Nun ist die Einführung einer solchen Inventarisierung eine Mammutaufgabe. Die initiale Erfassung ist unglaublich aufwändig. Und dann doch nur der erste Schritt. Denn es gilt die Daten aktuell zu halten. Oftmals treffe ich auf zentrale Architektur- und Sicherheitsabteilungen welche diese Aufgabe dann an Projekte delegieren. Verständliche Schlussfolgerung. Veränderungen an der initialen Erfassung werden in den meisten Fällen durch Projekte veranlasst. Also wird die Dokumentationspflicht ebenfalls dem Projekt aufgelastet. Nichts ist schöner, als einem motivierten Cloud System Engineer mal so ein Kontext-Diagramm zu zeigen und zu sagen, er solle doch jetzt bitte die Kommunikationsflüsse seines Windows 10 Clients dokumentieren. Ich verstehe die Logik, doch beobachte auch immer wieder den Widerstand von Projekten. Dies hat folgende, berechtigte, Gründe:

- Projekte sind latent überlastet. Kaum ein Projekt hat keinen Kosten-, Zeit- oder Ressourcendruck
- Sie kennen zum Zeitpunkt der Konzeption den einzuführenden Gegenstand noch zuwenig um ihn modellieren zu können
- Die Projektmitarbeitenden sind meist nicht direkt in Architektur- oder Sicherheitsmodellierungen involviert und müssten dies noch lernen

In der allseits beliebten Bauanalogie wäre es also würde man dem Maurer sagen er solle doch bitte den Plan zeichnen und die Statik berechnen.

Zwei Massnahmen erachte ich als praktisch und doch zuwenig genutzt:

## Gemeinsame Iterationen

Das Projekt wird regelmässig durch die modellierenden Stellen interviewt. Das ist für beide Seiten ressourcenschonend und lässt es zu, das Modell entsprechenden dem steigenden Kenntnisstand zu entwickeln. Zu Beginn wird wohl die Hypothese modelliert, welche Systeme von der Veränderung betroffen sind. Dann geht man schrittweise weiter und modelliert die neuen Komponenten und Kommunikationsflüsse. Im Laufe dieser Zusammenarbeit wird auch das gegenseitige Verständnis gestärkt und man kann die Ressourcenallokation weiter optimieren. Der sprichwörtliche Maurer kann vielleicht Teile des Plans übernehmen.

## Nutzung von Cloud-Mechanismen

Die Vorteile der Cloud werden mannigfaltig beschrieben. Was ich selber selten höre (oder zugegebenerweisen von mir gebe) ist die Möglichkeit der Transparenzschaffung. Azure beispielsweise hat Inventarisierung im Kern dabei. Beginnt man mit einer seriösen Governance, kann deren Einhaltung laufend überprüft werden. Alle Ressourcen die erstellt oder verändert werden hinterlassen auswertbare Spuren. Beispielsweise der [Azure Governance Visualizer](https://github.com/JulianHayward/Azure-MG-Sub-Governance-Reporting) oder komerzielle Produkte wie [Cloud Discovery](https://docs.servicenow.com/bundle/orlando-it-operations-management/page/product/discovery/concept/azure-cloud-discovery.html) von servicenow bieten Möglichkeiten Bestände zu identifizieren und dann zu modellieren.

{{< figure library="true" src="/img/az-gov-vis.png" title="Screenshot Azure Governance Visualizer" lightbox="true" >}}

Die Cloud dreht unheimlisch schnell. Man fragt sich oft wie man mit diesem Grad der Veränderung mithalten soll. Wie mein ehemaliger CIO im Kontext Mobile Computing mal treffend sagte: Ein paar kluge Köpfe und ein bisschen Methodik haben noch nie geschadet. Dies erinnert mich immer wieder daran vor lauter Veränderung und neuer Begrifflichkeiten die Grundlagen nicht zu vergessen und zu erkennen, wie sie trotz all der Hektik noch oftmals die Basis für den Erfolg sind.
