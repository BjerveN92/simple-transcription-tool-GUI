<!-- Läge 1: idle / recording / paused / ready -->
<main class="view">
  <header class="header">
    <h1 class="logo">Logotype</h1>
  </header>

  <section class="sources">
    <!-- Uppladdning: label + dold input = klick öppnar filväljaren utan JS -->
    <label class="dropzone">
      <input
        type="file"
        accept=".mp3,.wav,.m4a,.ogg,.opus,.flac,.webm"
        hidden
      />
      <p>Drag-and-drop eller klicka för att ladda upp</p>
      <small>mp3, wav, m4a, ogg, opus, flac, webm</small>
    </label>

    <!-- Inspelning (WASAPI mic + loopback) -->
    <div class="recorder">
      <canvas class="visualizer"></canvas>
      <time class="timer">00:00:00</time>
      <div class="controls">
        <button type="button">Spela in</button>
        <button type="button" disabled>Pausa</button>
        <button type="button" disabled>Stop</button>
      </div>
    </div>
  </section>

  <!-- Visas i ready: ett ljud åt gången (inspelning ELLER uppladdning) -->
  <section class="audio-file">
    <span class="audio-meta">&lt;namn på ljudfil&gt; : &lt;tidslängd&gt;</span>
    <div class="audio-actions">
      <button type="button">Ladda ner</button>
      <button type="button" aria-label="Ta bort ljud">✕</button>
    </div>
  </section>

  <button type="button" class="transcribe" disabled>Transkribera</button>
</main>

<style>
  .view {
    display: flex;
    flex-direction: column;
    gap: 2rem;
    max-width: 960px;
    min-height: 100vh;
    margin: 0 auto;
    padding: 1.5rem 2rem;
    box-sizing: border-box;
  }

  .header {
    display: flex;
    align-items: center;
  }

  /* Uppladdning och inspelning sida vid sida, bryts till kolumn på smal skärm */
  .sources {
    display: flex;
    flex-direction: row;
    flex-wrap: wrap;
    gap: 2rem;
  }

  .dropzone,
  .recorder {
    flex: 1 1 320px;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    gap: 0.75rem;
    min-height: 220px;
    padding: 2rem;
    box-sizing: border-box;
  }

  .dropzone p,
  .dropzone small {
    margin: 0;
  }

  .visualizer {
    width: 100%;
    height: 80px;
  }

  .controls {
    display: flex;
    flex-direction: row;
    gap: 0.75rem;
  }

  .audio-file {
    display: flex;
    justify-content: space-between;
    align-items: center;
    gap: 1rem;
    padding: 0.75rem 1rem;
  }

  .audio-actions {
    display: flex;
    gap: 0.5rem;
  }

  .transcribe {
    align-self: center;
    padding: 0.75rem 2.5rem;
  }
</style>
