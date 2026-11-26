# Cartoon Studio

A native Windows recreation of **The Simpsons Cartoon Studio** (1996) — the
classic cartoon-making game — rebuilt from scratch as a WinForms app, plus a
self-contained asset extractor.

This repo ships **only the extractor**. Everything else (`extracted/`, `app/`,
and the `CartoonStudio.exe` editor itself) is generated locally by running the
extractor against your own copy of the game — no game assets are distributed.

## Requirements

- Windows 10 (1607) or later / Windows 11 (64-bit)
- A copy of *The Simpsons Cartoon Studio* — either the **disc image**
  (`.iso`, `.img`, `.bin`, `.mdf`, `.nrg`, `.cue`) or an **installed game
  folder**
- Nothing else to install — the exe is a self-contained single file
  (~144 MB, .NET runtime bundled)

## Using the extractor on a disc image (ISO)

1. **Download** `CartoonStudio.Extractor.exe` from this repo — open the file
   page and use **Download raw file** (it's stored with Git LFS, so cloning
   also works if you have `git lfs` installed).
2. **Run it** — a window opens with three boxes:
   - *Installed game folder* — leave empty for ISO use
   - *…or disc image (.iso)* — click **Browse…** and pick your disc image
   - *Output folder* — defaults to the folder the exe sits in
3. **Tip:** you can also just **drag the ISO onto the exe** — it opens straight
   into the disc-image box.
4. Click **Extract**. The extractor mounts the disc image, decodes every
   sprite/sound/toon, and writes the finished install:

   ```
   <output>/extracted/   ← decoded PNGs + sounds
   <output>/app/         ← toon data + UI assets
   <output>/CartoonStudio.exe  ← the editor, ready to run
   ```

5. When it finishes, click **Launch CartoonStudio.exe** (or run it yourself) —
   that's the editor.

The disc mounts automatically and is ejected when extraction completes.

## Notes

- Expect a few minutes for extraction depending on disc speed.
- The editor plays and exports your cartoons; all progress saves as toon files
  inside the generated `app/toons/` folder.

## Credits

Faithful reconstruction of the original Macromedia Director-based game
(SIMPMAIN), including its palette banks, record/hold/delete editing model,
Krusty shuttle transport, and sound system — rebuilt as a native .NET 8 app.

Made with [Devin](https://devin.ai) — the AI software engineer from Cognition.
