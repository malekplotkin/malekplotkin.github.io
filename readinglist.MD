<html lang="en">
<head>
<meta charset="utf-8">
<meta name="viewport" content="width=device-width, initial-scale=1, viewport-fit=cover">
<title>Reading – Your Name</title>
<meta name="description" content="Reading resources recommended by Your Name.">
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Bricolage+Grotesque:opsz,wght@12..96,500;12..96,800&family=Newsreader:ital,opsz,wght@0,6..72,400;0,6..72,500;1,6..72,400&display=swap" rel="stylesheet">
<style>
:root {
  --bg: #edeadf;
  --ink: #2a2016;
  --muted: #62513b;
  --line: #b8a37d;
  --accent: #2f4a3a;
  --accent-ink: #f1e7d3;
  --display: "Bricolage Grotesque", "Helvetica Neue", Arial, sans-serif;
  --text: "Newsreader", Georgia, "Times New Roman", serif;
  box-sizing: border-box;
  padding-top: env(safe-area-inset-top, 0px);
  padding-bottom: env(safe-area-inset-bottom, 0px);
}
@media (prefers-color-scheme: dark) {
  :root:not([data-theme="light"]) {
    --bg: #211a12; --ink: #ebddc3; --muted: #aa9a80; --line: #3d3224;
    --accent: #b9cba0; --accent-ink: #211a12;
  }
}
:root[data-theme="dark"] {
  --bg: #211a12; --ink: #ebddc3; --muted: #aa9a80; --line: #3d3224;
  --accent: #b9cba0; --accent-ink: #211a12;
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

h1 a { color: inherit; text-decoration: none; }
h1 a:hover { color: var(--accent); }
nav a[aria-current="page"] { color: var(--accent); }

.jump { display: flex; flex-wrap: wrap; gap: 0.5rem 1.25rem; font-family: var(--display); font-weight: 500; margin: 0 0 2.5rem; }
.reads { list-style: none; margin: 0; padding: 0; }
.reads li { padding: 1rem 0; border-top: 1px solid var(--line); }
.reads li:last-child { border-bottom: 1px solid var(--line); }
.reads strong { font-family: var(--display); font-weight: 500; font-size: 1.15rem; display: block; }
.reads span { color: var(--muted); }

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
  <main>
    <section id="reading">
      <h2>Reading</h2>
      <p>[A line or two about what you read and why. Swap the placeholders below for your own picks.]</p>
      <p class="jump">
        <a href="#think-tanks">Think Tanks</a>
        <a href="#books">Books</a>
        <a href="#magazines-newspapers">Magazines/Newspapers</a>
        <a href="#people">People</a>
      </p>
    </section>

    <section id="think-tanks">
      <h2>Think Tanks</h2>
      <ul class="reads">
        <li><strong><a href="#">Think tank name</a></strong><span>Why you read them and what they cover.</span></li>
        <li><strong><a href="#">Think tank name</a></strong><span>Why you read them and what they cover.</span></li>
        <li><strong><a href="#">Think tank name</a></strong><span>Why you read them and what they cover.</span></li>
      </ul>
    </section>

    <section id="books">
      <h2>Books</h2>
      <ul class="reads">
        <li><strong><a href="#">Book title, Author</a></strong><span>A line on why it stuck with you.</span></li>
        <li><strong><a href="#">Book title, Author</a></strong><span>A line on why it stuck with you.</span></li>
        <li><strong><a href="#">Book title, Author</a></strong><span>A line on why it stuck with you.</span></li>
      </ul>
    </section>

    <section id="magazines-newspapers">
      <h2>Magazines/Newspapers</h2>
      <ul class="reads">
        <li><strong><a href="#">Publication name</a></strong><span>What you turn to it for.</span></li>
        <li><strong><a href="#">Publication name</a></strong><span>What you turn to it for.</span></li>
        <li><strong><a href="#">Publication name</a></strong><span>What you turn to it for.</span></li>
      </ul>
    </section>

    <section id="people">
      <h2>People</h2>
      <ul class="reads">
        <li><strong><a href="#">Person's name</a></strong><span>Who they are and why they're worth following.</span></li>
        <li><strong><a href="#">Person's name</a></strong><span>Who they are and why they're worth following.</span></li>
        <li><strong><a href="#">Person's name</a></strong><span>Who they are and why they're worth following.</span></li>
      </ul>
    </section>

    <footer>&copy; 2026 Your Name</footer>
  </main>
</div>
</body>
</html>
