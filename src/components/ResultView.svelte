<!-- Läge 3: result -->
<main class="view">
  <header class="header">
    <h1 class="logo">Logotype</h1>
  </header>

  <section class="results">
    <!-- correctedText -->
    <article class="end-result">
      <h2>End result</h2>
      <p class="corrected-text">– Talare 1 … – Talare 2 …</p>
    </article>

    <aside class="side">
      <!-- summary[] -->
      <section class="points">
        <h2>Punkter</h2>
        <ul>
          <li>Punkt 1</li>
          <li>Punkt 2</li>
        </ul>
      </section>

      <!-- actionItems[] -->
      <section class="actions">
        <h2>Åtgärder</h2>
        <ul>
          <li>Åtgärd 1</li>
        </ul>
      </section>
    </aside>
  </section>

  <footer class="footer">
    <div class="export">
      <span>Ladda ner i följande format</span>
      <div class="export-buttons">
        <button type="button">PDF</button>
        <button type="button">Word</button>
        <button type="button">Markdown</button>
      </div>
    </div>

    <!-- Bara om ljudet var en inspelning -->
    <div class="audio-file">
      <span class="audio-meta">&lt;namn på ljudfil&gt; : &lt;tidslängd&gt;</span
      >
      <button type="button">Ladda ner</button>
    </div>

    <button type="button" class="new">Ny transkribering</button>
  </footer>
</main>

<style>
  .view {
    display: flex;
    flex-direction: column;
    gap: 2rem;
    max-width: 1200px;
    min-height: 100vh;
    margin: 0 auto;
    padding: 1.5rem 2rem;
    box-sizing: border-box;
  }

  .header {
    display: flex;
    align-items: center;
  }

  /* End result tar 2/3, Punkter + Åtgärder 1/3 */
  .results {
    flex: 1;
    display: flex;
    flex-direction: row;
    flex-wrap: wrap;
    gap: 2rem;
  }

  .end-result {
    flex: 2 1 400px;
  }

  .side {
    flex: 1 1 260px;
    display: flex;
    flex-direction: column;
    gap: 1.5rem;
  }

  h2 {
    margin: 0 0 0.75rem;
  }

  .corrected-text {
    margin: 0;
    white-space: pre-wrap; /* bevarar "– " och radbrytningar från LLM:en */
  }

  ul {
    margin: 0;
    padding-left: 1.25rem;
  }

  .footer {
    display: flex;
    flex-wrap: wrap;
    justify-content: space-between;
    align-items: center;
    gap: 1rem;
  }

  .export,
  .audio-file {
    display: flex;
    align-items: center;
    gap: 0.75rem;
  }

  .export-buttons {
    display: flex;
    gap: 0.5rem;
  }
</style>
