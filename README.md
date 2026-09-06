# Rytmo Legal Site mit GitHub Pages veröffentlichen

Der Ordner enthält eine statische Website ohne Framework, Backend, Cookies, Tracking oder externe Analytics. Die ladungsfähige Anschrift ist in `privacy.html` und `imprint.html` eingetragen.

## 1. Anschrift vor der Veröffentlichung prüfen

Aktuell eingetragen:

```text
Adalbertstraße 8
48565 Steinfurt
```

Prüfe vor der Veröffentlichung, ob diese Anschrift noch aktuell ist, und trage dieselbe Anschrift in der App unter `src/config/legal.ts` ein.

## 2. GitHub-Repository erstellen

1. Melde dich auf GitHub an.
2. Klicke rechts oben auf das Pluszeichen und anschließend auf **New repository**.
3. Gib einen Repository-Namen ein, zum Beispiel `rytmo-legal`.
4. Wähle **Public**, damit GitHub Pages die Dateien öffentlich ausliefern kann.
5. Klicke auf **Create repository**.

## 3. Dateien hochladen

1. Öffne das neue Repository.
2. Klicke auf **Add file → Upload files**.
3. Lade den **Inhalt** dieses Ordners in das Stammverzeichnis des Repositorys:
   - `index.html`
   - `privacy.html`
   - `imprint.html`
   - `support.html`
   - `styles.css`
4. Klicke auf **Commit changes**.

Die HTML-Dateien sollen direkt im Stammverzeichnis liegen und nicht noch einmal in einem Unterordner `legal-site`.

## 4. GitHub Pages aktivieren

1. Öffne im Repository **Settings**.
2. Klicke links unter **Code and automation** auf **Pages**.
3. Wähle bei **Source** die Option **Deploy from a branch**.
4. Wähle als Branch `main`.
5. Wähle als Ordner `/(root)`.
6. Klicke auf **Save**.
7. Warte einige Minuten und lade die Pages-Seite erneut. GitHub zeigt danach die öffentliche URL an.

## 5. Öffentliche URLs

Das Schema lautet:

```text
https://USERNAME.github.io/REPOSITORY/
https://USERNAME.github.io/REPOSITORY/privacy.html
https://USERNAME.github.io/REPOSITORY/imprint.html
https://USERNAME.github.io/REPOSITORY/support.html
```

`USERNAME` und `REPOSITORY` müssen durch die echten GitHub-Werte ersetzt werden. Keine Beispieladresse unverändert übernehmen.

## 6. URL in Rytmo eintragen

1. Kopiere die endgültige URL zu `privacy.html`.
2. Öffne `src/config/legal.ts`.
3. Ersetze bei `PUBLIC_PRIVACY_POLICY_URL` den Wert `null` durch die URL in Anführungszeichen.
4. Erzeuge danach den iOS-Projektstand erneut und lade einen neuen Build hoch.

Beispiel für das Format:

```ts
export const PUBLIC_PRIVACY_POLICY_URL: string | null = 'https://USERNAME.github.io/REPOSITORY/privacy.html';
```

## 7. URL in App Store Connect eintragen

1. Öffne App Store Connect und wähle Rytmo.
2. Öffne die App-Version beziehungsweise die App-Informationen.
3. Trage als **Privacy Policy URL / Datenschutzrichtlinie-URL** genau die veröffentlichte `privacy.html`-Adresse ein.
4. Trage die veröffentlichte `support.html`-Adresse als Support-URL ein.
5. Öffne jede URL in einem privaten Browserfenster und prüfe, ob sie ohne Anmeldung erreichbar ist.
