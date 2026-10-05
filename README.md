<style>
:root {
  --bg: #ffffff
  --ink: #000000;
  --muted: #4a4a4a;
  --line: #542900;
  --accent: #542900;
  --accent-ink: #ffffff;
  --display: "Bricolage Grotesque", "Helvetica Neue", Arial, sans-serif;
  --text: "Newsreader", Georgia, "Times New Roman", serif;
  box-sizing: border-box;
  padding-top: env(safe-area-inset-top, 0px);
  padding-bottom: env(safe-area-inset-bottom, 0px);
}
@media (prefers-color-scheme: dark) {
  :root:not([data-theme="light"]) {
    --bg: #101624; --ink: #e6ecf5; --muted: #98a5ba; --line: #2a3550;
    --accent: #8ea6ff; --accent-ink: #101624;
  }
}
:root[data-theme="dark"] {
  --bg: #101624; --ink: #e6ecf5; --muted: #98a5ba; --line: #2a3550;
  --accent: #8ea6ff; --accent-ink: #101624;
}
html { scroll-padding-top: env(safe-area-inset-top, 0px); }
*, *::before, *::after { box-sizing: border-box; }
body {
  margin: 0;
  background: var(--bg);
  color: var(--ink);
  font-family: var(--text);
  font-size: 1.125rem;
  line-height: 1.65;
}
a { color: inherit; text-decoration-color: var(--accent); text-underline-offset: 0.22em; text-decoration-thickness: 0.08em; }
a:hover { color: var(--accent); }
a:focus-visible { outline: 3px solid var(--accent); outline-offset: 3px; border-radius: 2px; }

.wrap {
  display: grid;
  grid-template-columns: minmax(0, 5fr) minmax(0, 6fr);
  gap: clamp(2rem, 6vw, 6rem);
  max-width: 78rem;
  margin: 0 auto;
  padding: clamp(1.5rem, 5vw, 4rem);
}
header { position: sticky; top: 0; align-self: start; padding-top: 1rem; }
h1 {
  font-family: var(--display);
  font-weight: 800;
  font-size: clamp(3.5rem, 11vw, 9rem);
  line-height: 0.88;
  letter-spacing: -0.04em;
  margin: 0 0 1.5rem;
  overflow-wrap: anywhere;
}
.tagline { font-size: 1.35rem; line-height: 1.4; max-width: 22ch; margin: 0 0 2rem; color: var(--muted); }
nav { display: flex; flex-wrap: wrap; gap: 0.5rem 1.25rem; font-family: var(--display); font-weight: 500; font-size: 1rem; }

main { padding-top: 1rem; }
section { padding: 0 0 3.5rem; }
h2 { font-family: var(--display); font-weight: 800; font-size: 1.6rem; letter-spacing: -0.02em; margin: 0 0 1rem; }
h3 { font-family: var(--display); font-weight: 800; font-size: 1.6rem; letter-spacing: -0.00em; margin: 0 0 0rem; }
p { margin: 0 0 1rem; max-width: 62ch; }

.list { list-style: none; margin: 0; padding: 0; }
.list li { display: grid; grid-template-columns: 4.5rem 1fr; gap: 1rem; padding: 1rem 0; border-top: 1px solid var(--line); }
.list li:last-child { border-bottom: 1px solid var(--line); }
.when { font-family: var(--display); font-weight: 500; font-size: 0.95rem; color: var(--muted); padding-top: 0.2rem; }
.list strong { font-family: var(--display); font-weight: 500; font-size: 1.15rem; display: block; }
.list span { color: var(--muted); }

.button {
  display: inline-block;
  font-family: var(--display);
  font-weight: 800;
  background: var(--accent);
  color: var(--accent-ink);
  padding: 0.8rem 1.4rem;
  border-radius: 999px;
  text-decoration: none;
}
.button:hover { color: var(--accent-ink); filter: brightness(1.1); }
footer { color: var(--muted); font-size: 0.95rem; padding-top: 1rem; }

@media (max-width: 52rem) {
  .wrap { grid-template-columns: 1fr; gap: 1.5rem; }
  header { position: static; }
  .tagline { max-width: 32ch; }
}
@media (prefers-reduced-motion: no-preference) {
  h1 { animation: rise 0.7s cubic-bezier(.2,.7,.2,1) both; }
  @keyframes rise { from { opacity: 0; transform: translateY(0.6em); } to { opacity: 1; transform: none; } }
}
</style>
<body>
<div class="wrap">
  <header>
    <h1>Malek Plotkin</h1>
    <p class="tagline">[studying history @ boston university]</p>
    <nav aria-label="Sections">
      <a href="#about">About</a>
      <a href="#work">Work</a>
      <a href="#writing">Writing</a>
      <a href="#Graphs">Graphs and Maps</a>
  <a href="https://malekplotkin.github.io/readinglist">Reading List</a>
      <a href="https://feraldgord.substack.com/">Substack</a>
      <a href="#contact">Contact</a>
  


    </nav>
  </header>

  <main>
    <section id="about">
      <h2>About</h2>
      <p>[Two or three sentences introducing yourself: where you're based, what you've been working on, and what you care about.]</p>
      <p>[One more sentence about what you're looking for or what you do outside of work.]</p>
    </section>

    <section id="work">
      <h2>Selected work</h2>
      <ul class="list">
        <li><span class="when">2026</span><div><strong><a href="#">Project title</a></strong><span>One line on what it is and what you did.</span></div></li>
        <li><span class="when">2025</span><div><strong><a href="#">Project title</a></strong><span>One line on what it is and what you did.</span></div></li>
        <li><span class="when">2024</span><div><strong><a href="#">Project title</a></strong><span>One line on what it is and what you did.</span></div></li>
      </ul>
    </section>

 <section id="Writing">
      <h2>Writing</h2>
      <ul class="list">
        <li><span class="when">May 2026</span><div><strong><a href="#">Post or article title</a></strong><span>A short description of the piece.</span></div></li>
        <li><span class="when">May 2026</span><div><strong><a href="#">Post or article title</a></strong><span>A short description of the piece.</span></div></li>
      </ul>
    </section>

<section id="Graphs">
      <h2>Graphs and Maps</h2>
      <ul class="list">
        <iframe title="Ozaukee 2-Party President Margin" aria-label="Interactive line chart" id="datawrapper-chart-qQdJu" src="https://datawrapper.dwcdn.net/qQdJu/3/" scrolling="no" frameborder="0" style="width: 0; min-width: 100% !important; border: none;" height="472" data-external="1"></iframe><script type="text/javascript">!function(){"use strict";window.addEventListener("message",(function(a){if(void 0!==a.data["datawrapper-height"]){var e=document.querySelectorAll("iframe");for(var t in a.data["datawrapper-height"])for(var r=0;r<e.length;r++)if(e[r].contentWindow===a.source){var i=a.data["datawrapper-height"][t]+"px";e[r].style.height=i}}}))}(); </script>
<div style="min-height:491px" id="datawrapper-vis-yQwFM"><script type="text/javascript" defer src="https://datawrapper.dwcdn.net/yQwFM/embed.js" charset="utf-8" data-target="#datawrapper-vis-yQwFM"></script><noscript><img src="https://datawrapper.dwcdn.net/yQwFM/full.png" alt="" /></noscript></div>      </ul>
<li><span class="when">Sept 6, 2026</span><div><strong><a href="https://x.com/ferald_gord/status/2096700836696977748/photo/1">2026 Norf-Suff District – Democratic Primary Precinct Map.</a></strong><span><br>A precinct map of September 1st Democratic primary for the Norfolk and Suffolk District in the Massachusetts State Senate. 
<img src="https://i.imgur.com/0l22N7u.png">
</span></div></li>    
</section>
    
    <section id="contact">
      <h3>Contact</h3>
            <p>malekplotkin at gmail dot com.</p>
      <p><a href="#">GitHub</a> &nbsp; <a href="#">LinkedIn</a> &nbsp; <a href="https://x.com/ferald_gord">Twitter (X)</a></p>
    </section>

    <footer>&copy; Malek Plotkin</footer>
  </main>
</div>
</body>
</html>
