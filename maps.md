<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="utf-8">
<meta name="viewport" content="width=device-width, initial-scale=1, viewport-fit=cover">
<title>Gallery – Your Name</title>
<meta name="description" content="Photo gallery by Your Name.">
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

.carousel { margin-top: 1.5rem; }
.track { display: flex; overflow-x: auto; scroll-snap-type: x mandatory; scrollbar-width: none; border-radius: 6px; border: 1px solid var(--line); }
.track::-webkit-scrollbar { display: none; }
.track:focus-visible { outline: 3px solid var(--accent); outline-offset: 3px; }
.slide { flex: 0 0 100%; scroll-snap-align: center; margin: 0; }
.slide img { display: block; width: 100%; aspect-ratio: 3 / 2; object-fit: cover; }
.controls { display: flex; align-items: center; justify-content: space-between; gap: 1rem; margin-top: 1rem; }
.arrows { display: flex; gap: 0.5rem; }
.arrows button {
  font: 800 1.1rem var(--display); width: 2.75rem; height: 2.75rem; border-radius: 50%;
  border: 1.5px solid var(--ink); background: transparent; color: var(--ink); cursor: pointer;
}
.arrows button:hover { background: var(--accent); border-color: var(--accent); color: var(--accent-ink); }
.arrows button:focus-visible, .dots button:focus-visible { outline: 3px solid var(--accent); outline-offset: 3px; }
.dots { display: flex; gap: 0.5rem; }
.dots button { width: 0.75rem; height: 0.75rem; padding: 0; border-radius: 50%; border: 1.5px solid var(--ink); background: transparent; cursor: pointer; }
.dots button[aria-current="true"] { background: var(--ink); }
#caption { margin: 1rem 0 0; color: var(--muted); min-height: 1.65em; }
@media (prefers-reduced-motion: no-preference) { .track { scroll-behavior: smooth; } }

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
</head>
<body>
<div class="wrap">
  <header>
    <h1><a href="index.html">Your Name</a></h1>
    <p class="tagline">[One sentence on what you do and who it's for.]</p>
    <nav aria-label="Sections">
      <a href="index.html#about">About</a>
      <a href="index.html#work">Work</a>
      <a href="index.html#writing">Writing</a>
      <a href="index.html#contact">Contact</a>
      <a href="gallery.html" aria-current="page">Gallery</a>
    </nav>
  </header>

  <main>
    <section id="gallery">
      <h2>Gallery</h2>
      <p>[A line about what these images show.]</p>
      <div class="carousel" role="region" aria-roledescription="carousel" aria-label="Photo gallery">
        <div class="track" id="track" tabindex="0"></div>
        <div class="controls">
          <div class="arrows">
            <button type="button" id="prev" aria-label="Previous image">&larr;</button>
            <button type="button" id="next" aria-label="Next image">&rarr;</button>
          </div>
          <div class="dots" id="dots"></div>
        </div>
        <p id="caption" aria-live="polite"></p>
      </div>
    </section>

    <footer>&copy; 2026 Your Name</footer>
  </main>
</div>
<script>
// Replace each src with your own image path (e.g. "photos/one.jpg") and edit the captions.
var PHOTOS = [
  { caption: "Caption for the first image.",  bg: "#c9b48c", fg: "#2a2016" },
  { caption: "Caption for the second image.", bg: "#2f4a3a", fg: "#f1e7d3" },
  { caption: "Caption for the third image.",  bg: "#8a7656", fg: "#f1e7d3" },
  { caption: "Caption for the fourth image.", bg: "#a9b79a", fg: "#2a2016" }
];
function placeholder(n, bg, fg) {
  var svg = '<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 1200 800"><rect width="1200" height="800" fill="' + bg + '"/><text x="600" y="420" font-family="Arial, sans-serif" font-size="56" text-anchor="middle" fill="' + fg + '">Image ' + n + '</text></svg>';
  return "data:image/svg+xml;utf8," + encodeURIComponent(svg);
}
var track = document.getElementById("track"), dots = document.getElementById("dots"), caption = document.getElementById("caption");
PHOTOS.forEach(function (p, i) {
  var fig = document.createElement("figure"); fig.className = "slide";
  var img = document.createElement("img");
  img.src = placeholder(i + 1, p.bg, p.fg); img.alt = p.caption;
  fig.appendChild(img); track.appendChild(fig);
  var d = document.createElement("button"); d.type = "button";
  d.setAttribute("aria-label", "Go to image " + (i + 1));
  d.addEventListener("click", function () { goTo(i); });
  dots.appendChild(d);
});
var current = 0;
function goTo(i) {
  var n = PHOTOS.length; i = (i + n) % n;
  track.scrollTo({ left: i * track.clientWidth });
}
function update() {
  var i = Math.round(track.scrollLeft / track.clientWidth) || 0;
  current = Math.max(0, Math.min(PHOTOS.length - 1, i));
  caption.textContent = PHOTOS[current].caption;
  Array.prototype.forEach.call(dots.children, function (d, k) { d.setAttribute("aria-current", k === current ? "true" : "false"); });
}
var ticking = false;
track.addEventListener("scroll", function () {
  if (!ticking) { ticking = true; requestAnimationFrame(function () { update(); ticking = false; }); }
});
document.getElementById("prev").addEventListener("click", function () { goTo(current - 1); });
document.getElementById("next").addEventListener("click", function () { goTo(current + 1); });
track.addEventListener("keydown", function (e) {
  if (e.key === "ArrowLeft") { e.preventDefault(); goTo(current - 1); }
  if (e.key === "ArrowRight") { e.preventDefault(); goTo(current + 1); }
});
window.addEventListener("resize", function () { track.scrollTo({ left: current * track.clientWidth, behavior: "instant" }); });
update();

</script>
</body>
</html>
