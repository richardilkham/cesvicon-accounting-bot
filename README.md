# CESVICON – Smart Accounting & OCR Bot 

CESVICON ist ein KI-gestützter Telegram-Bot, der entwickelt wurde, um den manuellen Aufwand in der Buchhaltung radikal zu minimieren. Die Software automatisiert die Erfassung, rechtliche Prüfung und revisionssichere Archivierung von B2B-Rechnungen und alltäglichen Kassenbons.

## Kernfunktionen (Key Features)

* **Intelligente Datenextraktion (OCR & LLM):** Liest A4-Rechnungen und Bons in Millisekunden aus. Bei komplexen, zerknitterten oder unklaren Layouts greift automatisch ein LLM-Fallback, um maximale Genauigkeit bei der Datenerfassung zu gewährleisten.
* **§14 UStG Compliance-Check:** Das System prüft autonom, ob alle steuerrechtlich relevanten Pflichtangaben (z.B. Steuernummer, Anschrift, Umsatzsteuer) auf dem Beleg vorhanden sind, und meldet fehlende Daten sofort an den Nutzer zurück.
* **Smart Archiving & Tag-Search:** Mehr als nur ein Scanner. Jedes hochgeladene Dokument wird mit einer **Unique ID**, Zeitstempeln und intelligenten Tags (Händler, Kategorie, Betrag) versehen und in der Datenbank hinterlegt. Durch eine schnelle Suchfunktion (via Keyword oder Datum) lässt sich das Originalbild oder die Datei jederzeit in Sekunden wieder aufrufen.
* **Kategorisierung & Export:** Automatische Zuweisung von Spesenkategorien und strukturierte Aufbereitung für die nahtlose Integration in bestehende Unternehmens-Workflows.

## Tech Stack & Architektur

* **Backend & Logic:** Python 3, aiogram 3.x (Asynchronous Telegram Framework)
* **Data Processing:** Tesseract OCR, LLM-APIs zur semantischen Analyse
* **Intelligentes LLM-Routing (Timeout-gesteuerte Kaskade):** Einsatz einer dynamischen Fallback-Architektur zur Performance- und Kostenoptimierung. Das System überwacht die Antwortzeiten in Echtzeit: Überschreitet ein Modell das definierte Zeitlimit (Timeout), wird der Task nahtlos an die nächste Instanz übergeben.
  * **Gemma 2 (27B):** Die primäre High-Speed-Engine. Liefert die schnellsten Verarbeitungszeiten für Standard-Layouts und klare Tabellen.
  * **Llama 3.1 (8B):** Blitzschnelle und effiziente Alternative zur Textextraktion, die als direkter Fallback eingreift.
  * **Llama 3.3 (70B):** Der Heavy-Duty-Fallback. Übernimmt als letzte Instanz bei stark beschädigten, unstrukturierten Dokumenten, die eine tiefgreifende semantische Analyse erfordern.
* **Database & Storage:** PostgreSQL (für die sichere und relationale Speicherung von IDs, Tags und Metadaten)
* **Architecture:** Fokus auf asynchrone Task-Verarbeitung und ressourcenschonendes Routing für eine reibungslose Performance (verarbeitet Standard-Dokumente in unter 2 Sekunden).

## System Showcase

*(Platzhalter: Hier werden in Kürze die UI-Screenshots des Systems hinzugefügt)*
> 1. KI-gestützte Belegverarbeitung & Datenextraktion
> 2. §14 UStG-Prüfung & Erkennung fehlender Pflichtangaben
> 3. Schnelle Kassenbon-Erfassung & Kategorisierung
> 4. Dokumentensuche via Unique ID & Tags

---

**Möchten Sie manuelle Dateneingaben in Ihrem Unternehmen eliminieren?**  
Lassen Sie uns über Ihre Architektur sprechen: [Mein LinkedIn Profil](www.linkedin.com/in/richard-spengler)
