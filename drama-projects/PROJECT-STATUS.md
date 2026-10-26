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

### English: all 5 films complete ✅
The user confirmed that **all English videos are completed**.

| Film | State |
|---|---|
| The Blind Billionaire | Complete |
| The Buka Girl | Complete |
| The Night Driver | Complete |
| No Filter | Complete |
| My Mother's Shop | Complete |

- Next steps: confirm that each final file opens and plays, then upload. Uploading is not done yet unless stated otherwise.
- The v2 / v2a drafts (3.77 GB) are in the **Recycle Bin**. Empty it only after the finals are uploaded.
- **Known bug for later languages:** `collect_by_batch.py` once resolved a `/c/Users/...` path against the F: drive and created a stray `F:\c\...` folder. Use Windows paths (`C:\Users\...`) when running it.
- Because English is done, **Spanish generation may start now**.

### Spanish: in progress, some videos already done
**Update from the user:** some Spanish videos have been updated since the notes below were written.
The new session must check `D:\YT DX\Spanish Drama\Films` to see which films are written, generated, rendered or uploaded. The notes below are older.

- `D:\YT DX\Spanish Drama\Frameworks`: four framework documents (study, titles, script, prompts).
- **Tractor Viejo** is fully packaged: blocks, beat sheet, scene table, prompts file, SEO, thumbnail, music plan and description. Its clip folder is still empty. English is complete, so its OmniFlow generation can start now.
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

English is complete, so start **Spanish** first. Portuguese comes next, then Russian.
