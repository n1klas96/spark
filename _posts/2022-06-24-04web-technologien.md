---
toc: true
layout: post
description: Systemansprache
categories: [markdown]
title: Web - Technologien
---
## Web-Technologien von Frunch Infinity
---


### Streamlit

Die Ergebnisse des Projekts bzw. des Auto-ML-Prozesses werden innerhalb einer Streamlit Applikation visualisiert. Diese wird wiederrum von Streamlit Cloud 
gehostet und ist somit öffentlich zugänglich. Durch Streamlit ist es einerseits sehr schnell möglich Ergebnisse anschaulich dazustellen, aber auch sie in einem relativ leichten Prozess durch GitHub und Streamlit Cloud zu deployen.

### SQL-Alchemy (Data Warehouse)

Durch SQL-Alchemy stellen wir unserem System ein Data Warehouse bereit, in dem einerseits die Trainingsergebnisse unseres Modells abgespeichert und dementsprechend auch abgefragt werden können. Zudem wird das Target Feature, welches in der Streamlit-Applikation auswählbar ist, ebenfalls im Data Warehouse abgelegt.

### PyCaret

Durch die Hilfe von PyCaret werden insgesamt 17 verschiedene Modelle trainiert und im Anschluss mit Hilfe verschiedener Metriken verglichen. Der ausgegebene Data Frame wir nach Beendigung des Trainings in der Streamlit App dargestellt

### Poetry

Innerhalb der Projektorganisation nutzen das Package Management System von Poetry. Innerhalb des poetry.lock files werden sämtliche Paket Requirements gelistet. Durch Poetry arbeiten alle Entwickler auf den gleichen Versionsebenen der verschiedenen Pakete.

### Hydra

Als Pfad-Management-Tool verwenden wir das Framework von Hydra. Durch Hydra ist es möglich beispielsweise den Daten-Pfad einmal zentral in config (main.yaml) festzulegen und diesen Ort durch den decorator von hydra überall anzusprechen. Sollte sich der Ort irgendwann ändern, kann dies zentral an einem Ort erfolgen

### Cookiecutter

Für die Organisation und die Strukturierung des Projekt Repositorys haben ein Template von Cookiecutter verwendet. Auch wenn nicht alle Vorlagen des Templates verwendet wurden, hat dies bei der Übersichtlichkeit des Projekts geholfen

### Comit Control 

Durch die .pre-commit-config-yaml werden in einige Richtlinien für den Abschluss eines Commits festgelegt. Ein Beispiel für eine solche Richtlinie ist beispielsweise isort zu nennen. Hierbei werden die Imports automatisch in sinnvoller Reihenfolge und alphabetisch sortiert.

### Docker Container

Docker Container werden innerhalb des Projektes einerseits für dev-dependencies, die Entwicklung in virtuellen Umgebungen und den Aufbau des Frontends verwendet 

### Logging

In einem .log file werden sämtliche Prozesse die in der Ausgabe beispielsweise beim Modell-Training oder im Preprocessing mitlaufen abgespeichert. Dies ist insbesondere für Debugging essentiell.

### Unittest

Es gibt verschiedene Unit-Tests im Projekt. Das Framework testet dabei unter anderem innerhalb der Preprocessing-Pipeline auf die korrekte shape der Daten, ob die entsprechenden Variablen entfernt wurden und der Pfad stimmt. Zudem gibt es einen Test, ob die Streamlit-Applikation aufrufbar ist. Durch die Unit- tests wird das gesamte System robuster und vereinfacht darüber hinaus das Debugging. 

### Pdoc

Durch die Software von Pdoc ist es innerhalb des Projekts möglich, sämtliche Docstrings in einer html-Datei zusammenzufassen und dementsprechend wichtige  Informationen zu dokumentieren.

