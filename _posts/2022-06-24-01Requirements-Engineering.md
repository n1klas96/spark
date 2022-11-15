---
toc: true
layout: post
description: Requirements Engineering
categories: [markdown]
title: Modellierte Anforderungen (Requirements)
---
## Modellierte Requirements von Frunch Infinity
---
![]({{ site.baseurl }}/images/requirements.drawio.png "modellierte Requirements")

## Veränderung der Requirements im Projektverlauf

In Stage 1 unseres Projektes haben wir die Requirements nach den Sophisten Regeln grundlegend festgelegt und auf Basis jener
wurden die ersten, erforderlichen Entwicklungsschritte durchgeführt:

- erstellung eines dev-containers
- Aufbau einer preprocessing Pipeline
- Aufbau einer CI/CD Pipeline
- Unit-Tests für Pipelines
- erste Version der Streamlit Applikation
- Modellentwicklung mit PyCaret

Nachdem die ersten Entwicklungsschritte von Stage 1 abgeschlossen waren, haben wir in unserem Sprint-Review einen neuen Requirement-Zyklus eingeleitet
und die einzelnen Requirements neu priorisiert.
Zunächst hat sich gezeigt das das Requirement: "Wenn der Turbofan-Datensatz in die Streamlit-Applikation importiert wurde, muss die Applikation
alle Variablen und Werte des Datensatzes erkennen" nach unseren ersten Entwicklungserkenntnissen nicht ganz passend für unsere MVP-Software einer Auto-ML ist. Der Import von einem oder verschiedenen Datensätzen erschwert die Entwicklung eines ersten, funktionierenden Produkts enorm.
Die Wichtigkeit unserer Requirements wurde also in diesem Zyklus angepasst auf zunächst einen Datensatz (Turbofan) und Regressions-Algorithmen priorisiert.

Nach jedem größeren Entwicklungsschritt bzw. in jedem Sprint-Review sollten die aufgestellten Requirements auf konsistenz und Vollständigkeit geprüft werden, da auf Veränderungen innerhalb der Requirements nur angemessen reagiert werden kann, wenn diese bekannt sind.

[^1]: Die Abbildung wurde mit draw.io erstellt


