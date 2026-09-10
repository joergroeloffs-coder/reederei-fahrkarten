# Reederei Fahrkarten

Fahrkartenverkauf und Bordkontrolle für eine Fähr-Reederei: Karten
verkaufen, drucken und beim Einstieg prüfen. Eine einzige HTML-Datei,
ohne Server, ohne Netz, ohne Abhängigkeiten — im selben Stil wie der
[Ticketmanager](https://github.com/joergroeloffs-coder/Ticketmanager).

**Im Browser öffnen:** `index.html` herunterladen und per Doppelklick öffnen.

## Häfen und Verbindungen

Drei Häfen — Wyk, Dagebüll, Wittdün —, alle sechs gerichteten
Verbindungen dazwischen buchbar. Einfache Fahrt oder Hin- und
Rückfahrt, Erwachsenen- und Kindertarife.

## Zusatzkarten und Fahrzeuge

Fahrrad, Hund, Bollerwagen zum festen Preis je Fahrt. Pkw gestaffelt
nach Fahrzeuglänge, Lkw zum eigenen Preis. Alle Preise frei
einstellbar.

## Wie es arbeitet

Jede Fahrkarte trägt einen QR-Code aus drei Teilen: der Verbindung,
einer laufenden Nummer und einer Signatur (HMAC-SHA-256, gerechnet mit
einem Schlüssel aus den Einstellungen). Ohne den Schlüssel lässt sich
keine gültige Karte malen; ohne die gespeicherte Liste lässt sich keine
zweimal einlösen.

Bei einer Hin- und Rückfahrt gilt derselbe Code für beide Fahrten —
Hinfahrt und Rückfahrt werden getrennt verbucht. Bei der Bordkontrolle
wird immer gegen die dort gewählte Verbindung geprüft: eine Karte für
eine andere Strecke gilt dort nicht, auch wenn ihre Signatur stimmt.

Gerechnet wird in ganzen Cent. Die Daten liegen im Speicher des
Browsers, pro Gerät getrennt. Über *Einstellungen → Sicherung* lässt
sich der Stand exportieren und auf einem anderen Gerät wieder
einspielen.

## Was (noch) nicht dabei ist

- Fahrpläne und Abfahrtszeiten
- Mehrgeräte-Betrieb / laufender Abgleich zwischen mehreren Geräten
- Etiketten- oder Bondrucker

## Herkunft

Entstanden aus dem [Vereinsmanager](https://github.com/joergroeloffs-coder/vereinsmanager)
(Preislogik, Warenkorb) und dem [Ticketmanager](https://github.com/joergroeloffs-coder/Ticketmanager)
(QR-Code, Signatur, Bordkontrolle als Einlasskontrolle) — mit eigenem
Erscheinungsbild.
