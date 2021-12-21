---
title: Microsoft Information Protection - wirklich verschlüsselt?
date: 2021-12-21
draft: false
---

Wie sehe ich denn ob ein Dokument wirklich verschlüsselt ist, wie es Microsoft behauptet? Word kann mir ja viel erzählen. 

Ein Office Dokument ist ja eigentlich nicht viel anderes als ein ZIP-Archiv mit XML Informationen. Sehen wir uns dieses unverschlüsselte Dokument an, sehen wir in Preview den Blindtext den Word bei Eingabe von =rand(5,50) generiert. 

{{< figure library="true" src="/img/preview.png" lightbox="false" >}}

Öffnen wir dieses File in BBEdit, oder bei Windows über die Umbenennung in .zip, sehen wir den Inhalt in der Ordnerstruktur als XML Datei

{{< figure library="true" src="/img/xml-content.png" lightbox="false" >}}

Die verschlüsselte Datei können wir schon gar nicht auf diesem Weg öffnen. Hier müssen wir die Datei in .zip umbenennen und können uns dann den verschlüsselten Gibberish ansehen:

{{< figure library="true" src="/img/gibberish.png" lightbox="false" >}}

In Windows, mit dem Umweg über 7zip sehe ich wenigstens noch ein bisschen Struktur, aber auch keinen effektiven Inhalt. Verschlüsselt, halt. 

{{< figure library="true" src="/img/7zip.png" lightbox="false" >}}
