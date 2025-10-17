# Anforderungskatalog – Library of Things

Dieses Dokument beschreibt den Anforderungskatalog für das Softwareprojekt **„Library of Things“**.  
Ziel des Projekts ist die Entwicklung einer webbasierten Anwendung, mit der Gegenstände erfasst, reserviert, ausgeliehen und zurückgegeben werden können.  
Das System unterstützt verschiedene Benutzerrollen und bildet den gesamten Prozess der Ausleihe digital ab – von der Bestandsverwaltung bis zur Rückgabe.

---

## 1. Ziel und Nutzen

Studierende können Gegenstände sehen, reservieren und ausleihen.  
Admins pflegen den Bestand, sehen Ausleihen und geben Rückmeldungen frei.  
Fokus liegt auf verständlichem **CRUD-Design**.

---

## 2. Stakeholder und Rollen

- **Besucher**: Nur lesen und suchen.  
- **Benutzer**: Registriert, kann reservieren und eigene Ausleihen sehen.  
- **Admin**: Verwaltet Items, Kategorien, Bestände, Freigaben und Rückgaben.

---

## 3. Systemkontext

Web App mit Java Backend als **REST API**.  
Optional kleine Web-UI oder Postman-Tests.  
Datenbank lokal (**H2** oder **Postgres**).

---

## 4. Muss-Anforderungen (MVP)

- Items verwalten (CRUD)  
- Kategorien verwalten (CRUD)  
- Suchen und Filtern nach Kategorie und Verfügbarkeit  
- Reservieren und Ausleihen inkl. Genehmigung  
- Rückgabe mit Zustandsaktualisierung  
- Einfache Benutzerverwaltung  
- Protokollierung von Aktionen  

---

## 5. Kann-Anforderungen

- Echte Authentifizierung (JWT oder Session)  
- E-Mail-Benachrichtigungen  
- Bewertungen oder Kommentare  
- Bar- oder QR-Code für Item-Erkennung  
- Export als CSV  

---

## 6. Technischer Rahmen

- **Sprache:** Java 25
- **Framework:** Spring Boot 3.x
- **Datenbank:** H2 lokal, optional Postgres  
- **Build:** Maven  
- **Tests:** JUnit 5  
- **API-Dokumentation:** Springdoc OpenAPI  

---

## 7. REST API Entwürfe

**Beispiele:**
- `GET /api/items?search=&kategorie=&verfuegbar=true`  
- `POST /api/items`  
- `POST /api/reservierungen` *(Rolle: USER)*  
- `POST /api/reservierungen/{id}/genehmigen` *(Rolle: ADMIN)*  
- `POST /api/ausleihen/{id}/rueckgabe` *(Rolle: ADMIN)*  

---

## 8. Qualitätsanforderungen

- Verständlicher Code, JavaDoc an öffentlichen Methoden  
- 70 % Testabdeckung im Service-Layer  
- Saubere Fehlerbehandlung und korrekte HTTP-Codes  
- Swagger-Doku / OpenAPI verfügbar  

---

## 9. Definition of Done

- Alle Endpunkte gemäss Liste vorhanden und getestet  
- README erklärt Start in 3 Befehlen  
- API-Doku erreichbar  
- Beispieldaten verfügbar  
- Keine offenen Blocker-Bugs  
