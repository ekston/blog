---
title: Dokumente aufgrund vorhandener Informationen kennzeichnen.
date: 2018-10-12T17:39:09.178Z
draft: false
---

Mit Azure Information Protection kann man die Kennzeichnungen (respektive Labels) auch aufgrund von Informationen in SharePoint vergeben. So kann der allfällige Schutz von Dokumenten an MetaDaten verknüpft werden.

Der Microsoft Artikel hierzu findet sich hier:   
[https://docs.microsoft.com/en-us/azure/information-protection/rms-client/client-admin-guide-customizations#label-an-office-document-by-using-an-existing-custom-property](https://docs.microsoft.com/en-us/azure/information-protection/rms-client/client-admin-guide-customizations#label-an-office-document-by-using-an-existing-custom-property)

Ich werde kurz durch den Prozess führen.

### SharePoint

Erst definiere ich die Information die ich in SharePoint vergeben will. In meinem Fall möchte ich eine Auswahl die drei Klassifikationsstufen abbildet:

![](https://cdn-images-1.medium.com/max/800/1*TKMCsPLATLpuds-H7Z9xxg.png)
![Spaltendefinition in SharePoint online.](https://cdn-images-1.medium.com/max/800/1*nUve1R7fMceP0BJxWv3SYA.png)
Spaltendefinition in SharePoint online.

Die Information muss Labelbezeichnungen in MIP/AIP übereinstimmen. Als Standartwert definiere ich “intern”.

In SharePoint kann ich jetzt einfach die definierten Werte abfüllen. Durch die Definition des Standardwerts, erhalten auch alle neuen Dokumente die Information “intern”.

![Definition über Details.](https://cdn-images-1.medium.com/max/800/1*mXFydPEY-MCFSUHKN3dQ_A.png)
Definition über Details.

### Azure Portal

In Azure Information Protection wähle ich jetzt die Policy, welcher ich die Labelvergabe angeben will, und konfiguriere “Erweiterte Einstellungen”:

![](https://cdn-images-1.medium.com/max/1200/1*M7aIEqi2WYqfR_iYKvCEjQ.png)

Die Möglichkeiten sind im Artikel von Microsoft beschrieben. In meinem Fall ist es relativ simpel.

1.  Name: SyncPropertyName — Value: Meine Spaltenbenennung (ClassificationFime)
2.  Name: SyncPropertySate — Value: OneWay

![](https://cdn-images-1.medium.com/max/800/1*fPtz4NTjUeP_rTC6G9llaA.png)

### Office

Wenn ich jetzt Dokumente in Office öffne, sehe ich, dass sie bereits ein Label erhalten haben. Zum Test erstelle ich direkt in SharePoint ein neues PowerPoint Dokument und öffne es dann mit Office 365 ProPlus in dem das Azure Information Protection AddIn aktiviert ist.

![Neues Dokument direkt in SharePoint erstellen.](https://cdn-images-1.medium.com/max/800/1*Qq0fEg4yj0rbxQhbDS-cxQ.png)
Neues Dokument direkt in SharePoint erstellen.![Neue Präsentation in PowerPoint Online erstellen.](https://cdn-images-1.medium.com/max/800/1*2DtsG6ckr6EkWjzXeWEs-A.png)
Neue Präsentation in PowerPoint Online erstellen.![Präsentation in PowerPoint auf dem Notebook öffnen und Label prüfen.](https://cdn-images-1.medium.com/max/800/1*MXLb4-JwvQ7m4TvDQMu46A.png)
Präsentation in PowerPoint auf dem Notebook öffnen und Label prüfen.

### Voila

Diese Möglichkeit macht es einfach vorhandene Metadaten mit Labels zu kombinieren und das alles frei von zusätzlichen Lizenzen\*

Wozu könnte man es nebst der Klassifikation noch benutzen?

\*Azure Information Protection ist ein Lizenzbestandteil von “Enterprise Mobility and Security” oder “Azure Premium P1"