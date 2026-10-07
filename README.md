# sigla
Sigla is a textual collator to compare states of literary texts
# Sigla

A collator for the witnesses of a text: variants, transpositions and an apparatus, in verse or prose.

Sigla compares two or more versions of a poem or prose passage and shows where they differ, line by line and word by word. It is one web page. There is nothing to install and no server: open it in a browser and paste in your texts.

**Use it:** https://drmarsden.github.io/sigla/

Or download `index.html` from this repository and open it in any current browser.

## What it does

- **Reads pasted transcriptions.** Paste each witness into its own box, or paste several at once under header lines beginning `Text:`. Sigla strips page and column markers, joins wrapped turnover lines, rejoins words hyphenated across them, removes stanza numbers, and detects titles. It tells you what it removed.
- **Shows the base text with every variant marked.** Substantive variants and accidentals are marked differently. Lines a witness lacks, adds or has elsewhere are noted in the margin.
- **Shows the witnesses side by side,** with threads joining each line to the same line in the next witness, so moved, new and dropped lines are visible at a glance.
- **Builds an apparatus** in the usual form (`lemma] sigla; reading sigla`), with each reading classed as substantive or accidental. You can change any class and attach notes.
- **Detects transpositions** of whole lines or paragraphs and reports them as moves, not as a deletion and an insertion.
- **Flags its own doubtful decisions.** Line matches that are weak, ambiguous or made by position alone are listed with the reason, and you can correct any match by hand.
- **Exports** a printable edition (web page), TEI XML in parallel segmentation, and a Markdown briefing that gives an AI model the whole collation in one file.
- **Saves** collations in the browser, or as a file or text you can move between machines.

A built-in example (three texts of Poe's "The City in the Sea") loads from the opening screen.

## How it works

1. Each witness is tidied and divided into units: lines for verse, paragraphs for prose.
2. Each witness is matched to the base text separately. Units are paired by how many words they share, with rarer words counting for more, keeping the order of the text.
3. Leftover units are then tested as lines split or run together, as lines moved elsewhere, and as lines revised in place.
4. Within each matched pair, words are compared by longest common subsequence.
5. A reading is classed as accidental when it differs from the base only in punctuation, capitals, word division, accents, or `-ed` against `'d`. Everything else is substantive.

By default, all dash forms are treated as one and curly and straight quotation marks as the same. These and the other tidying steps can be switched off under Settings, and every one applied is listed in the generated note on the text.

## Limits

- **It is base-centred.** Each witness is compared with the base text on its own. Sigla does not build a single alignment of all witnesses, as CollateX does. Two witnesses are grouped only when their readings are identical.
- **It is strongest on verse.** In prose, a sentence moved inside a paragraph appears as a cut and an insertion.
- **Line matching is a heuristic.** It can pair the wrong lines, especially refrains and heavily rewritten lines. Check the flagged matches.
- **A reading is only as good as the transcription.** Check surprising readings against the source.
- **Size.** Poems, stories and chapters are comfortable. Witnesses above roughly 2,800 lines are refused.
- **The TEI export** is well-formed XML but has not been validated against the TEI schema.

## What it has been tested on

Sigla has been run on five texts of Poe's "The City in the Sea" (from the Edgar Allan Poe Society of Baltimore) and five editions of Whitman's "To You" (from the Walt Whitman Archive), plus small invented prose cases. It has not been compared with Juxta or CollateX on the same texts, and its results have not yet been checked against a published variorum. Treat it as a new instrument.

If you have a set of witnesses that defeats it, please send it. Hard cases are the most useful thing a user can contribute.

## How it was made

Sigla was written in October 2026 by Claude, an AI model made by Anthropic, in conversation with Steve Marsden. Marsden supplied the purpose, the scholarly conventions and the test texts, and judged the results; he did not write the code or review it line by line. A second AI model reviewed the design against Juxta's and proposed three of the later changes. A chronology of the build, recording who asked for what and what failed, is available from the author.

The project follows Marsden's "Texts and Transformission: Teaching American Literature with Juxta," *Teaching American Literature* 4:2 (Winter 2011): 38–52. Juxta is no longer maintained.

## Privacy

Your texts stay in your browser. Sigla sends nothing to a server. The page requests two typefaces (Literata and Source Sans 3) from Google Fonts and falls back to system fonts if they are unavailable. It uses no other outside code.

## Citing

Marsden, Steve, and Claude. *Sigla: A Collator for the Witnesses of a Text*. 2026. https://YOUR-USERNAME.github.io/sigla/

DOI: (to be added)

## Licence

MIT. See `LICENSE`.

## Contact

Steve Marsden, Stephen F. Austin State University. dr.marsden@gmail.com
