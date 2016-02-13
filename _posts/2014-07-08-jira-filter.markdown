---
layout: post
title:  "Erweiterte Vorgangsfilter mit Jira"
date:   2014-07-08 21:45:00
---

Ticketsysteme sind der Freund des Projektmanagers und [Jira](https://de.atlassian.com/software/jira){:target="_blank"} des Herstellers [Atlassian](https://de.atlassian.com){:target="_blank"} mit Sicherheit neben Redmine eine der am weitesten verbreiteten Lösungen. Ich mag an Jira die Möglichkeit Vorgangsfilter auf meine Bedürfnisse zuschneiden zu können ohne erst den Admin involvieren zu müssen. Für einfache Bedürfnisse bietet Jira die Möglichkeit Filter zusammenzuklicken. 

![Jira Basisfilter](/images/blog/jira1.png){:width="50%" height="50%" }


Über den Link "Zu erweitert wechseln" erschließt sich eine mächtige [Abfragesyntax](https://docs.atlassian.com/jira/docs-052/Advanced+Searching){:target="_blank"} welche es ermöglicht erheblich erweiterte Suchabfragen über die im System enthaltenen Tickets laufen zu lassen. 

![Jira Erweiterte Filter](/images/blog/jira2.png){:width="50%" height="50%" }

Die Syntax erinnert an SQL Queries und ermöglicht es zum Beispiel, im Gegensatz zum Basismodus, auch Negationen als Suchparameter zu übergeben. 

{% highlight sql %}

assignee = currentUser() AND status != Closed

{% endhighlight %}

Diese Abfrage zum Beispiel ermöglicht es mir alle Tickets anzeigen zu lassen, die mir zugewiesen und **nicht** geschlossen sind. Der Standardfilter "Meine offenen Vorgänge" unterschlägt nämlich Tickets im Status "Erledigt" (resolved) und ist für mich insofern unpraktikabel, als das meine Teammitarbeiter nach Erledigung das Ticket mir zuweisen damit ich das Ergebnis reviewen und das Ticket anschließend final schließen kann. 

Mit dem Button "Speichern unter" kann man die neue Abfrage unter einem neuen Filternamen speichern und so nicht nur im Issue Navigator (Vorgänge) im Schnellzugriff halten, sondern auch als Widget auf dem Startseiten-Dashboard einbinden.


Ein weiterer für mich nützlicher Filter listet alle Tickets, welche

* Entweder von mir erstellt und noch nicht erledigt wurden sowie auch nicht mir zugewiesen sind...
* ... oder bei denen ich zwar nicht Autor aber Beobachter bin und die nicht mir zugewiesen sowie offen sind.

   
{% highlight sql %}

(resolution = Unresolved AND reporter = currentUser() AND assignee != currentUser()) OR (resolution = Unresolved AND reporter != currentUser() AND assignee != currentUser() AND watcher = currentUser())

{% endhighlight %}



Dieser Filter residiert neben dem oben genannten prominent als "In Arbeit von mir" auf meinem Dashboard und dient mir zum schnellen Überblick darüber, welche meiner Tickets noch im Team in Bearbeitung sind.

Mit diesen beiden Filtern kann man sich schonmal schnell einen Überblick über den Bearbeitungsstand in seinen Projekten verschaffen. Ist man wie ich im Multiprojektmanagement unterwegs kann es zudem Sinn machen bestimmte Projekt verschärft im Blick zu behalten. Dafür schränke ich die Filter auf einzelne Projekt ein, z.B. so

{% highlight sql %}

assignee = currentUser() AND status != Closed AND project = "Projektname"
	
{% endhighlight %}
	
Zuletzt habe ich noch meine Kontrolliste über meine Tickets, die zwar erledigt aber nicht mir zum schließen zugeordnet wurden (wir arbeiten bei uns nicht mit diesbezüglichen automatischen Workflows)

{% highlight sql %}

resolution = Fixed AND status != Closed AND reporter = currentUser() AND assignee != currentUser()

{% endhighlight %}
	
Wie man sieht macht lohnt sich ein bisschen Anpassungsarbeit und spart im Projektcontrolling eine Menge Zeit.


