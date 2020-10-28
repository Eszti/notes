# Softwarearchitektur

## Aufgaben und Ziele

- Was ist Architektur?
  - Pläne
  - Abstraktiion
  - etwa: wo kommen die Daten her?, wie bette ich mein System in Unternehmen ein?
  - jeder kann sich Softwerarchitekt nennen
  - Definition:
    - Komponenten (Bausteine): wie zerlege ich mein System
    - Beziehungen
    - Prinzipien & Guidelines (Framework): konsistent eingehalten werden (Datebankzugriff, State Management)
      - Entwurfentscheidungen
      - Evoultion

- Aufgaben & Ziele
  - langfristig vs kurzfristige Projektziele
  - Architekturverletzung
    - Hebel
    - Gegenwirkung
    - Budget

  - Systeme definieren
  - Anforderung - Bausteine Mapping
  - Qualitätsszenarien
  - Anforderungsanalyse
  - Dokumentation
  - Rechtfertigung/Begründung der Architektur
  - Feedback einholen
  - Überraschungen vermeiden
  - Wartbarkeit erhalten/herstellen
  - Verständlichkeit des Codes erhöhen
  - Stakeholder für Qualitätsanforderungen (nichtfunktionale Anforderungen)
  - Rahmenbedungen betrachten
  - Nachvollziehbarkeit schaffen
  - Stakeholder identifizieren

- Architekt
  - beraten
    - Entwicklern, Betreiber, Management, Auftraggeber
  - entwerfen
    - Bausteine und deren Verantwortlichkeiten (viel mit Entwicklern)
  - aufdecken
    - implizite Annahmen
  - entscheiden
    - GUI, wie teile ich die Bausteine auf...
  - bewerten
    - Auswirkungen...
  - komminizieren
    - mit den Stakeholdern, Schnittstelelnro (lle
  - dokumentieren
    - bedarfgerecht (!!!)

## Dokumentatiion

- Warum
  - Rahmenbedingungen und Absprachen
  - Veranschaulichung
  - Kontext und Begründung wichtiger Entscheidungen

- Rolle des Architekten
  - Owner
  - holt Information ein
  - überprüft und lasst überprüfen
  - hält aktuell

- Zielgruppenorientierung
  - Management-Ebene: Was kostet
  - Anforderer: Wann
  - Entwickler: Umsetzung
  - Betrieb: Wartung

- 4 Anfordrungen
  - Verfügbarkeit
    - jeder hat Zugriff, etwa Confluence
  - Vollstä}digkeit
    - nicht alles im Detail!
    - Dinge fehlen oder bewusst rausgelassen sind?
  - Richtigkeit
    - falsche Doku bringt nichts
  - Aktualität
    - veraltete Doku ist Müll

- Was
  - Kontext (Abhängigkeiten)
  - Bausteine
  - Funktionale Anforderungen
  - Qualitätsmerkmale
  - Entscheidungen + Begründungen
  - Use Cases & Szenarien
  - Risiken
  - technische Schulden
  - Schnittstellen
  - Infrastruktur
  - Rahmenbedingungen
  - Stakeholder-Map
  - Laufzeitverhalten
  - Prinzipien
  - Design-Ziele
  - Prioritäten
  - Dokumentübersicht
  - (Zeit und Stufenplan)

- Wann?
  - wenn ich es mache/liefere
  - Schrank
    - prozessagnostixh
    - keine Bildung an Personen oder Rollen

- Wie?
  - Templatebasierte Dokumentation
  - arc42
    - deutsch
    - open source
  - C4
    - nicht deutsch
    - mappt auf arc43

- ADR: Architecture Decisiion Record
  - Entscheidungen statt Zustände
  - Titel | Status | Kontext | Entscheidung | Konsequenzen

- Archtekturwand
  - nicht zur Klagemauer
  - Ziele, Prinzipien, Technische Schulden & Risiken, Komponentensichten

## Vorgehen und Stakeholder

- Als erstes Stakeholder ermitteln
  - jeder der Interesse ans Produkt hat
  - Auftraggeber, Projektmanager, Administrator, Releasemanager, Dienstleiser, Kunde, Entwickler
  - Doku: Kontaktspalte
    - Ziele
    - Kontakt
    - Erwartung
    - Relevanz bei Abgabe

- Sprache
  - einheitliche Sprache
  - Glosser
    - Brücke zwischen Anforderern und Entwicklern
    - kontinuierliche Erweiterung
    - unterschiedliche Domänen

- Kontextabgrenzung
  - abstrakt, keine Bausteine im System
  - muss nicht UML Standard sein

- Rahmenbedingungen
  - Organisationsstruktur
  - Partnerschaften (e.g. Oracle)
  - Projektressources (Geld)
  - SLA von externen Services
  - Standards (e.g. Backup, DSGVO)
  - zeitpläne

- Risiken identifizieren
  - identifizieren
    - Feedbackschleifen
    - frühzeitig
  - Umgang
    - dokumentieren

## UML

### Entscheidungen

- implizit (ist nicht dokumentiert!) und explizit

- dokumentieren
  - dass men was beschlossen hat
  - Kontext: Abwägung, Konsequenzen
  - verworfene Wege

### Anwendungsfalldiagramm

- use case
- für Scenarios

### Laufzeitdiagramm

- sequence diagram
- wie Scenarios ablaufen

### Klassendiagramm

- immer generieren
- in Doku: im Fall von Patterns, Prinzipien, als Beispiel

### Aktivitätsdiagramm

- Start- und Endzustände

### Komponentendiagramme

- Datenbanken und Applikationen
- verschiedene Detailgrad
- Bausteinsicht

### Zustandsdiagremm

- Kanten und Knoten andersrum als bei Aktivitätsdiagramm
- für Ereignisse
- Microcontroller Umfeld

### Verteilungsdiagramm

- wo landet der Code?
- k8s, AWS generiertes Diagramm...

### Objektdiagramm

- in der Praxis quasi nie

## Archhitekturbewertung

- hierarchisches Quatlitätsmodell (ISO 25010)

- Funktionalität: das macht, was er tun soll
  - Angemessenheit: Genauigkeit von Werten
- Zuverlässigkeit
- Performanz
- Betreibbarkeit
- Sicherheit
- Kompatibilität
- Wartbarkeit
- Übertragbarkeit

### Qualitätsszenarien

- Messbarkeit: allerwichtigste

### ATAM

- wird häufig von externen Firmen gemacht

- Stakeholder identifizieren
- Ziele vorstellen
- Architektur vorstellen
- Qualitätsbaum erstellen
- durch Szenarien verfeinern
- Architektursäule analysieren
- Ergebnisse präsentieren

- Personen
  - leader: Architekt
  - Stakeholder

- Artefakten
  - Dokumentation

## Prinzipien

### Kopplung

- Statische
- Laufzeit
  - Datenbank
  - Abstürzen
  - Reihenfolge
  - Von Mitarbeiter zum Service
- niedrige Kopplung

### Kohesion

- hohe Kohesion
  - richtig geschnitten
- nicht von Bausteinen hinweg, sondern intern
- Änderungen auf einer Stelle

### Information Hiding

- private
- Iceberg

### Konzeptionelle Integrität (Consistency)

- einheitliche Struktur
- gleiche Probleme auf die gleich Art zu lösen
- Persistenzstrategie, Immutable Objects...

### SOLID-Prinzipien

- Single Responsibility Principle
- Open-close
  - open for extension, closed for modification
- Liskov substitution
  - e.g. in Tests Rechteckk durch Quadrat ersetzen
  - Rückgabewert: kann nicht weniger sein (keine schwächere Nachbedingungen)
  - Eingabeparams: kann nur Submenge sein (keinen stärkere Vorbedingungen)
  - schränkt die Vererbung ein
- Interface Segregation
- Dependency Inversion
  - abstrakte Teile dürfen keine konkrete Teile kennen
  - konkrete Teile dürfen nur abstrakte Teile kennen

## Methoden und Entwurf

ALLES WICHTIG

- Bausteine
  - Pakete: nur gruppieren
  - Komponente: mit Schnittstelle
  - Blackbox: info hiding
  - Whitebox: unit tests
  - unterschiedliche Levels

- Schnittstellendesign
  - leicht zu erlernen
  - decken alle Use-Cases ab
  - decken alle QAs ab
  - gut dokumentiert
  - rückwärtskompatibel
  - Fehlertoleranz

  - Externe
    - noch relevanter

  - Entwerfen
    - selber benutzen
    - Implementierung verstecken
    - sprechende Namen
    - minimale Seiteneffekte
    - doku: Sonder- und Fehlerfälle

### DDD

- Strategic design
  - Domaäne
    - Gesamtfachlichkeit
    - Subjekte und Verhalten
    - Subdomäne: fachlich abgeschlossene Teile
    - Core-Sub-Domain, Support-Sub-Domain (outsorcing)
  - Ubiquitous Language
    - Sub-Domain Level
    - immer mit Damain Experten
  - Bounded Context
    - im idealfall: Subdomain = BC
    - Abgrenzung eines Domains
    - Context Mapping: Übersetzung von einem auf das andere Domain

- Technical design
  - in BC
  - Entity
    - Subjekt
    - Lebenszyklus
  - Value Objects
    - immutable
  - Aggregate
    - root Entity + Sammlung von anderen Entitäten
    - in Transaktion speichern
  - Domain Event
  - Service
    - Implementierung von Operationen
  - Repository
    - Persistenzbaustein

  - DDD Building Blocks zu finden
    - Use Cases

### Werkzeuge

- Anforderungsmanagement
- Dokumentation und Modellierung (Code from Model)
  - Modellierung: PlantUML, StarUML, Enterprise Architekt
  - Generieren: JHipster, doxygen
- Entwicklung
  - IntelliJ, eclipse, Visual Studio (Verständnis ++)
- Analyse von Quellcode
  - statisch und dynamisch
  - Statisch: Sonar, FindBugs
  - dynamisch: JBoss Profiler, JMeter, VisualVM
- Analyse von Architektur
- Build & Deployment
  - CI/CD
  - Build: Ant, Maven, Gradle, Make
  - Versionieren: git
- Verteiltes Arbeiten in Teams
- Planung & Dokumentation von Architektur & Entwicklungstätigkeiten
  - Doku: markup, Wiki

- Anschaffungs- und Betriebskosten
- Lizenzen
- Bedienbarkeit
- Verfügbarkeit
- Skalierbarkeit

### ArchUnit

- TNG open source
- Architektureigenschaften aus Bytecode
- code smells dekumentieren
