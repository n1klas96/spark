---
toc: true
layout: post
description: Data Science Methodik-Konzept
categories: [markdown]
title: Data Science Methodik-Konzept - Beschreibung
---
---
## Abbildung des Datenflusses
---
![]({{ site.baseurl }}/images/Datenfluss.drawio.png "modellierter Datenfluss")

## Business Understanding

Das Ziel des Projektes ist die Entwicklung eines Auto Machine Learning Prozesses welcher innerhalb einer UI Schnittstelle ausgelöst werden kann.
Ausgehend von diesem Ziel müssen die Rohdaten des Turbofan-Datensatzes innerhalb einer Pipeline für das anschließende Training mit Pycaret aufbereitet werden. Sobald das Training der Modelle beendet ist, muss der Output (Metriken) der Modelle übersichtlich in einem Dataframe dargestellt werden.
Innerhalb einer Streamlit-Applikation muss es möglich sein, jenen Dataframe auszugeben, sowie ein "Retraining" der Pipeline erneut zu initiieren.

## Data Understanding

Die Datenbasis bildet der Turbofan-Datensatz, welcher in mehreren txt Dateien in data/raw des Projekt-Repositorys abliegt. Die Datensätze bestehen dabei  aus mehreren multivariaten Zeitreihen. Jeder Datensatz wird zudem in Trainings- und Test-Teilsätze unterteilt. Außerdem stammt jede Zeitreihe aus einer unterschiedlichen Maschine. Die Textdateien werden mit 26 numerischen Variablen, getrennt durch Leerzeichen, bereitgestellt. 

## Data Preparation

In der Datenaufbereitung wird der Trainingsdatensatz zunächst für die "Preprocessing Pipeline" aufbereitet. Wichtige Schritte sind hierbei die Bestimmung der Input Feature, sowie des Target Features. Während das Taret Feature die Sensor-Werte 1-23 annehmen kann, müssen die Variablen: Unit-Number, Cycles und Operational Settings 1-3 in kategoriale Variablen konvertiert werden.
Im Anschluss werden mithilfe einer Pipeline, fehlende und None Werte entfernt. zudem werden die numerischen Variablen skaliert.

## Modeling

Durch die PyCaret Funktion .setup werden die numerischen, kategorialen Variablen, sowie das Target Feature für das anschließende Training initialisiert.
Das eigentliche Training erfolgt durch die Funktion .compare_models()

## Evaluierung

Nachdem das Modell-Training beendet ist, wird durch die .pull() Funktion ein Data Frame erzeugt, welcher die Trainingsresultate zusammenfasst. 
Der Data Frame beinhaltet eine Auflistung der unterschiedlichen Modelle, dem entsprechenden MAE, MSE, RMSE, R^2, RMSLE, MAPE und die verstrichene Trainingstzeit. Anhand dieser Metriken kann jedes Modell evaluiert werden

## Deployment

Die Applikation sollte eigentlich mit Streamlit Cloud deployed werden, da mithilfe dieses Dienstes der Veröffentlichungsprozess recht einfach umsetzbar ist. Um die Applikation public zu machen, wird ledigleich ein GitHub-Repository mit den selben Inhalten wie in GitLab Repository benötigt. Im Anschluss kann direkt über die lokale Streamlit-App die build-in Funktion "deploy app" verwendet werden. Nachdem man dort den entsprechenden GitHub-Account und Repository angegeben hat, wird die Applikation automatisch deployed. Hierbei kann es zu Problemen kommen, wenn die App die von Streamlit breitgestellten Ressourcen übertrifft. Dieses Problem ist leider in unserem Fall aufgetreten, da die Modellierung mit PyCaret extrem viele Ressourcen braucht.
