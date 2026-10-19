---
name: study-skill
description: Turn any study material (photos, notes, PDFs, worksheets, vocab lists) for any subject into a single-file HTML mastery trainer built on retrieval practice, spaced repetition and type-it-out corrections.
---

# Study Skill

Build a self-contained HTML study game from whatever the student uploads (photo of a textbook page, worksheet, notes, PDF, pasted list). It is the same design as the Latin Vocab Trainer: learn in small batches, climb a 3-step mastery ladder, pass a perfect final test, then apply the material, then a bonus reverse round. The audience is a student, so keep the language simple and encouraging.

## Learning science the design is built on (keep every one)

- **Retrieval practice / testing effect** (Roediger & Karpicke 2006; Dunlosky et al. 2013 rate it "high utility"): the student keeps pulling answers from memory instead of re-reading.
- **Spaced repetition** (Cepeda et al. 2006): a missed item returns within 2-3 cards. Items get spaced further apart as their level goes up.
- **Generation effect and desirable difficulty** (Slamecka & Graf 1978; Bjork 1994): the ladder goes recognition (multiple choice) → typed recall → delayed typed recall.
- **Immediate corrective feedback** (Metcalfe 2017): after any miss, show what they typed next to the right answer, then make them **type the correct answer out** before they can continue.
- **Elaborative encoding / mnemonics** (keyword method, Atkinson & Raugh 1975): every item gets a 💡 memory hook, plus related words or examples when they help.
- **Targeting confusions**: easily confused pairs get a ⚠️ warning. Wrong multiple-choice options should be plausible, ideally the item's real look-alikes.
- **Interleaving** (Rohrer & Taylor 2007): mix items from the active pool. Never show the same item twice in a row.
- **Mastery learning** (Bloom): a perfect final test is required to unlock the apply stage. Misses go back to practice.
- **Transfer**: the apply stage uses items in new contexts, not just isolated recall.
- **Motivation**: streak 🔥, best streak, accuracy %, color-coded progress chips, a "toughest items" list, short celebratory messages. Keep it fun but not cluttered.

In the reply, don't overclaim. Say the design uses "well-supported study techniques", not "guaranteed".

## Workflow

1. **Read the material.** For images, use Read to view each photo. For PDFs and docs, extract the text. If an image is blurry or the item list is ambiguous, ask one short question. Otherwise proceed.
2. **Build the item deck.** Each item needs:
   - `q`: the prompt (term, question, or problem)
   - `f`: an optional sub-line (grammatical forms, units, context)
   - `a`: an array of accepted answers. The first is canonical. Include common synonyms and spellings.
   - `h`: a memory hook (vivid, short, age-appropriate)
   - `d`: optional related words or examples
   - `w`: optional ⚠️ confusion warning
   - `mc`: an optional array of 3 plausible distractors. Otherwise pull distractors from other items' answers.
   Pick the item style by subject:
   - Vocab or language: term ↔ meaning.
   - Science or history: question → short fact. Use concept items as "what is X / why does Y".
   - Math: problem → numeric answer. Accept numeric equivalents, and generate a fresh variant on retry if possible.
   - Processes: an ordering question, typed as a short sequence.
   Cover everything in the material. Don't skip items.
3. **Write the apply items** (stage 3). Write 15-25, built mostly from the deck:
   - Languages: sentences to translate, each with a word-by-word gloss.
   - Math: word problems.
   - Science or history: scenario or "explain why" questions with a model answer and the key points.
   The student self-grades against the model answer. If they mark a miss, they type out the model answer, which counts as correct at ≥80% token overlap. The item then returns 3 cards later.
4. **Build the HTML.** Use one file, no external dependencies, structured like this:
   - **Stages:** Learn → Final test → Apply → Bonus reverse (answer → prompt, e.g. English → Latin, or definition → term), then a hub with redo buttons.
   - **Learn:** active pool of 6. A new item first shows an intro card with the answer, hook, and warning, and the student types the answer once. Levels: 1 = multiple choice (number keys 1-4 work), 2 = typed, 3 = typed again later, 4 = mastered. A correct answer goes up one level. A wrong answer goes down one level (minimum 1) and triggers type-it-out. Re-insertion distance by level: L1 2-3 cards, L2 3-5 cards, L3 6-9 cards.
   - **Final test:** all items shuffled and typed, with no feedback until the end, and a perfect score is required. Each miss → a "fix" screen where they type the answer out → back to Learn at level 2.
   - **Answer checking:** lowercase, strip accents/macrons and punctuation, strip leading "to/the/a/an/i". Split the input on , ; / "or". Use Levenshtein tolerance: 0 for answers under 5 characters, 1 for 5-8, 2 for 9 or more.
   - **HUD:** mastered count, streak, best streak, accuracy. A chip grid shows each item's level, with a legend. The 📖 item list overlay (with hooks) is hidden during the final test. A reset button with confirm.
   - **Progress:** save to localStorage, with every read and write in try/catch. Use a unique storage key per subject so trainers don't overwrite each other.
   - **Style:** a warm, clean look with CSS variables, a dark mode via prefers-color-scheme, mobile-friendly at 16px side padding, and Enter to submit/continue everywhere. Title the page after the subject (e.g. "Biology Ch. 4 Trainer").
5. **Test before delivering.** Extract the script and run `node --check`. Then simulate a full run with jsdom: answer mostly right with some wrong answers, complete the type-outs, and step through every stage to the end. Confirm there are no errors.
6. **Deliver.** Send the .html file and write 2-4 short lines on how it works. Point out anything from the material you weren't sure how to read. Don't recap the build steps.