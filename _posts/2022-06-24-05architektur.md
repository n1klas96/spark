---
toc: true
layout: post
description: Beschreibung Architektur
categories: [markdown]
title: Architektur
---
## Projekt-Architektur 
---
### Monolitische Architektur

Innerhalb des Projekts Frunch Infinity wird größtenteils eine monolytische Architektur verwendet. Prinzipiell ist das System mit diversen Komponenten, wie beispielsweise der processing.py, model.py und ui.py miteinander verbunden, voneinander abhängig und nicht, wie in modularen Systemen, lose gekoppelt.
Der Vorteil modularer Systeme im Gegensatz zu einem Monolithen ist, dass einzelne Module losgelöst voneinander verändert werden können. Dies ist in unserem System nicht vollumfänglich möglich. Einige Komponenten wie beispielsweise model.py, erwarten eine bestimmte Vorverarbeitung der Pipeline aus pipeline.py. Werden hier grundlegende Änderungen vorgenomme, müsste model.py ebenfalls angepasst werden. 
Trotzdem hat auch die monolitische Architektur wichtige Vorteil gegenüber einem modularen Aufbau bzw. Microservices. Durch eine monolitische Architektur ist es möglich die Software leichter zu testen, als auch zu debuggen.

### Dokumentation des Systems

Die [Dokumentation](https://dalibor.mitic.pages.web.fh-kufstein.ac.at/se2_project/src) wurde mithilfe von Pdoc erstellt. Dabei werden sämtliche Docstring, welche in den verschiedenen Skripten verwendet wurden, zu einer HTML-Datei zusammengefügt und über GitLab Pages bereitgestellt.
