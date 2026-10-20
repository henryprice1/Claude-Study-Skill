# Claude Study Skill

A Claude skill that turns your study material (a photo of a textbook page, a worksheet, notes, a PDF, or a vocab list) into a study game. The game is one HTML file that works in any browser, on a computer or a phone. Works for any subject.

👉 **[Try the live Latin example](latin-example.html)**

## Install


1. Download **[study-skill-v2.zip](study-skill-v2.zip)** (latest). The older version is still here as [study-skill-v1.zip](study-skill-v1.zip).
2. In Claude, go to **Customize → Skills** ([claude.ai/customize/skills](https://claude.ai/customize/skills)).
3. Click **+**, then **Create skill**, then **Upload a skill**, and choose the zip.
4. Make sure the skill is toggled **on**. Skills also need **Code execution and file creation** turned on in Settings → Capabilities.

If you already have v1 installed, turn it off (or delete it) so Claude uses v2.

More detail: [Use Skills in Claude](https://support.claude.com/en/articles/12512180-use-skills-in-claude).

## Use it

Start a chat, attach your material, and say:

> Make a study trainer from this.

Examples:

- *"Make a study trainer from this photo of my biology vocab."*
- *"Here are my Spanish chapter 5 words. The apply stage should be sentences."*
- *"Make a study trainer from these history notes. My test is Friday."*

Claude sends back an `.html` file. Open it in your browser and start studying.

**Tips:** learn a little each night, do your reviews when the app says cards are due, use ⚡ Cram the night before a quiz (then sleep!), and back up your progress with ⚙️.

## What's new in v2

- Every item is learned **both ways**: prompt → answer, and answer → explain it in your own words.
- **Cram mode** for the night before a test, plus a morning check of what you missed.
- **Long-term reviews** spaced out over days (Anki-style), and a 📅 test date so everything is reviewed in time.
- "Sure" vs. "Just guessing" answers, write-your-own memory hooks, a daily streak, and backup/restore codes.

## Files

```
README.md            ← this page
index.html           ← the GitHub Pages home page
study-skill-v2.zip   ← the skill (latest), upload this to Claude
study-skill-v1.zip   ← the original version
latin-example.html   ← an example trainer
```
