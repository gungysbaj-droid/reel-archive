reel-archive

Saved Instagram reel recommendations, extracted into a structure meant for LLM reading. Owner: Shotaro. Source of truth for the human version: a private hosted page ("The late-night archive gallery").

Layout
INDEX.md - one-table overview of every reel.
data/reels.json - one record per reel: id, url, creator, title, summary, saved date, item_ids, file.
data/items.json - flat list of every item (id, reel, collection, title, kind, creator, note, links[], image).
reels/NN-slug.md - one file per reel, with front matter and every item written out.
assets/ - cover/poster/preview images referenced by image fields.
Conventions
Item ids are global and increase by one (currently 1-58). Reel ids are rNN.
kind is one of: archive-item, film, website, book, lesson.
creator on an item is the director/author; the reel creator is on the reel record.
Notes mark what was checked and what was not. Treat unchecked claims as unverified.
Links are reference pages, not availability or rights claims.
Adding a reel
Add a record to data/reels.json (next rNN, slug NN-short-name).
Append its items to data/items.json with the next ids.
Create reels/NN-slug.md in the same shape as the others and add images to assets/.
Add a row to INDEX.md.

## Storage notes

The archive page: https://files.instinct.com/psb3uy828v0d-the-late-night-archive-gallery

Legacy image uploads carry numeric filename prefixes. The image fields and reel markdown refer to their actual names; preserve those references when appending. The two latest records are r08 and r09, saved 2026-10-11.
