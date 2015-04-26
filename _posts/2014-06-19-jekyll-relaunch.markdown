---
layout: post
title:  "Relaunch mit jekyll"
date:   2014-06-18 19:31:01
---

Da ist er, der Relaunch meiner Website. Bisher war sie eine Sammlung von statischen HTML-Seiten. Das ganze war hochgradig unbefriedigend, wenn man sich beruflich Tag für Tag mit Content Management Systemen beschäftigt will man eigentlich Content von Design und Templates trennen. Auf meiner lokalen Maschine hatte ich meine Webseite schon einmal nach TYPO3 6.1 migriert, scheute aber Kosten und Administrationsaufwand des notwendigen Hostingupgrades.

Vor kurzen entdeckte ich dann [jekyll](http://jekyllrb.com/){:target="_blank"}, ein kleines aber feines Ruby-Gem um Blogs und einfache Webseiten aus Markdown-Dateien und unter Verwendung von Liquid-Templates zu generieren. Zusammen mit dem Gem [glynn](https://github.com/dmathieu/glynn){:target="_blank"} war es sogar möglich, auch mit meinem Billo-Webspace bei Hosteurope ohne ssh ein einfaches Deployment via ftp zu realisieren. Danach war nur noch ein Feintuning des jekyll default css und der Templates notwendig um das ganze an meine optischen Erwartungen anzupassen. Praktischerweise ist das css bereits im responsive Design ausgelegt.

In Zukunft kann ich so nicht nur meine Web-Vistenkarte zu den gleichen niedrigen Hostingkosten weiter betreiben, sondern auch um ein einfaches Blog ergänzen.

Die nächsten Schritte in der Zukunft: Das Stylesheet weiter customizen, insbesondere mit dem Blockquote von Code bin ich noch nicht wirklich zufrieden. Zusätzlich git als Versionsverwaltung in das deployment einbinden. Und dann nach und nach meine Bloginhalte von blogspot hierhin migrieren, in diesem Zuge dann noch ein paar zusätzliche Seitentypen für Bildergalerien etc. in den Templates umsetzen. Außerdem müssen gewisse dynamische Elemente (Kontaktformular, Kommentarfunktion) noch durch SaaS/JavaScript-Lösungen ersetzt werden.

Update: Das code-css ist im Bezug auf das Wraping angepasst und die Kommentare mit [Disqus](http://disqus.com) umgesetzt.