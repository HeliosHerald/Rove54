ROVE 54 — FILE GUIDE
====================

STRUCTURE
---------
style.css                — all colors and fonts. Edit here to change the look everywhere.
sigil.svg                — replace with your commissioned artwork (keep the filename).
index.html               — front page: intro, all six seal clues, info section.

s/location-1/            — sticker location 1
s/location-2/            — sticker location 2
s/location-3/            — sticker location 3
s/location-4/            — sticker location 4
s/location-5/            — sticker location 5
s/location-6/            — sticker location 6

complete/                — the final gate page (checks all cookies, reveals Discord)


WHAT TO EDIT ON THE FRONT PAGE (index.html)
--------------------------------------------
Search for [PLACEHOLDER] — every editable section is marked.

1. Intro text       — the Order's opening address. 3-5 sentences. Solemn, cryptic.
2. Seal IV clue     — not yet provided. Add it in the Seal IV box.
3. Contact email    — replace [PLACEHOLDER@email.com] with your real address.


WHAT TO EDIT ON EACH LOCATION PAGE (s/location-N/index.html)
-------------------------------------------------------------
Search for [PLACEHOLDER] — every editable section is marked.

1. Flavor text      — the Order speaking about this specific place. 1-2 sentences.
2. Fragment code    — replace [XX] with the real number (e.g. 07).
   The six fragments together form the combination lock code.


WHAT TO EDIT ON THE COMPLETION PAGE (complete/index.html)
----------------------------------------------------------
Search for [PLACEHOLDER] — every editable section is marked.

1. Congratulatory message   — the Order speaks. Solemn. 2-3 sentences.
2. Discord invite URL       — replace # in href="#" with your real invite link.
3. Failure message          — the Order speaks when seals are still missing.
                              The number of remaining seals is injected automatically.


RENAMING LOCATION FOLDERS (important before going live)
--------------------------------------------------------
The folder name becomes part of the URL. Right now they are:
  yoursite.com/s/location-1/

Rename each folder to something obscure and non-guessable, e.g.:
  yoursite.com/s/kestrel/
  yoursite.com/s/irongate/
  yoursite.com/s/vesper/
  yoursite.com/s/warden/
  yoursite.com/s/halcyon/
  yoursite.com/s/dulwich/

After renaming, you must update two things:
  1. The cookie name in each location page's <script> tag.
     e.g. change "location_1" to "kestrel" to match the folder.
  2. The SEALS array in complete/index.html.
     It must list all six cookie names exactly as set in the location pages.


PREVIEWING LOCALLY
------------------
Opening HTML files by double-clicking will not show styles correctly —
the relative CSS paths only work when served from a server.

To preview locally, run this in Terminal from inside the rove54 folder:
  python3 -m http.server 8000

Then open http://localhost:8000 in your browser.

Alternatively, use VS Code with the Live Server extension.


GOING LIVE ON GITHUB PAGES
----------------------------
1. Create a free account at github.com
2. Create a new repository (click +, name it anything, set to Public)
3. Upload the entire rove54 folder contents (not the folder itself — its contents)
4. Go to repository Settings → Pages → set source to "main branch / root"
5. Your URL will be: yourusername.github.io/repositoryname/

NFC chips should be programmed to the full URL of each location page, e.g.:
  yourusername.github.io/repositoryname/s/kestrel/

The completion page URL to share or link to (if needed):
  yourusername.github.io/repositoryname/complete/


COOKIE LOGIC
------------
Each location page sets a cookie the moment it loads.
Cookies are stored on the participant's device and browser.
The completion page checks for all six cookies before revealing the Discord invite.

Important notes for participants (already listed on the front page):
  - Use the same device throughout
  - Do not clear browser cookies until complete
  - Seals can be found in any order


COMBINATION LOCK
----------------
The six fragment codes ([XX] on each location page) together form
the combination to the physical lock on the final box.
Decide your six digits and fill them in before going live.
A four-digit lock requires four fragments total — adjust if needed.
