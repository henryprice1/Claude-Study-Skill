# Claude Study Skill

**Claude Study Skill** is a skill for Claude that works with any subject. You upload your study material and Claude builds a study game from it. The material can be a photo of a textbook page, a worksheet, notes, a PDF, or a vocab list. The game is a single HTML file that works in any browser, on a computer or a phone.

Works for any subject: languages, science, history, math, vocab, definitions, dates, formulas.

👉 **[Try the live Latin example](examples/latin-vocab-trainer.html)**

## What you get

Each trainer takes you through four stages:

1. **Learn.** Items come in small groups of about 6. Each one climbs a 3-step ladder:
   - pick the answer from multiple choice,
   - type it,
   - type it again a few cards later.

   If you miss one, you see what you typed next to the right answer, and you have to **type the correct answer out** before moving on.
2. **Final test.** Every item, shuffled, with no hints. You need a perfect score to unlock the next stage. Anything you miss goes back to practice.
3. **Apply.** You use the material in new examples. These can be sentences to translate, word problems, or "explain why" questions, depending on the subject.
4. **Bonus.** The reverse direction, for example English → Latin, or definition → term.

Along the way you get memory tricks 💡, warnings for easily confused items ⚠️, streaks 🔥, accuracy, and a list of your toughest items. Progress saves automatically in your browser.

## The learning science behind it

| Technique | What the trainer does | Research |
|---|---|---|
| Retrieval practice | Keeps testing you instead of letting you re-read | Roediger & Karpicke, 2006; Dunlosky et al., 2013 |
| Spaced repetition | Missed items come back soon, and known items come back later | Cepeda et al., 2006 |
| Desirable difficulty / generation | Multiple choice first, then typed recall | Bjork, 1994; Slamecka & Graf, 1978 |
| Corrective feedback | Type out the right answer after every miss | Metcalfe, 2017 |
| Mnemonics | A memory hook for every item | Atkinson & Raugh, 1975 |
| Interleaving | Items are mixed, never the same one twice in a row | Rohrer & Taylor, 2007 |
| Mastery learning | You need a perfect test before moving on | Bloom, 1968 |

## Install the skill in Claude

1. Download **[study-skill.zip](study-skill.zip)**.
2. In Claude, go to **Customize → Skills** ([claude.ai/customize/skills](https://claude.ai/customize/skills)).
3. Click **+**, then **Create skill**, then **Upload a skill**, and choose the zip.
4. Make sure the skill is toggled **on**. Skills also need **Code execution and file creation** turned on in Settings → Capabilities.

For more detail, see Anthropic's guide: [Use Skills in Claude](https://support.claude.com/en/articles/12512180-use-skills-in-claude).

## Use it

Start a chat, attach your material, and say:

> Make a study trainer from this.

Some examples:
- *"Make a study trainer from this photo of my biology vocab."*
- *"Here are my Spanish chapter 5 words. Make a study trainer, and the apply stage should be sentences."*
- *"Make a study trainer from these history notes, focused on dates and causes."*

Claude sends back an `.html` file. Open it in your browser and start studying.

## Put your own trainers on this site (optional)

1. Save the `.html` file Claude made into the `examples/` folder of this repo. Use a clear name, like `examples/biology-ch4.html`.
2. Add a link to it in `index.html` under "Example trainers".
3. Commit. GitHub Pages updates in a minute or two.

## What's in this repo

```
index.html                         ← the GitHub Pages home page
study-skill/SKILL.md             ← the skill itself
study-skill.zip                  ← the same skill, zipped for upload to Claude
examples/latin-vocab-trainer.html  ← an example trainer
```
