---

layout: post
title:  "iOS7: Offline Websites"
date:   2013-10-06 19:31:01

---

Heute mal wieder ein Post aus der Reihe praktische Herausforderungen des Arbeitsalltags. Mein Team hat einen HTML5 Prototypen gebaut, inkl. aufwändiger JavaScript Effekte und optimiert für das iPad. Der Kunde wünscht nun diesen Website-Prototypen in internen Runden auch ohne Netzzugang auf dem iPad präsentieren zu können.

Jailbreak-Webserver fallen hier raus und ausgänglich plante ich die Website mittels Dropbox oder Documents von Readdle auf das iPad zu bringen. Beide Lösungen rendern die Site aber nicht sauber. Rund 5 gruselige Offline-Reader aus dem AppStore später kam ich über Googlen und das stets verlässliche StackOverflow auf die richtige Fährte.

Die HTML5 Spezifikation sieht bereits vor über sogenannte Cache Manifest Dateien dem Browser des ausspielenden Devices anzuweisen die dort definierten Teile einer Website lokal zu cachen.

Die Manifestdatei selber wird einfach in der Index.html referenziert.

	<html manifest="cache.manifest">

Die Datei cache.manifest wiederum ist inhaltlich im einfachsten Fall auch übersichtlich und umfasst neben einem Headerteil eine Auflistung der Lokal zu cachenden Dateien, relativ zum Manifest. Wichtig dabei ist die pro Revision der Website eindeutige Versionsnummer und das die Dateidefinition keine Wildcards umfassen darf.


	CACHE MANIFEST
	# Version 201310916251
	CACHE:
	/index.html
	/images/image1.png

Um die Generierung dieses Manifests zu erleichtern habe ich ein kleines Rubyscript geschrieben.


{% highlight ruby %}

#!/usr/bin/ruby -w
t = Time.new
timestamp = t.year, t.month, t.day, t.hour, t.min, t.sec
open('cache.manifest', 'w') do |fo|
  fo.puts "CACHE MANIFEST"
  fo.puts "# Version #{timestamp}"
  fo.puts "CACHE:"
  array = Dir["./**/*"].select{|f| !File.directory? f}
  array.each do |i|
    fo.puts "#{i}".gsub(/^\./, "")
  end
end
{% endhighlight %}


An sich ist damit alles vorbereitet damit der Mobile Safari auf dem iPad beim ersten Aufruf der Website eine lokale Kopie in den Cache schaufelt. Um diese Upzudaten muss der User entweder einen manuellen Reload forcieren oder die Versionsnummer in der cache.manifest inkremiert werden (was das Script über einen Zeitstempel erledigt). Um das ganze schön zu machen wurde in der Index.html noch über das passende metatag auf ein schickes Icon verwiesen und das Ganze kann dann über die entsprechende Funktion des mobile Safari als Bookmark direkt auf den Homescreen abgelegt werden.


Somit war nur noch eine Frage offen: Wie groß darf die Website sein. Apple schweigt sich dazu in seiner Developer Reference aus, im Netz finden sich angaben im Bezug auf iOS6 zwischen 5 und 10MB. Mittels Trial and Error konnte ich ermitteln, dass unter iOS 7 eine Website über die cache.manifest 20MB cachen darf. Geht die Summe der Dateien darüber hinaus wird interessanterweise radikal gar nichts gecacht!

