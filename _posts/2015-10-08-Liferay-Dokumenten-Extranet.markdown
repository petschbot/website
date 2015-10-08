---
layout: post
title:  "Liferay als Dokumenten-Extranet"
date:   2015-10-08 12:00:00
---

Viele Geschäftsprozesse sind auch im Jahre 2015 dokumentenzentriert. Eine eher transaktionale Abbildung im Web ist ein löbliches Endziel, am Startpunkt eines Digitalen Transformationsprozesses steht aber der häufige Leidensdruck des Dokumentenaustauschs des Unternehmens mit seinen B2B-Kunden. 

Für jeden Kunden werden unzählige Rechnungen, Lieferbestätigungen, Präsentationen und andere Dokumente als PDF-, Excel- oder Worddateien per Mail in stets zu kleine Outlook-Exchange-Postfächer verschickt. Dort gehen Sie dann gerne in der täglichen Mail-Flut unter oder müssen umständlich aus dem Mailprogramm exportiert und auf beiderseitig nur intern zugänglichen Fileservern abgelegt werden. Das alles kostet Zeit, Geld und Nerven.

Aus dem privaten Umfeld kennen Mitarbeiter Webservices wie [Dropbox](https://www.dropbox.com){:target="_blank"} oder [Google Drive](https://drive.google.com){:target="_blank"}. Deren Einsatz verbietet sich aus Gründen der Geheimhaltung aber nicht erst seit dem Scheitern des Safe Harbour Abkommens. Die unabgesprochene und nicht-autorisierte Nutzung solcher Dienste durch die leidgeplagten Mitarbeiter stellt in diesem Kontext ein [permanentes Sicherheitsrisiko](http://www.e-recht24.de/artikel/blog-foren-web20/7115-rechtssicher-in-der-cloud-ihre-daten-bei-dropbox-icloud-google-drivea-co.html){:target="_blank"} dar.

[Liferay](https://www.liferay.com){:target="_blank"} bietet hier mit dem [Document Library Portlet](https://www.liferay.com/de/documentation/liferay-portal/6.2/user-guide/-/ai/getting-started-with-the-documents-and-media-port-12){:target="_blank"} eine Lösung an, welche all diese skizzierten Herausforderungen adressiert und die Erwartungen der Benutzer hinsichtlich der User Experience an ein solches Tools erfüllt. Das Portlet gehört dabei zum Liferay Standard-Lieferumfang.

![Liferay Document Library Portlet](/images/blog/doc_lib1.png){:width="100%"}


Wie alle Portlets eines Liferay-Portals fügt es sich in das [Rollen- und Rechtekonzept](https://www.liferay.com/de/documentation/liferay-portal/6.2/user-guide/-/ai/roles-and-permissions-liferay-portal-6-2-user-guide-16-en){:target="_blank"} ein und ermöglicht es, kunden- oder kundengruppenspezifische Dokumentensammlungen in die jeweiligen [Sites](https://www.liferay.com/de/documentation/liferay-portal/6.2/user-guide/-/ai/leveraging-liferays-multi-site-capabili-liferay-portal-6-2-user-guide-02-en){:target="_blank"} innerhalb des Portals zu integrieren. Dabei kann je nach Nutzungsszenario definiert werden, ob nur die eigenen Mitarbeiter Dokumente hochladen können oder ob dies im Sinne der bilateralen Dokumentenverwaltung auch dem authentifizierten externen Nutzer möglich sein soll. Die Dokumente selber können bequem über die Weboberfläche des Portals per Drag & Drop aus dem Windows Explorer oder OSX Finder hochgeladen werden. Die autorisierten Nutzer der Dokumentensammlung können dabei selber bestimmen, ob sie über neue oder geänderte Dokumente per Mail informiert werden möchten.

![Liferay Document Library Portlet Document Categories](/images/blog/doc_lib2.png)

In der Dokumentenablage ist es möglich, jenseits einer frei strukturierbaren Ordnerhierarchie verschiedene Dokumentenkategorien zu definieren, zum Beispiel “Angebote” oder “Forecast”. Zusammen mit der sehr leistungsfähigen [Suchfunktion](https://www.liferay.com/de/documentation/liferay-portal/6.2/user-guide/-/ai/searching-for-content-in-liferay-liferay-portal-6-2-user-guide-06--3){:target="_blank"}, welche auch Dokumenteninhalte indexiert, ergibt sich auch in sehr großen Dokumentensammlungen eine optimale Wiederauffindbarkeit von einzelnen Dokumenten. 

![Liferay Document Library Portlet Document Download](/images/blog/doc_lib3.png){:width="40%"}

Der Download der Dokumente erfolgt direkt über das Portal. Es ist dabei auch möglich, vergleichbar zu Dropbox und Google Drive, für einzelne Dokumente Download-Links zu erzeugen um diese per Copy & Paste in eine Mail einzufügen. In der Standard-Konfiguration fragt Liferay nach dem Klick auf einen solchen Link die Logindaten des Benutzers ab, um einen autorisierten Zugriff sicherzustellen. Das für Unternehmen zu kurz greifende standardmäßige Security through Obscurity-Konzept des URL-Sharings von Dropbox [0] wird somit effizient unterbunden.

Liferay importiert bereits die gängigen Microsoft Office-Metadaten und ermöglicht es, eigene [Metadatenfelder zu definieren](https://www.liferay.com/de/documentation/liferay-portal/6.2/user-guide/-/ai/document-types-and-metadata-sets-liferay-portal-6-2-user-guide-05-en){:target="_blank"} - und zwar pro Dokumentenkategorietyp eigene Sets - und während des Uploads über die Weboberfläche zu befüllen. So ist es zum Beispiel möglich, auch hausinterne Aktenzeichen-Kategorisierungen und Vorgangsnummern im Portal abzubilden. 

![Liferay Document Library Portlet Document Versions](/images/blog/doc_lib4.png){:width="50%"}

Die Möglichkeit zur Versionierung einzelner Dokumente beendet das Chaos der Versionsverwaltung über Dateinamen ala Konzept_V1.2_Final_Freigabe2.docx. Für jedes Dokument kann eine neue Version hochgeladen werden, zugleich bietet Liferay die vergangenen Versionen in der Versions-Historie zum Download an. Dabei unterstützt Liferay auch aus Dokumenten Management Systemen bekannte Funktionen wie Check-In und Check-Out-Prozesse um Dokumente zur Überarbeitung zu sperren sowie damit verbundene Dokumentenstati (Entwurf, Final). In Kombination mit einem frei definierbaren Rollenkonzept und anpassbaren Workflows lassen sich so auch mehrstufige Freigabeszenarien direkt im Portal realisieren.

![Liferay Document Library Portlet WebDAV](/images/blog/doc_lib5a.png){:width="75%"}

Neben dem Zugriff über das Webinterface des Portals ist es auch möglich, das Document Library Portlet via [WebDAV](https://www.liferay.com/de/community/wiki/-/wiki/Main/Accessing+the+Document+Library+with+WebDAV){:target="_blank"} zu adressieren. Auch hier erfolgt die Authentifizierung über die Portal-Logindaten. Dies ermöglicht es, spezifische Document Libraries in den gängigen Betriebessystemen, ähnlich einem Netzwerklaufwerk, in den Dateimanager des Benutzers einzubinden. Der Mitarbeiter kann nun seine Dokumente direkt aus der Textverarbeitung heraus im Portal ablegen und dort auch wieder öffnen. Der Check-In und Check-Out der Dokumente erfolgt dabei ebenso automatisch wie die Versionierung des einzelnen Dokuments. Mit [Liferay Sync](https://www.liferay.com/de/documentation/liferay-portal/6.2/user-guide/-/ai/liferay-sync-liferay-portal-6-2-user-guide-05-en){:target="_blank"} steht zudem eine diesbezügliche App für Windows, Mac, Android und iOS bereit. Liferay Sync vereinfacht die Einrichtung dieses Zugriffs erheblich und stellt auch Möglichkeiten zur Offline-Synchronisation von Dateien bereit, was gerade den Erfordernissen von Außendienstmitarbeitern entgegen kommt.

Technisch betrachtet persistiert die Liferay Document Library die Dokumente standardmäßig im Dateisystem des Servers und weiß auch ggf. betriebssystemseitig bestehende Beschränkungen - zum Beispiel hinsichtlich der maximalen Dateianzahl pro Ordner - transparent zu kompensieren. Es ist aber konfiguratorisch auch möglich, die Dokumente in einem Jackrabbit Content Respository nach JSR-170, einem CMIS-Respository oder einem Amazon S3 Bucket zu persistieren.

Zusammenfassend bietet Liferay mit dem Document Library Portlet genau die Funktionen welche sich Mitarbeiter wünschen, um Kunden Dokumente bereitzustellen und systematisch zu verwalten. Die User Experience entspricht dabei aus dem Privatbereich bekannten Lösungen wie Dropbox. Aufgrund der funktionalen Tiefe, inklusive Versionierung, Check-In/Check-Out und Workflows, muss sich Liferay auch hinter spezialisierten Lösungen wie [Alfresco](https://www.alfresco.com/de/products/enterprise-content-management/community){:target="_blank"} nicht verstecken. Gegenüber [Owncloud](https://owncloud.org/){:target="_blank"} differenziert sich Liferay durch seine Java-Applikationsbasis und seine weiteren Portal-Funktionalitäten, welche Thema in folgenden Blogbeiträgen sein sollen.


[0] Der Vollständigkeit halber sei erwähnt, dass Dropbox Pro einen Password-Schutz von Download-Links ermöglicht.

(Dieser Blogpost ist Teil meiner Reihe [Liferay als Plattform für Digitale Transformation]({% post_url 2015-10-07-Liferay-Digitale-Transformation %}). Alle inhaltlichen Darstellungen beziehen sich auf die Version Liferay 6.2 EE, die Optik der Screenshots ist durch ein kundenspezifisches Theme bestimmt)


