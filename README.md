# Simple Transcription Tool – Desktop-app skapad i Tauri + SvelteKit

Skrivbordsapp som spelar in eller tar emot ljud, transkriberar det och låter en LLM
rätta, sammanfatta och plocka ut åtgärder. Gjord främst för digitala möten.

> **Status:** Tidigt skede. Det här repot innehåller **frontend** (Tauri + SvelteKit).
> Backenden (Spring Boot WebFlux som lokal sidecar) är inte påbörjad än.

## Funktioner

-  Ladda upp ljud (drag & drop / klick): mp3, wav, m4a, ogg, opus, flac, webm
-  Spela in mikrofon + systemljud (WASAPI-loopback), med pausa/återuppta och timer
-  Ljudvisualizer under inspelning
-  Transkribering med laddningsanimation, timer och möjlighet att avbryta
-  Resultat i tre delar: **End result**, **Punkter**, **Åtgärder**
-  Export till PDF, Word och Markdown
-  Ladda ner inspelat ljud (Opus)

## Teknikstack

| Del | Teknik |
|---|---|
| UI | SvelteKit (adapter-static), TypeScript |
| Desktop | Tauri 2 (Rust) |
| Inspelning | Rust: `cpal`/`wasapi`, `hound`, `rustfft` |
| Export | `pdfmake`, `docx` |
| Backend *(planerad)* | Spring Boot WebFlux → OpenRouter (STT + LLM) |

## Arkitektur

```
SvelteKit (UI, state, export)
   ├─ invoke/events ─▶ Rust (inspelning, nivåer, ffmpeg)
   └─ fetch ─────────▶ Spring Boot-sidecar (localhost) ─▶ OpenRouter
```

API-nyckeln finns bara i backenden och hamnar aldrig i frontend-bundlen.

## Kom igång

**Krav (Windows):** Node.js LTS, Rust (stable), [Tauri-förkrav](https://tauri.app/start/prerequisites/) (MSVC Build Tools, WebView2)

```bash
npm install
npm run tauri dev      # utvecklingsläge
npm run tauri build    # bygg installer
```

## Plattform

Windows först (WASAPI-loopback). macOS och Linux kommer senare.

> 💡 Använd hörlurar vid inspelning. Med högtalare tar mikrofonen även upp systemljudet och det blir eko i transkriptionen.

## Om utvecklingen

Projektet byggs med AI-assistans. Arkitektur, flöde och beslut finns i `docs/`.

## Licens

MIT
