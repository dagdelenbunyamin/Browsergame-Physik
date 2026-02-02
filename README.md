# 🚀 Solar Lander Pro (Physics Edition)

![Version](https://img.shields.io/badge/Version-1.0.0-blue)
![Physics](https://img.shields.io/badge/Engine-Newtonian_Mechanics-orange)
![Year](https://img.shields.io/badge/Year-2026-brightgreen)

Ein interaktiver Flugsimulator zur Veranschaulichung der klassischen Mechanik in einem zweidimensionalen Koordinatensystem. Entwickelt als Physik-Projekt für die Oberstufe.

---

## 🌌 Physikalische Grundlagen

Das Spiel simuliert die Bewegung eines Landers unter Einfluss von Gravitation und Schubkraft mittels **Euler-Integration**.

### A) Vektorgleichungen
Die Gesamtbeschleunigung ergibt sich aus der Summe der wirkenden Kräfte:

$$F_{net} = \sum F = F_{Schub} + F_{Gravitation}$$

Aufgeteilt in Komponenten:
* **Vertikal (y-Achse):** $a_y = \frac{F_{Schub,y} - (m \cdot g)}{m}$
* **Horizontal (x-Achse):** $a_x = \frac{F_{Schub,x}}{m}$

### B) Numerische Integration
In jedem Frame ($dt \approx \frac{1}{60}s$) werden die Bewegungszustände diskret aktualisiert:
1.  **Geschwindigkeit:** $v_{neu} = v_{alt} + a \cdot dt$
2.  **Position:** $s_{neu} = s_{alt} + v \cdot dt$

---

## 🛠 Realismus & Vereinfachungen

Um den Fokus auf die **Vektormechanik** zu legen, wurden gezielte Annahmen getroffen:

* **Vakuum-Simulation:** Verzicht auf Luftwiderstand (entsprechend der Atmosphäre von Mond oder Mars).
* **Impuls-Grenzwerte:** Die strukturelle Integrität ist an die kinetische Energie gekoppelt. Eine erfolgreiche Landung erfordert:
    * $v_y < 3.0 \, \text{m/s}$
    * $v_x < 2.0 \, \text{m/s}$
* **Superpositionsprinzip:** Horizontale und vertikale Bewegungen werden unabhängig voneinander berechnet und im HUD separat visualisiert.

---

## 🎮 Features & Steuerung

-   **Variable Gravitation:** Erforsche unterschiedliche Ortsfaktoren $g$ (Mond: $1.62$, Mars: $3.71$, Erde: $9.81 \, \text{m/s}^2$).
-   **Treibstoff-Optimierung:** Begrenzte Ressourcen zwingen zur effizienten Berechnung der Flugbahn.
-   **Prozedurales Audio:** Dynamische Triebwerksgeräusche via Web Audio API (Oszillatoren).

### Steuerung
| Taste | Aktion |
| :--- | :--- |
| `Leertaste` / `↑` | Haupttriebwerk (Vertikaler Schub) |
| `←` / `→` | Steuerdüsen (Horizontaler Schub) |

---

## 💻 Technischer Stack

* **Core:** HTML5 Canvas API (60 FPS Rendering)
* **Styling:** Tailwind CSS (Modernes HUD Design)
* **Audio:** Web Audio API (Synthetische Klangerzeugung)
* **Versionierung:** Git / GitHub

---

> **Projektkontext:** Dieses Programm entstand im Rahmen des Physik-Unterrichts (2026) zur Demonstration von zweidimensionaler Kinematik.
