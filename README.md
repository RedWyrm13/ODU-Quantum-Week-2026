# QSA Quantum Week Hackathon: Challenges

Welcome! No quantum experience needed. Everything here runs on a quantum **simulator** on your own laptop, using Qiskit.

## How to start

1. Open `00_warmup_quantum_basics.ipynb` and run the first code cells. If you see "Setup complete," you're ready.
2. Work through the warmup (about 45 minutes).
3. Your team picks **one** challenge below and opens its notebook.

Using Google Colab instead? Upload the notebook, then re# QSA Quantum Week Hackathon: Challenges

Welcome! No quantum experience needed. Everything here runs on a quantum **simulator** using Qiskit, either in VS Code on your own laptop or in Google Colab.

**Before the event:** finish Steps 1 and 2 below, and make sure the setup cell in `00_warmup_quantum_basics.ipynb` prints "Setup complete." If anything goes wrong, contact the organizer before the event so we can start building right away.

---

## Step 1: Make your team's copy (fork)

Your team works in its own copy of this repository, called a **fork**. The organizer looks at your fork to see your final submission.

**One fork per team.** One person (the "team captain") does this:

1. Sign in to [GitHub](https://github.com) (make a free account if you need one).
2. At the top of this repository's page, click **Fork**.
3. Leave the name as it is, then click **Create fork**.
4. You now have a copy at `https://github.com/YOUR-USERNAME/REPO-NAME`. This is the link you'll submit.

**Your fork must stay public** so the organizer can see it. Forks of a public repository are public automatically. Do **not** use "Use this template," and do not download the files and re-upload them to a new private repository.

**Add your teammates** so everyone can save work to the same fork:

1. In your fork, go to **Settings → Collaborators → Add people**.
2. Add each teammate by GitHub username or email.
3. Each teammate accepts the invite from their email or GitHub notifications.

Working solo? Just fork it and skip the teammates part.

---

## Step 2: Choose your setup

Pick **one** option:

| | Option A: VS Code on your laptop | Option B: Google Colab |
| --- | --- | --- |
| Install anything? | VS Code, Python, and Git | Nothing |
| Works offline? | Yes | No |
| Best for | Most people | Chromebooks, or if Option A gives you trouble |

### Option A: VS Code with a virtual environment

You'll write and run everything inside **VS Code**, a free code editor. A **virtual environment** is a private folder of Python packages just for this project, so it can't clash with anything else on your computer.

#### A1. Install the tools (one time only)

Install these three things, in this order:

1. **VS Code.** Download it from [code.visualstudio.com](https://code.visualstudio.com/) and install it.
2. **Python 3.10 or newer.** Python 3.12 is a safe choice. Download it from [python.org/downloads](https://www.python.org/downloads/).
   - **Windows:** on the first installer screen, check **"Add python.exe to PATH"** before clicking Install.
   - **Mac:** use the python.org installer.
   - **Linux:** Python is usually already installed. On Ubuntu or Debian, also run `sudo apt install python3-venv`.
3. **Git.** Download it from [git-scm.com/downloads](https://git-scm.com/downloads). On a Mac, you can instead run `xcode-select --install` in the Terminal app.

**Restart your computer after installing**, so VS Code can find Python and Git.

#### A2. Add the VS Code extensions (one time only)

1. Open VS Code.
2. Click the **Extensions** icon in the left sidebar (four small squares), or press **Ctrl + Shift + X** (Mac: **Cmd + Shift + X**).
3. Search for **Python** and install the one published by **Microsoft**.
4. Search for **Jupyter** and install the one published by **Microsoft**.

#### A3. Clone your fork

Cloning downloads your fork to your computer. Use **your fork's** link, not the original repository's link.

1. In VS Code, press **Ctrl + Shift + P** (Mac: **Cmd + Shift + P**) to open the Command Palette.
2. Type **Git: Clone** and press Enter.
3. Paste your fork's link, `https://github.com/YOUR-USERNAME/REPO-NAME.git`, and press Enter.
4. Pick a folder to save it in (Documents is fine).
5. When VS Code asks, click **Open**. If it asks whether you trust the authors, click **Yes, I trust the authors**.

You should now see the notebooks listed in the **Explorer** sidebar on the left.

#### A4. Create the virtual environment and install Qiskit

1. In VS Code, open a terminal: **Terminal → New Terminal** in the top menu. It opens at the bottom of the window, already inside your project folder.
2. Copy the commands for your operating system into the terminal, one line at a time, pressing Enter after each.

**Windows**

```powershell
py -m venv .venv
.venv\Scripts\Activate.ps1
python -m pip install --upgrade pip
python -m pip install "qiskit[visualization]==2.6.1" ipykernel
```

If you see "running scripts is disabled on this system," run this once, then try `.venv\Scripts\Activate.ps1` again:

```powershell
Set-ExecutionPolicy -Scope CurrentUser RemoteSigned
```

If `py` isn't found, use `python -m venv .venv` instead.

**Mac**

```bash
python3 -m venv .venv
source .venv/bin/activate
python -m pip install --upgrade pip
python -m pip install "qiskit[visualization]==2.6.1" ipykernel
```

**Linux**

```bash
python3 -m venv .venv
source .venv/bin/activate
python -m pip install --upgrade pip
python -m pip install "qiskit[visualization]==2.6.1" ipykernel
```

When the environment is active, the terminal prompt starts with `(.venv)`. The install takes a few minutes. If VS Code pops up a message asking whether to use the new environment for this workspace, click **Yes**.

#### A5. Connect the notebooks to your environment

1. In the Explorer sidebar, click `00_warmup_quantum_basics.ipynb` to open it.
2. Click **Select Kernel** in the top-right corner of the notebook.
3. Choose **Python Environments**, then pick the one marked **.venv**.
4. Click the setup cell and press **Shift + Enter** to run it.

When you see **"Setup complete,"** you're ready. VS Code remembers this choice, so you only do it once per notebook. If a notebook ever shows a different kernel name in the top-right corner, click it and choose **.venv** again.

#### A6. Every time you come back

Open VS Code. Your project usually reopens automatically; if not, use **File → Open Recent** and pick `REPO-NAME`. Open a notebook and start running cells. You don't need to reinstall anything or reactivate the environment to run notebooks.

### Option B: Google Colab (nothing to install)

You need a Google account. Each notebook is opened separately.

1. Go to [colab.research.google.com](https://colab.research.google.com).
2. Click **File → Open notebook**, then choose the **GitHub** tab.
3. Paste **your fork's** link (`https://github.com/YOUR-USERNAME/REPO-NAME`) and press Enter.
4. Click the notebook you want, starting with `00_warmup_quantum_basics.ipynb`.
5. In the second code cell, delete the `#` at the start of the `!pip install` line, then run that cell. It takes about a minute.
6. Run the setup cell. When you see **"Setup complete,"** you're ready.

Colab forgets installed packages when your session ends. Every time you reopen a notebook, run the `!pip install` cell again first.

**Important:** Colab does not save to GitHub automatically. See Step 4 for how to save your work back to your fork.

---

## Step 3: The challenges

Work through the warmup together at the start (about 45 minutes). Then your team picks **one** challenge.

| # | Challenge | Difficulty | You'll build | Good fit for |
| --- | --- | --- | --- | --- |
| 1 | Quantum Dice Lab | ★☆☆ | Coins, dice, a loaded coin, and a fortune teller powered by true randomness | First-time coders, game fans |
| 2 | Quantum Coin Duel | ★☆☆ | A game where the quantum player always wins, until you find the counter-move | Puzzle and game lovers |
| 3 | Quantum Spy Network | ★★☆ | BB84 quantum encryption that catches an eavesdropper | Cybersecurity and CS |
| 4 | Spooky Telepathy | ★★☆ | Entangled pairs that send 2 bits with 1 qubit, then a whole text message | Physics fans |
| 5 | Quantum Treasure Hunt | ★★★ | Grover's search: find the treasure in one try | CS and math, teams wanting a stretch |
| 6 | Quantum Art Studio | ★☆☆ | Generative art painted by superposition and entanglement | Art, design, and music majors |

Want to pitch your own idea instead? Ask the organizer first.

### How each challenge works

- **Missions 1 to 5** walk you through the core build. Each has a `# TODO` to fill in and a check cell: ✅ means done, ❌ comes with a hint.
- **Make it yours** is where your project becomes yours. Pick an idea or invent one. This is what makes a demo stand out.
- **Explain it** has three questions. Judges care most about whether you understand what your quantum code does, so answer these as a team.

**Teams sharing one fork:** avoid two people editing the same notebook at the same time, because their changes can conflict. Split the work by notebook (for example, one person on the missions, another on a new notebook for "Make it yours"), or have one person type while the others help.

---

## Step 4: Submit your work

Your submission is whatever is in your fork on GitHub at the deadline: **[DEADLINE]**. Save early and often; you can push as many times as you like.

Before your final save, run your notebook from top to bottom (**Run All** at the top of the notebook) so the outputs (pictures, results, checks) are saved inside it.

### If you used Option A (VS Code)

Save the notebook (**Ctrl + S**, or **Cmd + S** on a Mac). Then, in the VS Code terminal (**Terminal → New Terminal** if it's closed):

```bash
git add *.ipynb
git commit -m "Describe what you changed"
git push
```

If you created other files (images, Python files), add them by name too, for example `git add my_art.png`. Don't add the `.venv` folder.

The first time you push, VS Code or Git may ask you to sign in to GitHub. Follow the browser prompt.

If `git push` is rejected because a teammate pushed first, run `git pull` and then `git push` again.

### If you used Option B (Google Colab)

1. Click **File → Save a copy in GitHub**.
2. Allow Colab to access your GitHub account if it asks.
3. Choose **your fork** as the repository and `main` as the branch.
4. Keep the file path the same as the notebook's name, so it replaces the original.
5. Type a short commit message and click **OK**.

### Final check

1. Open your fork's page on GitHub **in a private or incognito browser window**. If you can see your notebooks there, so can the organizer.
2. Click your notebook and confirm your latest work is there.
3. Send your fork's link to the organizer: **[WHERE TO SUBMIT]**.

---

## When you're stuck

1. Read the last line of the error message. It usually says what's wrong.
2. Re-run the setup cell, then run the notebook from the top.
3. Check the cheat sheet at the end of the warm-up notebook.
4. Ask a neighboring team.
5. Still stuck after 5 minutes? Flag down the organizer.

### Common setup problems

| Problem | Fix |
| --- | --- |
| `python` or `py` is not recognized (Windows) | Reinstall Python and check **"Add python.exe to PATH"** on the first screen. Then restart your computer and reopen VS Code. |
| `ModuleNotFoundError: No module named 'qiskit'` | The notebook is using the wrong Python. Click the kernel name in the notebook's top-right corner and choose **.venv**. |
| `.venv` doesn't appear in Select Kernel | Make sure Step A4 finished without errors, then close and reopen VS Code. |
| VS Code asks to install `ipykernel` | Click **Install**, or rerun the last install command from Step A4 with `(.venv)` showing. |
| `externally-managed-environment` error | You're installing outside the virtual environment. Run the activate command from Step A4 first, so the prompt starts with `(.venv)`. |
| `No module named venv` (Linux) | Run `sudo apt install python3-venv`, then create the environment again. |
| **Git: Clone** doesn't appear, or `git` is not recognized | Install Git, then restart your computer and reopen VS Code. |
| Circuit drawings fail with a `pylatexenc` or `matplotlib` error | Reinstall with the quotes included: `python -m pip install "qiskit[visualization]==2.6.1"`. |
| Nothing works on your laptop | Switch to Option B (Google Colab) and keep going. |move the `#` in the second code cell (`!pip install ...`) and run it once.