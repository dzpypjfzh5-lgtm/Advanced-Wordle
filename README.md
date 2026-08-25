# Set Down This

A quiet word game for **HSC English Advanced (NSW)**. One self-contained
`index.html` — no build step, no dependencies, no network. Open it in a browser
and it works, including offline.

The title is Eliot's, from *Journey of the Magi*.

## The categories

Five, one per module plus two for the metalanguage. Thirty answers each: six
words at every length from four to eight letters.

| Category | Drawn from |
| --- | --- |
| Texts and Human Experiences | Arthur Miller, *The Crucible* |
| Textual Conversations | Shakespeare, *The Tempest* & Atwood, *Hag-Seed* |
| Critical Study of Text | Poetry of T. S. Eliot — *Prufrock*, *Preludes*, *Rhapsody on a Windy Night*, *The Hollow Men*, *Journey of the Magi* |
| Techniques and Forms | Devices, form and prosody |
| Modules and Rubric | Syllabus and marking language |

Answers are characters, places, key words from the prescribed quotations, and
the analytical vocabulary the rubrics ask for. Proper nouns are welcome — a
dictionary check would reject more than it caught, so any correctly-sized
string of letters is a legal guess.

The Craft of Writing module has no prescribed text and is deliberately out of
scope.

## Playing

- Longer words earn more guesses: 6 tries up to five letters, 7 up to seven, 8
  for eight-letter words.
- **Modules** picks the category and pins a word length, or leaves it at Any.
- **Found** shows every answer in every category, grouped by length, with the
  ones you haven't reached yet masked.
- **Progress** keeps play counts, win rate, streaks and a guess distribution,
  both overall and per category.
- Progress is stored in `localStorage` under the `setDownThis:` prefix. If
  storage is unavailable the game still plays; it just won't remember.

## Editing the word lists

Everything is derived from the data. Append an entry to `CATEGORIES` and a
matching array to `WORDS` under the same id, and the length picker, the guess
distribution, the progress card and the found list all adapt. Add a matching
entry to `GLYPHS` for its icon; without one the category simply shows no icon.

Don't reuse an id, and don't rename one — a rename orphans that category's
saved progress (it is preserved in storage rather than deleted, so restoring
the old id brings it back).

A console-only audit runs on load and warns about lists that aren't plain A–Z,
words repeated within or across categories, uneven category totals, and
`WORDS` entries with no matching category. It never blocks play.

## Sources

The word lists were built from teacher reference documents for the three
prescribed texts. Quotations and terminology should be checked against the
prescribed editions before any classroom or examination use.
