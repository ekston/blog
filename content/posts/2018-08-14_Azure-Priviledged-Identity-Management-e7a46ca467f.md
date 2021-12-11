---
title: Azure Priviledged Identity Management
date: 2018-08-14T09:33:24.288Z
draft: false
---

![](https://cdn-images-1.medium.com/max/800/1*p0oyGlyD7LoKad9vwUIwBA.png)

Beim Einsatz von Office 365 benötigt es verschiedene Administrationsrollen. Als allererstes wird ein “Global Admin” angelegt. Der Über-Admin der alles konfigurieren und verändern kann. Diese Rolle möchte man sorgfältig vergeben. Mit steigender Aufgabenlast, wird aber auch diese Rolle auf mehrere Personen verteilt.

Nebst den Systemunabhängigen Mechanismen wie Adminrechte nie auf seinem Arbeitsuser zu tragen sowie so wenig Admins wie nötig zu berechtigen, gibt es weitere Wege.

Microsoft arbeitet laufend daran die Notwendigkeit der “Global-Admin”-Rolle zu reduzieren. So musste ich zu Beginn meiner Office 365 Tätigkeit bereits Global Admin sein um den “Conditional Access” einzurichten. Inzwischen gibt es hierzu den dedizierten “Conditional Access”-Admin.

Mehrere und granularere Admin-Rollen ist der eine Weg den man gehen sollte. Zeitlich beschränkte und an einen Prozess gekoppelte Rollenvergabe ist der andere den man prüfen sollte.

In Azure und Office 365 wird dieser Weg mit “Azure Priviledged Identity” (fortan PIM genannt) beschritten. Die Funktion ist einfach eingerichtet und bietet ein höheres Mass an Sicherheit, denn:

*   Administratorenzugriffe temporär
*   Die Rollenvergabe kann an alle Admins kommuniziert werden.
*   Die Rollenvergabe wird auditierbar.
*   Die Rollenvergabe kann hinter einen Genehmigungsprozess gestellt werden.
*   Die Rollenvergabe muss begründet werden und kann sogar die Eingabe einer Ticket-Nummer fordern. Diese Ticket-Nummer ist nicht technisch verknüpft, sondern kann lediglich in der Genehmigung oder Auditierung überprüft werden .

So wäre selbst bei Identitätsdiebstahl eine weitere Hürde eingebaut um sämtliche Daten oder Konfigurationen zu komprimitieren, da erst PIM aktiviert werden müsste.

#### Notwendige Konfiguration

Nach grundsätzlicher Einrichtung von PIM werden die Mitglieder pro Rolle definiert. Dabei kann entschieden werden, ob die Rolle permanent vergeben wird oder ob sich ein Mitglied die Rolle in PIM zuteilen muss.

![Vergabe der Rollen an Personen.](https://cdn-images-1.medium.com/max/800/1*WpFPlgy4CqEFjz7Uru3W5g.png)
Vergabe der Rollen an Personen.

Für jede Rolle können diverse Einstellungen vorgenommen werden.

![Einstellungen für den Conditional Access Administrator](https://cdn-images-1.medium.com/max/800/1*4N_Kw4ODKNuWUk2CU4Aqug.png)
Einstellungen für den Conditional Access Administrator

Es kann eingestellt werden, wie lange die Aktivierung gültig ist, ob alle Admins über die Vergabe informiert werden sollen, ob die Eingabe eines Tickets notwendig ist und schlussendlich ob die Vergabe genehmigt werden muss.

Ich empfehle hier die Differenzierung der Konfiguration. Einen “Reports Reader” kann man länger aktiviert lassen (1–72h) als den “Global Admin”. Auch will man vielleicht einen “Guest Inviter” nicht zwingend genehmigen während dies beim “Conditional Access”-Admin vielleicht Sinn macht.

#### Lizenzierung

Die Funktion ist wertvoll und sehr gut gelöst. Das weiss auch Microsoft und lässt sie sich entsprechend bezahlen:

![via [https://docs.microsoft.com/en-us/azure/active-directory/privileged-identity-management/pim-configure](https://docs.microsoft.com/en-us/azure/active-directory/privileged-identity-management/pim-configure)](https://cdn-images-1.medium.com/max/800/1*vGcKbete8ByYdM9zXC_WHQ.png)
via [https://docs.microsoft.com/en-us/azure/active-directory/privileged-identity-management/pim-configure](https://docs.microsoft.com/en-us/azure/active-directory/privileged-identity-management/pim-configure)

Da können in grösseren Office 365 Installationen schon einige User zusammenkommen die Azure AD Premium P2 (Listenpreis [$9 user/month](https://azure.microsoft.com/en-us/pricing/details/active-directory/)) oder EMS E5 (Listenpreis [$14.80 per user /month](https://www.microsoft.com/en-us/cloud-platform/enterprise-mobility-security-pricing))

Wie bei vielen Lizenzoptionen im Office 365 Umfeld ist die Prüfung der Lizenz nicht technisch, sondern vertraglich umgesetzt. Man kann die Funktion unlizenziert nutzen, darf aber nicht.

#### Empfehlungen

Ich empfehle die Funktion auszurollen. Die Lizenzkosten stehen in keinem Verhältnis gegenüber den Risiken die bei Fehlmanipulation oder Missbrauch von Adminrechten entstehen können. Ausserdem könnten die Lizenzen schon aus anderen Gründen im Haus vorhanden sein (gerade EMS bietet ja noch viel mehr als Azure AD Premium).

Bezüglich der Adminrollen gilt es die Wichtigkeit und die Häufigkeit abzuwägen. Je “mächtiger” eine Admin-Funktion, desto restriktiver der Zugriff. Je häufiger die Funktion notwendig ist, desto tiefer die Einstiegshürde für den Zugriff. Folgende Beispiele als Leitfaden:

*   **Global Admin**: Die mächtigste aller Rollen sollte nie permanent getragen werden. Wird hier aber Arbeit übernommen, kann die Arbeit durchaus zeitintensiv sein. Daher kann die Rolle gut einen Arbeitstag vergeben werden. Genehmigt oder nicht hängt stark von der Service-Organisation ab. Man will die Störungsbehebung am sprichwörtlichen Freitagabend evt. nicht von einer Freigabeperson abhängig machen.
*   **Reports Reader:** Diese Rolle berechtigt zum Zugriff auf Nutzungszahlen von Office 365. Sie ist damit auch interessant für nicht technische Funktionen wie Produktmanager, Management oder Projektleiter. Nebst der Privatssphärenüberlegungen gibt es wenig Risiken, die Rolle kann also durchaus permanent vergeben werden.
*   **Guest Inviter:** An jeder Ecke können in Office 365 Gäste eingeladen werden. Dies ist Fluch und Segen zugleich. Je nach Umgang damit empfehle ich die Handhabung der Rolle. Dürfen alle Mitarbeitenden Gäste einladen bringt PIM nur geringen Mehrwert aber hohen Schulungsaufwand (und Lizenzkosten). Ist man restriktiv in Benutzergruppen, hilft PIM mit Nachvollziehbarkeit.
*   **Conditional Access Admin**: An der Funktion wird man nicht täglich rumschrauben. Manipulationen am Conditional Access können aber erheblichen Einfluss auf die Arbeit der Anwender haben. Diese Rolle würde ich also sogar genehmigen lassen mit Bezug auf ein Ticket welches die geplante Manipulation erklärt.