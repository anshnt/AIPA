<div align="center">

# 🧑‍✈️ AIPA 🧑‍✈️

</div>

---


<br>

<div align="center">

### AIPA doesn't just generate code, it builds apps!

</div>



AIPA aims to research how much LLMs can be utilized to generate fully working, production-ready apps while the developer oversees the implementation.

**The main idea is that AI can write most of the code for an app (maybe 95%), but for the rest, 5%, a developer is and will be needed until we get full AGI**.


---

---

# 🔌 Requirements

- **Python 3.9+**

# 🚦How to start using AIPA?

### If you're new to AIPA:

After you have Python and (optionally) PostgreSQL installed, follow these steps:

1. `git clone ` (clone the repo)
2. `cd AIPA` (go to the repo folder)
3. `python3 -m venv venv` (create a virtual environment)
4. `source venv/bin/activate` (or on Windows `venv\Scripts\activate`) (activate the virtual environment)
5. `pip install -r requirements.txt` (install the dependencies)
6. `cp example-config.json config.json` (create `config.json` file)
7. Set your key and other settings in `config.json` file:
   - LLM Provider (`openai`, `anthropic` or `groq`) key and endpoints (leave `null` for default) (note that Azure and OpenRouter are suppored via the `openai` setting)
   - Your API key (if `null`, will be read from the environment variables)
   - database settings: sqlite is used by default, PostgreSQL should also work
   - optionally update `fs.ignore_paths` and add files or folders which shouldn't be tracked by AIPA in workspace, useful to ignore folders created by compilers
8. `python main.py` (start AIPA)

All generated code will be stored in the folder `workspace` inside the folder named after the app name you enter upon starting the pilot.

# 🧑‍💻️ CLI arguments

### List created projects (apps)

```bash
python main.py --list
```

Note: for each project (app), this also lists "branches". Currently we only support having one branch (called "main"), and in the future we plan to add support for multiple project branches.

### Load and continue from the latest step in a project (app)

```bash
python main.py --project <app_id>
```

### Load and continue from a specific step in a project (app)

```bash
python main.py --project <app_id> --step <step>
```

Warning: this will delete all progress after the specified step!

### Delete project (app)

```bash
python main.py --delete <app_id>
```

Delete project with the specified `app_id`. Warning: this cannot be undone!

### Import projects from v0.1

```bash
python main.py --import-v0 <path>
```

This will import projects from the old AIPA v0.1 database. The path should be the path to the old AIPA v0.1 database. For each project, it will import the start of the latest task you were working on. If the project was already imported, the import procedure will skip it (won't overwrite the project in the database).

### Other command-line options

There are several other command-line options that mostly support calling AIPA from our VSCode extension. To see all the available options, use the `--help` flag:

```bash
python main.py --help
```

# 🏗 How AIPA works?

Here are the steps AIPA takes to create an app:

1. You enter the app name and the description.
2. **Product Owner agent** like in real life, does nothing. :)
3. **Specification Writer agent** asks a couple of questions to understand the requirements better if project description is not good enough.
4. **Architect agent** writes up technologies that will be used for the app and checks if all technologies are installed on the machine and installs them if not.
5. **Tech Lead agent** writes up development tasks that the Developer must implement.
6. **Developer agent** takes each task and writes up what needs to be done to implement it. The description is in human-readable form.
7. **Code Monkey agent** takes the Developer's description and the existing file and implements the changes.
8. **Reviewer agent** reviews every step of the task and if something is done wrong Reviewer sends it back to Code Monkey.
9. **Troubleshooter agent** helps you to give good feedback to AIPA when something is wrong.
10. **Debugger agent** hate to see him, but he is your best friend when things go south.
11. **Technical Writer agent** writes documentation for the project.

<br>
