[README.md](https://github.com/user-attachments/files/28377679/README.md)
# app
töölepingu automatiseerimine
# Töölepingu vormistamise prototüüp

See prototüüp asendab käsitsi Google Docsis töölepingu täitmise lihtsa töövooga:

1. kasutaja avab lokaalse veebivormi;
2. sisestab töötaja andmed ja 5 kuni 10 ametiülesannet;
3. vajutab `Loo täidetud leping`;
4. süsteem täidab lisatud töölepingu malli, salvestab selle lepingute kausta ja laadib alla `.docx` faili, mille saab avada või importida Google Docsi.

## Käivitamine

```powershell
& "C:\Users\kasutaja\.cache\codex-runtimes\codex-primary-runtime\dependencies\python\python.exe" .\app.py
```

Seejärel ava brauseris:

```text
http://127.0.0.1:8787
```

## Andmed, mida vorm küsib

- töötaja nimi;
- isikukood;
- aadress;
- ametinimetus;
- töötasu;
- tööle asumise kuupäev;
- ametiülesanded, 5 kuni 10 punkti.

## Lepingute hoiustamine

Kõik loodud lepingud salvestuvad siia kausta:

```text
C:\Users\kasutaja\Documents\Codex\2026-05-25\files-mentioned-by-the-user-to\generated\google-docsi-lepingud
```

Rakenduses on link `Salvestatud lepingud`, kust saab salvestatud failid uuesti alla laadida. Kui see kaust lisada Google Drive'i sünkkausta või laadida failid Google Drive'i üles, saab neid avada Google Docs dokumentidena.

## Tehniline märkus

Rakendus kasutab faili `template.docx` töölepingu mallina ning täidab selle Pythoniga. Väljund on Wordi `.docx`, mis sobib Google Docsi importimiseks ja seal edasi muutmiseks.
