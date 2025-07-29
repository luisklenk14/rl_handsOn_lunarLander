# rl_handsOn_lunarLander
 Landen Lernen: Entwicklung eines Reinforcement-Learning-Agenten in der LunarLander-Umgebung


# 🛰️ Reinforcement Learning mit PPO in der Umgebung `LunarLander-v3`

## 🔍 Projektüberblick

Dieses Projekt untersucht die **Entwicklung, das Verhalten und die Performance** eines Reinforcement-Learning-Agenten auf Basis des **Proximal Policy Optimization (PPO)**-Algorithmus in der bekannten **OpenAI Gymnasium-Umgebung `LunarLander-v3`**.

Ziel war es, einen Agenten zu trainieren, der lernt, ein Landemodul kontrolliert und sicher auf einer Plattform zu landen — ein klassisches Beispiel für **kontinuierliche Steuerung unter Unsicherheit** in einem **Markov Decision Process (MDP)**.

---

## 🎯 Zielsetzung

* Training eines RL-Agenten mit PPO zur Lösung der LunarLander-Aufgabe
* Analyse des Trainingsverlaufs durch geeignete Metriken und Visualisierungen
* Visuelle Evaluation des Agentenverhaltens anhand von gespeicherten Videos
* Kritische Reflexion des Lernverhaltens, der Belohnungsstruktur und möglicher Verbesserungen

---

## ⚙️ Setup & Ausführung

### 🧱 Voraussetzungen

* Python ≥ 3.8
* Abhängigkeiten sind in requirements.txt definiert
* pip install -r requirements.txt

---

### ▶️ Training starten

Das Skript trainiert einen PPO-Agenten für 500.000 Schritte mit Zwischenevaluationen.

---

### 📊 Evaluierung & Visualisierung

Nach dem Training werden zwei Diagramme erzeugt:

* **Reward-Verlauf** über die Zeit (Lernkurve + gleitender Mittelwert)
* **Episodenlänge** über die Zeit (zeigt Effizienz des Agenten)

Zusätzlich wurden seperat drei Evaluierungsvideos erzeugt und gespeichert:

* Nach **20**, **10.000** und **500.000** Schritten
* Dienen zur qualitativen Einschätzung des Fortschritts

---

## 📈 Ergebnisse & Beobachtungen

| Timestep  | Beobachtung (Video)                           |
| --------- | --------------------------------------------- |
| 20        | Agent stürzt unkontrolliert ab                |
| 10.000    | Agent zeigt Steuerung, landet aber unpräzise  |
| 500.000 | Agent landet kontrolliert, aber knapp im Ziel |

### 📉 Lernverlauf

* Deutlich steigende Rewards bis ca. **200.000** Schritte → schneller Lernerfolg
* **Episodenlänge** sinkt im Verlauf → Agent findet effizientere Strategien
* Belohnungsstruktur belohnt Landung, aber nicht Präzision → erklärt Limitierung

---

## 🧠 Kritische Reflexion

* PPO ist robust, aber nicht optimal für **Feinsteuerung**
* Belohnungsfunktion der Umgebung kann zu „suboptimalem Verhalten“ führen
* Videos sind unerlässlich zur **qualitativen Bewertung**
* Reward allein spiegelt nicht immer reale Steuerungsqualität wider

---

## 🔮 Mögliche Erweiterungen

* Alternative Algorithmen: DDPG, TD3, SAC für kontinuierliche Kontrolle
* Reward-Shaping zur Förderung von Präzision
* Curriculum Learning oder Transfer Learning
* Integration eines Custom Reward-Trackings

---

## 📁 Projektstruktur

```
├── training_lunar.ipynb      # Training + Speicherung Agent evaluieren + Video erzeugen
├── models/                   # Gespeicherte Modelle (beste & letzte)
├── logs/                     # TensorBoard Logs & Evaluationsergebnisse
├── videos/                   # Evaluation als Video (MP4)
└── README.md                 # Diese Datei
```

---

## ✍️ Motivation

Dieses Projekt entstand im Rahmen eines Hochschulprojekts zur **praktischen Anwendung von Reinforcement Learning**. 
Die Simulation vermittelt spielerisch, aber herausfordernd die Grundprinzipien der autonomen Entscheidungsfindung. Als jemand mit Interesse an Computerspielen und Robotik war dies eine motivierende und anschauliche Wahl. Außerdem hätte ich jetzt noch eine Drohne mehr, wenn sie es geschafft hätte dort zu landen, wo sie gestartet ist.

