---
title: Warum in die Cloud?
date: 2020-03-05
draft: false
tags: 
categories:

---

Als Berater/Architekt bei einem Cloud-Dienstleister ist die Frage eigentlich mein täglich Brot: Weshalb verschieben wir Informatik in die Cloud?

Die Frage ist je nach Kunde mehr oder weniger beantwortet. Wenn ich ein bisschen reflektiere komme ich auf folgende Gruppierungen.

{{< figure library="true" src="/img/cloud_drivers.png" title="Treiber für eine Cloud Migration" lightbox="false" >}}

**Gestern - Kosten** Die ersten Cloud Migrationen waren noch sehr stark von versprochenen Kostenvorteilen geprägt. Kaum ein Cloud-Projekt, welches dies nicht als hauptsächlichen Treiber hatte. Die Kostenoptimierungen sollten primär kommen, weil Clouds einerseits tiefere Preise wegen Skalen-Effekten anbieten konnten, sekundär brachte das *pay-per-use* Prinzip aber auch Potentiale Fixkosten einzusparen wenn Dienste nicht dauernd oder mit tiefer Auslastung bezogen werden mussten.

**Heute - Funktionen und Flexibilität** Wenn man heute Cloud Projekte etwas abstrahiert betrachtet ist die Kostenthematik sicher noch eine Hoffnung. Man hat aber auch erkannt, dass die Kostenvorteile der Cloud meist nur mit einer hohen Disziplin genutzt werden. Die Disziplin seine Anwendungen grundlegend zu modernisieren, damit sie auf Services wie Azure Webapps basieren anstatt immer einen kompletten Web- und Datenbankserver zu benötigen. Aber auch die Disziplin sauber abzustecken welche Funktionen zu welchem Zeitpunkt verwendet werden und hier vielleicht etwas Unmut von Anwendern zu ertragen wenn gewisse Funktionen halt nicht zur Verfügung gestellt werden.

Im Vordergrund stehen heute aber oft Funktionalität und Flexibilität. Im Bereich der Anwendungen bietet die Cloud beispielsweise Funktionen die nicht oder nur sehr mühselig auf eigener Infrastruktur zur Verfügung gestellt werden. Ein Beispiel sind "cognitive services" von Azure, wo mit wenig Aufwand Bilder analysiert, Sprache übersetzt oder Texte auf Schlagworte oder emotionalen Unterton untersucht werden. Im Bereich Microsoft 365 sind dies Zusammenarbeitsvorzüge die sich durch Microsoft Teams oder auch künstliche Intelligenz und die geschickte Verknüpfung und Analyse von Signalen ergeben. So zeigt mir Outlook inzwischen potentiell relevante Dokumente zu meinen Terminen im Kalender an.  

**Morgen - Sicherheit** Was heute der grösste Hinderungsgrund für den Sprung in die Cloud ist, wird gemäss meiner Einschätzung in wenigen Jahren der Hauptgrund für die Cloud werden. Sicherheit. Bevor zuviele Leute ihre Fackeln anzünden und mit Heugabeln in meine Richtung losziehen, lasst mich erklären.

Die Sicherheitsarchitektur des geschützten Perimeters ist schon länger unter Beschuss. Mobile Endgeräte, nie sauber ins Unternehmensnetz integriert. App Stores wo Anwendungen geladen werden können die mit geschäftlichen Daten interagieren. "Shadow IT" wo User sich selber Dienste abonnieren und dort Geschäftsaufgaben erledigen die der Unternehmensarbeitsplatz nicht optimal unterstützt. Sie alle pickelten Stein für Stein Löcher in unseren Perimeter.
Der Effekt wird durch den Wunsch nach firmenübergreifender Zusammenarbeit verstärkt. Sei es zur Entwicklung neuer Geschäftsmodelle oder zur Einbindung von Freelancern, die Zusammenarbeit mit externen Stellen ist heute überall eine Anforderung.

Auf der Gefärdungsseite wird der Zugang zu Angriffsmöglichkeiten immer einfacher. Sei es "Ransomware" die mit wenig Aufwand geladen werden kann oder frei verfügbare Anleitungen zur Abfrage von Datenbank-Backups die versehentlich im Internet erreichbar sind. Angreifbar ist heute jeder welcher auch nur einen Computer mit der Möglichkeit von E-Mail hat. Die Gefahr wird auch immer realer. In der Schweiz sind Meldungen über erfolgreiche Angriff mit hoher Tragweite inzwischen im Mainstream angekommen.

Die Situation wird mit dem Mangel von Ressourcen verstärkt. Einerseits sind Mittel knapp und andererseits sind Spezialisten schwer zu finden. Sind sie gefunden treffen sie meist auf so grosse Baustellen, dass die Ressourcen schnell absorbiert sind. Dabei sollten sie zusätzlich noch auf dem aktuellsten Stand der Bedrohungslage und Verteidigungsmöglichkeiten bleiben. Eine schier unlösbare Aufgabe.

Und darauf fusst meine Hypothese. In der Cloud profitiert man von der Erfahrung und den Ressourcen der grössten Firmen. Im mir bekannten Microsoft Umfeld bietet Microsoft Dienste des eigenen "Cybersecurity-Centers" an. Zum einen werden Signale und verdächtige Verhalten auf der weltumspannenden Microsoft Infrastruktur analyisiert und entsprechend bei Kunden verhindert, andererseits bietet man Dienstleistungen wie erfolgreiche Angriffe mitigert und betroffene Systeme wiederhergestellt werden können.
Dies kann kaum eine Firma selbständig in dieser Qualität bieten. 