============================================================
PROJEKT-DOKUMENTATION: SOLAR LANDER PRO (PHYSICS EDITION)
============================================================

1. PHYSIKALISCHE GRUNDLAGEN
Das Spiel basiert auf der klassischen Mechanik Newtons, erweitert auf 
ein zweidimensionales Koordinatensystem (x und y).

A) Vertikale Bewegung (y-Achse):
Hier wirkt das Kräftegleichgewicht zwischen Schubkraft (F_s) und 
Gewichtskraft (F_g).
Formel: F_net_y = F_schub_y - (m * g)
Beschleunigung: a_y = F_net_y / m

B) Horizontale Bewegung (x-Achse):
Hier wird die Trägheit bei seitlicher Beschleunigung simuliert.
Formel: F_net_x = F_schub_x
Beschleunigung: a_x = F_net_x / m

C) Integration (Euler-Verfahren):
In jedem Frame (dt ≈ 1/60s) werden die Werte aktualisiert:
v_neu = v_alt + a * dt
s_neu = s_alt + v * dt



2. REALISMUS & VEREINFACHUNGEN
Um den Spielspaß mit dem Lerneffekt zu kombinieren, wurden folgende 
Annahmen getroffen:
- Vakuum-Simulation: Kein Luftwiderstand, was für Mond und Mars 
  physikalisch korrekt ist.
- 2D-Translation: Das Schiff bleibt senkrecht orientiert, um den 
  Fokus auf die Vektorberechnung der Kräfte zu legen.
- Diskrete Kollision: Der Aufprall wird als unelastischer Stoß 
  gewertet. Übersteigt der Impuls beim Aufprall einen Grenzwert 
  (v > 3 m/s), führt die kinetische Energie zur Zerstörung.

3. INTERAKTIVE PARAMETER & LERNELEMENTE
Der "Pro"-Lander ermöglicht das Erforschen verschiedener Szenarien:
- Ortsfaktor (g): Variiert je nach Level (Mond: 1.62, Mars: 3.71, 
  Erde: 9.81 m/s²). Der Spieler spürt direkt die Auswirkung der 
  Gravitation auf die benötigte Gegenkraft.
- Treibstoff-Management: Die begrenzte Ressource erzwingt eine 
  effiziente Flugbahn (Optimierungsproblem).
- Vektor-Analyse: Das HUD zeigt Geschwindigkeiten in x- und y-Richtung 
  getrennt an, was das Verständnis für unabhängige Bewegungs-
  komponenten (Superpositionsprinzip) schärft.

4. TECHNISCHE UMSETZUNG
- Rendering: HTML5 Canvas API für flüssige 60-FPS-Grafik.
- UI/Design: Tailwind CSS für ein modernes, responsives HUD.
- Audio: Web Audio API zur dynamischen Erzeugung von Triebwerks-
  geräuschen basierend auf Oszillatoren (keine externen Samples).
- Partikel-System: Simulation von Abgasstrahlen zur Visualisierung 
  der Kraftrichtung.

5. STEUERUNG
- [LEERTASTE / PFEIL OBEN]: Haupttriebwerk (Vertikaler Schub)
- [PFEIL LINKS / RECHTS]: Steuerdüsen (Horizontaler Schub)
- Ziel: Landung auf der markierten Plattform mit v_y < 3.0 m/s 
  und v_x < 2.0 m/s.

============================================================
Entwickelt als Physik-Projekt (Oberstufe) - 2026
============================================================
