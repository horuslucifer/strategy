# Source cache notes (written by the main session, 2026-09-23)

Verified dead ends — do not waste calls on these:
- `digitalattic.org/home/war/vegetius/` — the domain has been taken over and now serves online-casino spam. It is NOT a Vegetius text any more. The Wayback copy also failed to return the text.
- `archive.org/download/...djvu.txt` and `archive.org/stream/...` — returned JavaScript shells or "Page Not Found" during this cache build, not text. If you must use archive.org, verify the bytes (`file`, `head`) before trusting them.
- `sacred-texts.com` — behind a Cloudflare interstitial ("Just a moment...").
- Gutenberg ebook 55388 is Graham's Magazine, not Vegetius. Gutenberg 62202 is "The Sabbath, the Crystal Palace, and the People", not Frederick. Do not guess Gutenberg IDs; search the catalogue.
- No free machine-readable English Vegetius was found. The Latin of Books I-III is cached instead (`vegetius_latin*_clean.txt`, from thelatinlibrary.com) and is the better verification source; Clarke 1767 and Milner 1993 wording should be quoted only from a page you actually open.

Always check a downloaded file with `file` and `head` before quoting from it. Several of these URLs return a 200 with an error page or a spam page in the body.

## Added 2026-09-23 (X1 grammar file)
- `jomini_artofwar.txt` — Jomini, *The Art of War*, Mendell and Craighill translation, Project Gutenberg 13549, downloaded from `https://www.gutenberg.org/cache/epub/13549/pg13549.txt`. Verified real text (888KB, UTF-8). Not one of the thirteen canon texts, but Jomini supplies the definitions (strategy / grand tactics / logistics, decisive point, interior and exterior lines, lines of operation) that Clausewitz argues against by name.

Further verified dead ends from that run:
- `press.armywarcollege.edu`, `apps.dtic.mil`, `jcs.mil` and `armypubs.army.mil` all return 403 to curl and to WebFetch. Lykke's 1989 *Military Review* article and the current US/UK doctrinal publications could not be opened; the X1 file marks the affected claims UNVERIFIED.
- `cairn.info` returns 403. DuckDuckGo's html/lite endpoints return 202 with no results; Bing returns unrelated results for "Lykke".
- Crossref's API (`api.crossref.org`) and Open Library's (`openlibrary.org/search.json`) both work without a key and are the cheapest way to confirm a citation's volume/issue/year when the full text is paywalled.

## Added 2026-09-23 (X4 descendants file)

New caches, all byte-checked with `file`/`head` before use:
- `dupicq_battlestudies.txt` — Ardant du Picq, *Battle Studies*, Greely & Cotton trans., Gutenberg 7294.
- `lawrence_seven_pillars_pgau.txt` — Lawrence, *Seven Pillars of Wisdom*, Project Gutenberg **Australia** eBook 0100111 (`gutenberg.net.au/ebooks01/0100111.txt`). Not on US Gutenberg; don't look for it there.
- `mao_on_protracted_war.txt`, `mao_on_guerrilla_warfare.txt` — Marxists Internet Archive, HTML stripped to text. The guerrilla text is Samuel Griffith's translation (in copyright); quote briefly and by chapter.
- `fuller_foundations.txt` — Fuller, *The Foundations of the Science of War* (1926), archive.org item `foundationsofsci00jfcf`. OCR with heavy inter-word spacing: always verify against a whitespace-flattened copy.
- `liddellhart_decisive_wars_1929.txt` — archive.org `decisivewarshistory`. Google-scan OCR; front matter is garbage, body is usable.
- `unrestricted_warfare_cryptome.txt` — Qiao & Wang, FBIS translation, `cryptome.org/cuw.htm`. Full eight chapters. NOTE: the famous "first rule … nothing forbidden" line is in the FBIS editor's note quoting a newspaper interview, NOT in the book.
- `boyd_destruction_and_creation_1976.pdf` + `.txt`, `boyd_patterns_of_conflict_1986.pdf`, `boyd_organic_design_1987.pdf`, `boyd_strategic_game_1987.pdf` — all from `colonelboyd.com/s/…`, which is the working Boyd mirror. Only *Destruction and Creation* has a text layer; the briefings are image scans and must be read as images.
- `moltke_de_wikiquote.html` — German Wikiquote, for the "Kein Operationsplan…" sentence with its *Militärische Werke* II.2 (1900) p. 291 citation.

Further verified dead ends from that run:
- `airuniversity.af.edu` and `media.defense.gov` return 403 to curl AND to WebFetch. The Air University edition of Boyd's *A Discourse on Winning and Losing* is unobtainable by these means.
- archive.org `_djvu.txt` returns 403 for any item whose metadata has `access-restricted-item: true` — check `archive.org/metadata/<id>` first, it is cheap and tells you before you download. `archive.org/stream/…` returns a JavaScript shell with no book text (confirms the note above). Items in `opensource`/`folkscanomy` collections DO serve their text.
- No copy of Beaufre, Wylie or Schelling could be opened anywhere; all are lending-only scans. X4 quotes none of them and says so.
- `tesseract` is NOT installed on this machine, so image-only PDFs cannot be OCR'd; read them with the Read tool's `pages` parameter instead. `pdftotext` (poppler) IS installed at `/opt/homebrew/bin/pdftotext`.
- DuckDuckGo html/lite, Mojeek, the Google Books API and the Semantic Scholar API all refuse or rate-limit automated queries. Direct URL guessing against `.edu` author pages worked where search did not (e.g. Axelrod's own page served the 1981 *Science* paper).
