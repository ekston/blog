---
title: Zero Trust
date: 2020-03-10
draft: false
tags: 
categories:

---

Man könnte meinen "Zero Trust"-Konzepte seien eine top moderne Modeerscheinung. Ohne jetzt die volle Recherche-Power des Internets zu nutzen, kann ich allerdings sagen, dass diese Konzepte schon seit über zehn Jahren propagiert werden. Google war der erste grössere Implementator.

Auf einen Satz zusammengedampft besteht "Zero Trust" in der ständigen Authentisierung von Anwendern, Anwendungen und Endgeräten.

Als Verfechter von benutzbarer Sicherheit sehe ich hier auch den Grund für den jetzigen Erfolg des Konzepts. Heute sind die Lösungen so einfach zu verwenden, dass Anwender akzeptieren sich ständig anmelden zu müssen. Weil Anwender Anmeldungen in den meisten Fällen gar nicht mitkriegen. Sie melden sich via Biometrie an ihrem Endgerät an. Dieses Endgerät ist fix auf sie zugeteilt und deshalb in Systemen als sichere Anmeldung hinterlegt.

Ist eine Anmeldung trotzdem notwendig ist es deutlich komfortabler als noch von ein paar Jahren. 
Was sag ich vor ein paar Jahren. Gerade letztes Jahr traf ich dieses Zwei-Faktor-Monster an:

{{< figure library="true" src="/img/matrix.png" title="2019 - wirklich" lightbox="false" >}}

Dieses Muster muss ich mir merken und bei jeder Anmeldung wird mir ein neues Sudokudingsbums präsentiert auf welchem ich das Muster durchfahre und dann die entstehende Nummer als PIN eingeben muss. Auch nur toll, wenn man mit Helpdesk-Anrufen Geld verdient. 

Dabei ist die gefürchtete, und von mir in Vergangenheit auch oft wegargumentierte Zweifaktor-Authentisierung inzwischen so einfach. Wir implementieren Microsoft Lösungen und empfehlen dabei meist die Office 365 / Azure Zweifaktor-Authentisierung zu nutzen und sein Mobiltelefon mit "Microsoft Authenticator" und "Push Notifications" zu konfigurieren. Damit hat man statt Gehirnjogging einfach eine Notification welche bestätigt werden muss. Im Extremfall klickt man einfach schnell auf das eigene Handgelenk:

{{< figure library="true" src="/img/tfa_applewatch.png" title="2020 baby" lightbox="false" >}}
