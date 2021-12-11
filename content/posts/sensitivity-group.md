---
title: Sensitivity Labels für Microsoft Teams
date: 2020-04-27
draft: false
tags: 
categories:

---

Als SBB 2018 Microsoft Teams fürs ganze Unternehmen einführte, hatte man mittels PowerShell Magie zwei verschiedene Arten Teams erstellt. Teams für vertrauliche Dokumente und Teams für maximal intern klassifizierte Dokumente. Diese Einstellung hatte unter anderem zur Folge ob externe Gäste hinzugefügt werden konnten oder nicht. Eine der Säulen der Microsoft 365 Sicherheit ist nämlich der Umgang mit Externen.

Heute ist dies im Standardumfang von Microsoft 365 enthalten und ich möchte kurz zeigen wie man es macht.

Die notwendige Einstellung befindet sich im [Microsoft 365 Security Center](https://security.microsoft.com/sensitivity?viewid=sensitivitylabels). Darin erstellt man für sein Unternehmen die Klassifikationsbezeichnungen. In meinem Entwicklungs-Tenant sind dies simpel "Extranet", "Intern" und "Vertraulich". Darin hinterlegt sind die entsprechenden "Group settings".

{{< figure library="true" src="/img/sensitivity1.png" title="Sensitivty labels" lightbox="true" >}}

Wie äussert sich das jetzt in der Praxis? Lass es uns ausprobieren. Ob alle User die Möglichkeit haben Teams zu erstellen, ist eine der Kernfragen jeder Teams-Einführung. Ich rate oft zu einer zwischengeschalteten Provisionierung, Microsoft rät zum Standard. Belassen wir es auf dem Entwicklungs-Tenant also im Microsoft Standard und alle User haben die Möglichkeit im Teams Client neue Teams zu erstellen.

{{< figure library="true" src="/img/sensitivity5.png" title="Neue Teams in Teams erstellen" lightbox="true" >}}

Die Einstellung der Vertraulichkeit für Teams ist eher gut versteckt, wenn kein roter Pfeil darauf hinweist.

{{< figure library="true" src="/img/sensitivity7.png" title="Einstellung der Vertraulichkeit" lightbox="true" >}}

Machen wir zur Demonstration also ein Extranet- und ein internes Team.

{{< figure library="true" src="/img/sensitivity9.png" title="Erstellung eines Extranets" lightbox="true" >}}

Wenn in diesen Teams jetzt Gäste hinzugefügt werden sollen, funktioniert es im Fall des Extranets, im Fall des internen Teams scheitert die Auflösung einer E-Mail-Adresse allerdings.

{{< figure library="true" src="/img/sensitivity17.png" title="Gast hinzufügen" lightbox="true" >}}

Nicht besonders aussagekräftig wenn die Auswahl der Klassifizierung nicht unmittelbar vorher geschehen ist. Damit dies etwas weniger verwirrend ist, kann in den Labels auch eine Beschreibung hinterlegt werden die sich im "mouseover" offenbart.

{{< figure library="true" src="/img/sensitivity18.png" title="Erklärung der Klassifikation" lightbox="true" >}}

Diese Klassifikation zieht sich durch die gesamte Office 365 Group, und ist somit auch in SharePoint ersichtlich.

{{< figure library="true" src="/img/sensitivity19.png" title="SharePoint Klassifikation" lightbox="true" >}}

Alles schön und gut. Doch aus Sicherheitssicht kommt jetzt die Krux. Jeder Team-Owner kann diese Einstellung natürlich rasch ändern. Man macht aus dem internen Team rasch ein Extranet, lädt Gäste ein und stellt es zurück auf Intern. Diese Konfiguration hat keinen Einfluss auf die User und ein externer Gast bliebe drin. Leider hinterlässt die Aktion auch keine sinnvoll auswertbaren Log-Einträge und damit ist es schwer zu überprüfen. [Cloud App Security](https://portal.cloudappsecurity.com/) bietet auch (noch) keine dedizierte Policy um dieses Verhalten zu stoppen oder darüber zu alarmieren. Lediglich eine Kontrolle über Gäste oder Hinzufügen oder Entfernen des Sensitivity Labels ist einfach möglich. Ich hoffe hier wird noch nachgebessert oder ein findiger Spezialist findet eine gute Möglichkeit die ich übersah.
