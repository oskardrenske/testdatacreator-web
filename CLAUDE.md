# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Architecture

Single-page web app that generates fictitious Swedish person records (`personnummer`, name, address, postal code, phone). All logic runs in the browser via [PyScript](https://pyscript.net/); the project has no build step and no server-side component.

The entire app — HTML, CSS, Python code, and source data — lives in `index.html`. Source lists (first names, last names, address parts, postal codes, personnummer) are embedded as `<script type="application/json" id="data-...">` blocks and read synchronously by the PyScript code at startup. This keeps the deploy artifact to a single file and avoids CORS/fetch concerns.

Spec lives in `instructions.md` (Swedish). The expected person record shape is documented there and must be kept in sync with `make_person()` inside `index.html`.

## Local development

PyScript needs to be served over HTTP — opening `index.html` via `file://` will not work. Use any static server, e.g.:

```bash
python3 -m http.server 8000
# then open http://localhost:8000/
```

## Deploy

Upload `index.html` to any static web host (SFTP works). Nothing else is needed.

## Editing the source data

The embedded JSON blocks in `index.html` are the source of truth. To regenerate them from external lists, do the conversion separately and paste the resulting JSON into the matching `<script type="application/json">` block — keep one entry per array element, preserving any intentional duplicates (e.g. `address_suffix` weights `gatan` and `vägen` by repeating them).
