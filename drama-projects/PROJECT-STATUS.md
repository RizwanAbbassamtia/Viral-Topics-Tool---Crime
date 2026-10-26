# Drama Projects — Status & Handoff

Handoff from the old Claude profile (Fable limit reached, resets Oct 30, 8:00 AM) to the new profile.
Everything below was rebuilt from the last messages of the old sessions (around Oct 25–26, 2026).
**Check it against the files on disk before acting on it.**

---

## 1. The four projects

| Project | Folder on laptop | Old session name |
|---|---|---|
| English Drama (parent) | `F:\YT DX\English Drama` | English Drama |
| Spanish Drama | `D:\YT DX\Spanish Drama` | Spanish Drama (fork) |
| Portuguese Drama | `D:\YT DX\Portuguese Drama` | Portuge Drama (fork) |
| Russian Drama | `D:\YT DX\Russian Drama` | Russian Drama (fork) |

There was also an **editor** session that renders the videos. It took instructions only from the English parent session.

---

## 2. Rules all sessions agreed on

1. **Order:** English finishes first, then Spanish, then Portuguese, then Russian.
   No Omni / OmniFlow generation for a language until the previous language is reported complete.
2. **Writing is allowed while waiting.** Only tool generation waits its turn; stories, scene tables and prompt files can be written at any time.
3. **Scene generation in OmniFlow comes first, rendering later.** If credit runs low, finish generation and postpone rendering.
4. **English belongs to the English parent session only.** No other session runs scripts against English folders.
   The parent's file server on **port 8765** is the only one that should be running.
5. **Ask before deleting anything.** Old drafts go to the Recycle Bin, never deleted outright.
6. **Save credit:**
   - Background scripts with one report file per film. No polling or watching renders.
   - Send one message per film, not running commentary.
   - The editor runs on **Sonnet, medium effort**, with one chained batch job per film.
   - Encoder: **libx264 `veryfast`** (2.7× faster under load). NVENC does not work on this laptop; Quick Sync was slower.

---

## 3. Status per language

### English: 5 films, 0 ready to upload
Stories, scene tables and prompt files are complete for all five films.
Clips are complete except **No Filter S100**, which the parent was re-submitting.

| Film | Latest known state |
|---|---|
| The Blind Billionaire | v3 (teaser opening) rendered; 4:2:0 re-encode about half done |
| The Buka Girl | v3 rendered; 4:2:0 re-encode started, content QC running |
| The Night Driver | v4 render in progress |
| No Filter | Queued after Night Driver; waiting on clip S100 |
| My Mother's Shop | Queued last |

- The v2 / v2a drafts of the three finished films (3.77 GB) are in the **Recycle Bin**. They can be restored until the bin is emptied.
- **Known bug:** a stray `F:\c\...` folder tree was created by the parent's own `collect_by_batch.py` run (23:09), where a `/c/Users/...` path was resolved against the F: drive.
  Use Windows paths (`C:\Users\...`) in that script. The C: clip folders are complete except S100.
- The parent re-downloaded My Mother's Shop clips into a private folder `Clips_en_main`. The 124 extra files in the Shop clips folder are fine.
- Next steps: finish the 4:2:0 re-encodes and QC, render Night Driver, get S100, render No Filter and My Mother's Shop, then send the "all English verified" message.

### Spanish: frameworks done, 1 film written
- `D:\YT DX\Spanish Drama\Frameworks`: four framework documents (study, titles, script, prompts).
- **Tractor Viejo** is fully packaged: blocks, beat sheet, scene table, prompts file, SEO, thumbnail, music plan and description. Its clip folder is empty because generation waits for English.
- The other Spanish films (2 more, plus 2 extra planned) are not on disk yet. The last instruction was to write them.
- When Spanish generation is done, give Portuguese its go signal.

### Portuguese: research done, 4 films being written
`D:\YT DX\Portuguese Drama` contains the channel study, three channel lists, the title corpus, ten raw transcripts, three frameworks (titles, script, Omni prompts) and the shared music.
The assembler opens each film with a **19-second teaser**. Each film is about **18 minutes** long.

| # | Title | Folder | State |
|---|---|---|---|
| 1 | Riram do Idoso Que Pediu 30 Centímetros de Tecido — Até Ele Abrir a Pasta | `Films\30 Centímetros de Tecido` | Being written |
| 2 | Negaram Água ao Compositor de 81 Anos no Barracão… Até a Presidente Trazer o Samba de 78 | `Films\O Samba de 78` | Being written |
| 3 | Negaram Água à Idosa no Hotel… Sem Saber o Que Ela Vinha Assinar | `Films\Água no Hotel` | Being written |
| 4 | Riram da Almofada Barulhenta da Rendeira de 78 Anos… Até a Dona da Fábrica Ver o Risco | `Films\A Rendeira de 78 Anos` | Scene table, character blocks and prompts landed, being checked |

- The 1.45M-view guitar Short was skipped because it is the same story as film 2.
- Next steps: check which of the four packages are complete on disk, finish the rest, then hold generation until Spanish is done.

### Russian: not started
- `D:\YT DX\Russian Drama` was created empty. Nothing has been researched or written yet.
- Next steps: the same pipeline as Portuguese (channel study, then titles, then frameworks, then four film packages). Generation comes last in the queue.

---

## 4. Warning about the old profile
The old sessions set a **check-in every 2 hours for 7 days**. They will wake up again when the old limit resets on **Oct 30, 8:00 AM**.
If the old sessions and the new ones both work on the same folders, they will clash.
On Oct 30, open the old profile, tell each old session to **stop and cancel its scheduled check-ins**, or simply don't use the old profile any more.

---

## 5. How to restart each project in the new profile
1. Claude desktop app → sign in with the new profile → **Code** → **New session** → environment **Local** → **Select folder** → pick the project folder from the table in section 1.
2. Copy this file into that folder.
3. Paste the message below, changing the language name:

```
This is my <LANGUAGE> Drama project. The previous sessions ran out of credit, so continue from here.
1. Read CLAUDE.md, PROJECT-STATUS.md, Frameworks\, tools\ and any report or status files in this folder.
2. Check PROJECT-STATUS.md against what is actually on disk and tell me the real status of every film:
   story, scene table, prompts, clips, render, QC, ready to upload.
3. Follow the rules in section 2 of PROJECT-STATUS.md: language order, ask before deleting, low credit use.
4. Then continue the next steps listed for <LANGUAGE> in PROJECT-STATUS.md.
```

Start **English first**. It is the parent and the other languages wait for it.
