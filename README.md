# reel-archive

Saved Instagram reel recommendations, structured for LLM reading. Owner: Shotaro. Human version: https://files.instinct.com/psb3uy828v0d-the-late-night-archive-gallery

## Layout

- `INDEX.md`: one-table overview of every reel.
- `THEMES.md`: every item organised by theme (film, books, archives, web/UI design, AI & dev tools, graphic design & motion, fashion, music, games, ideas, places). Items can belong to more than one theme.
- `data/reels.json`: one record per reel, with id, slug, url, creator, title, summary, saved date, item_ids and file.
- `data/items.json`: flat list of every item, with id, reel, collection, collection_title, title, kind, creator, note, links, image and themes.
- `reels/NN-slug.md`: one file per reel, with front matter and every item written out.
- `assets/`: cover, poster and preview images referenced by image fields.

## Conventions

- Item ids are global and increase by one, currently 1-325. Reels with no identifiable resource have an empty item_ids list; r19 is a process reference and adds no item; r20 adds items 119-121 and r21 adds items 122-125; r22 adds items 126-132 r23 adds items 133-137, r24 names no resource and adds no item, and r25 (a carousel post) adds items 138-143, r26 adds item 144, r27 names no resource and adds no item, r28 adds items 145-153, r29 names no resource and adds no item, and r30 adds items 154-156, and r31 adds items 157-183; r32 adds book item 184, r33 adds items 185-217 (NYC shops), r34 adds items 218-222 (layout sites), and r35 adds items 223-227 (an essay carousel and its four cited books), r36 adds items 228-229 (a song and a game), r37 adds item 230 (an AI prompt library site), r38 adds item 231 (a film), and r39 adds item 232 (a song); r51 adds items 291-292 (a video edit: its likely song and its creator); r52 adds items 293-294 (a video edit: its creator and After Effects); r53 adds items 295-297 (a video edit: its creator, the SFX artist and DaVinci Resolve); r54 adds items 298-304 (a gig promo: the event, four artists, the venue and its creator); r55 adds item 305 (a video edit: its creator's series); r56 adds items 306-312 (six architecture-theory books and a Melbourne bookshop), and r57 adds items 313-320 (the fonderie.download foundry and its seven free fonts), and r58 adds items 321-322 (two new Claude frontend-design tools; three more repeat r13), and r59 adds items 323-325 (a five-technique 'real print' editing recipe, its Mustang-ad demo material and an 1841 'O.K.' newspaper clipping). Reel ids are `rNN`, currently r01-r59.
- `kind` is one of archive-item, film, website, book or lesson.
- Item creator is the director/author; reel creator is on the reel record.
- Notes distinguish checked facts from unverified creator claims.
- Links are reference pages, not availability or rights claims.
- Image uploads carry numeric filename prefixes. Use their exact stored names, as the JSON and markdown do.

## Adding a reel

1. Add a record to `data/reels.json` with the next rNN and NN-short-name slug.
2. Append items to `data/items.json` with the next ids.
3. Create `reels/NN-slug.md` and upload any images to `assets/`.
4. Check the actual stored filenames and use them in every image/file reference.
5. Add a row to `INDEX.md` and read back the saved JSON to check counts and links.

The latest reels are r54-r59 (r54-r58 saved 2026-11-07, r59 saved 2026-11-08). The repository is public since 2026-11-05; the hosted gallery still covers only the earliest reels.

## Book contents

The six menswear items (38-43) now have optional `contents` objects in data/items.json, mirrored in reels/04-menswear-books.md. These record verified chapter lists or coverage summaries, sources, edition/source caveats and checked date. They do not contain full book texts. Modern Black Tie has a verified ten-chapter structure but not exact chapter names; Savile Row and The Italian Gentleman retain source discrepancies rather than invented harmonized contents.

Reels 10-16 were added to this repository only; the hosted gallery was not changed by this update.

## Substantive book notes

Items 38-43 and 306-311 have optional `knowledge` objects mirrored in the reel markdown pages: scope, checked date, depth, limits, sections (section, evidence, source_ids, summary) and sources (id, title, url, type). Direct book excerpts, established reviews, lower-confidence reader notes and author-site companion guides remain distinct. Missing chapters are marked. No full text or preview images are stored, and no percentage of knowledge recovered is claimed. `contents` remains the table-of-contents field.

