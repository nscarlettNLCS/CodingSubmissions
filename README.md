# Python Workspace with Code History

An AI-free Python editor for students that records how code is written, plus a teacher page for replaying it.

- `index.html` — the student editor. Python runs in the browser (no install, works on Chromebooks).
- `teacher.html` — load students' `.pyhist.json` files to see flags, a timeline and a step-by-step replay.
- `starters/` — optional starter code files for tasks.

## Put it online (GitHub Pages)

1. Create a new public repository on GitHub, e.g. `py-workspace`.
2. Click **Add file → Upload files** and drag in `index.html`, `teacher.html`, `README.md` and the `starters` folder. Commit.
3. Go to **Settings → Pages**, set **Source** to *Deploy from a branch*, choose `main` and `/ (root)`, and save.
4. After a minute or two the site is live at `https://YOUR-USERNAME.github.io/py-workspace/`.

## Making a task link

Open `teacher.html` on your site and use **Make a task link**. Links look like:

```
https://YOUR-USERNAME.github.io/py-workspace/index.html?task=Y10%20Password%20Checker&starter=starters/password.py&nopaste=1
```

- `task` — the task name students see (also used to keep their work separate per task).
- `starter` — optional path to a `.py` file in the repository.
- `nopaste=1` — optional; blocks pasting from outside the editor (copy and paste within the editor still works).

## Student routine

1. Open the task link and type their full name.
2. Work normally. Work autosaves in the browser.
3. At the end of each lesson, click **Save work** and upload the `.pyhist.json` file to Google Classroom.
4. On a different computer, use **Open saved work** to continue from their last file. The history carries on.

## What the teacher page shows

- **Summary table** for the whole class, sortable, with flags.
- **Timeline**: typing (blue), pastes from outside (red), runs (green/orange), time away from the page (grey), new sessions (dashed).
- **Replay**: scrub or play the code being written. Code pasted from outside stays highlighted in red, even if it was later cut and re-pasted or deleted and undone.
- **Key moments** list: pastes (with the pasted text), leaving the page, errors, sessions, saves.

Flags are prompts for a conversation, not proof. Things to look at:

- A large share of the final code pasted from outside.
- Text appearing in one go without a paste (can indicate a browser extension inserting code).
- Smooth, uncorrected typing straight after returning to the page (can indicate copying from another screen).
- A checksum mismatch (the save file was edited by hand).

## Limits

- The checksum catches casual editing of save files, not a determined forger who reads the source code.
- A student can still retype code from another device; the replay usually makes this visible (no hesitation, no errors, no restructuring).
- An infinite loop freezes the tab. Reloading is safe: work autosaves and reopens.
- `input()` uses a pop-up box. `turtle` and `tkinter` are not supported. `pandas`, `numpy` and `matplotlib` work (first import takes a few seconds; charts appear in the output).
- Needs access to `cdnjs.cloudflare.com` and `cdn.jsdelivr.net`. If the school filter blocks these, ask IT to allow them.
- Nothing is uploaded anywhere: all data stays in the student's browser and the files they hand in.
