---
title: Der Weg in die Cloud ist ein Weg voller Unsicherheiten.
date: 2018-04-19T14:40:59.575Z
draft: false
---

{{< figure library="true" src="/img/o365_sicherheit.png" title="" lightbox="true" >}}

Der Weg in die Cloud ist ein Weg voller Unsicherheiten. Hat man die grundlegenden Überlegungen zu Datenhaltung, interner Governance und gesetzlichen Rahmenbedingungen einmal gemacht, hilft einem Microsoft in der Absicherung von Office 365 hervorragend weiter.

Als Enterprise Architect war ich bei unserem Weg in die “_public cloud_” von Microsoft, unter anderem für die Absicherung unserer Informationen zuständig. Hier möchte ich nicht erläutern was wir gemacht haben (vielleicht später), sondern was wir einfacher hätten machen können und dabei auf vielleicht weniger bekannte Hilfsmittel verweisen.

### Information Protection Poster

![Poster mit Hinweisen, Einschätzungen und Werkzeugen](https://cdn-images-1.medium.com/max/800/0*JDVeD2H14_TOZIi5.png)
Poster mit Hinweisen, Einschätzungen und Werkzeugen

[In einem Poster](https://blogs.technet.microsoft.com/solutions_advisory_board/2017/03/30/updated-information-protection-poster-for-office-365/) wird einfach dargelegt welche verschiedenen Sicherheitsstufen es gibt, welche Werkzeuge helfen diese Stufe zu erreichen und wo man diese Werkzeuge allenfalls testen kann.

![Beispiel einer Sicherheitsstufe.](https://cdn-images-1.medium.com/max/600/1*LAtt6oRDXWtjGaB9qoEwWw.png)
Beispiel einer Sicherheitsstufe.![Hinweis auf die Möglichkeiten ein Werkzeug zu testen.](https://cdn-images-1.medium.com/max/600/1*UefEHF7HRSpv8bycZr5tEA.png)
Hinweis auf die Möglichkeiten ein Werkzeug zu testen.

Mit einer kurzen Beschreibung, Links auf weiterführende Informationen und - in der bisweilen verwirrenden Lizenzierung von Office 365 auch sehr wertvoll- Lizenzen die notwendig sind um das Feature zu nutzen.

Auch interessant ist die Möglichkeit ein Feature zu testen. So ist einer der Vorteile einer “_public cloud_”, dass sofort ein weiterer Tenant erstellt werden kann in dem Dinge ausprobiert werden können ohne seine eigenen Umgebungen nutzen zu müssen. Natürlich ist dies nicht immer praktikabel, wenn Integrationen notwendig sind. Für alleinstehende Werkzeuge aber sicher hilfreich.

### Secure Score

![](https://cdn-images-1.medium.com/max/600/1*zKm8-TdyETxkrXNCAbipGA.png)

Wie sicher ist denn jetzt die eigene Office 365 Umgebung? Diese Frage kann der Secure Score teils beantworten. [Aktuell auch um die Sicherheit von Windows erweitert](https://techcommunity.microsoft.com/t5/Security-Privacy-and-Compliance/Office-365-Secure-Score-is-now-Microsoft-Secure-Score/ba-p/182358), kann man unter [securescore.microsoft.com](https://securescore.microsoft.com) nach einem Login seine eigene Einschätzung einsehen. Was anfangs schockieren kann, wird durch einen Vergleich mit Tenants der selben Grösse oftmals relativiert:

Nebst der reinen Bewertung wird einem aber auch aktiv mit der Verbesserung der Punktzahl geholfen. Mittels Zielpunktzahl werden mögliche Massnahmen vorgeschlagen:

![](https://cdn-images-1.medium.com/max/800/1*4kK3imGFWFsl0v_jB_Colg.png)

Diese Übersicht bietet weitere Informationen zur Gefährdung und zum Schutz, sowie in diesem Beispiel die betroffenen Accounts und direkt den Link zum Adminportal wo die Aktion umgesetzt werden kann:

![](https://cdn-images-1.medium.com/max/800/1*sBSr-B8DU_beSKJAg8mzJA.png)

### Service Trust Portal

Nach soviel “Gamification” kommen wir zu etwas trockenerem. Compliance und Gesetze. Mit Inkrafttretung des europäischen Datenschutzgesetzes GDPR werden viele Firmen ihre IT-Infrastrukturen und Prozesse unter die Lupe genommen haben. Microsoft bietet hier ein Werkzeug zur Einschätzung der Erfüllung.

Das [Service Trust Portal wird von Microsoft gut beschrieben](https://techcommunity.microsoft.com/t5/Security-Privacy-and-Compliance/Announcing-Compliance-Manager-general-availability/ba-p/161922) und hilft effektiv Massnahmen zu identifizieren und zu tracken. Hierbei werden Prüfschritte erklärt und es können Zuständigkeiten verteilt und Prüfprotokolle hochgeladen werden. Es ist weniger “interaktiv” als der Secure Score, hilft aber als Guideline sicherlich weiter.

Das waren drei kurze Tipps zu mehr Sicherheit in O365. Als nächstes werde ich wohl über meinen Liebling den “Conditional Access” schreiben und weshalb er dazu führt, dass ich alle Browser/Clients auf englisch einstelle ;)