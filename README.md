# My Markdown Reader

A small app that runs locally and lets you read a collection of Markdown
documents comfortably, without opening them one by one.

Pick a folder and the app lets you:

- **browse** its subfolders, going down and back up a level;
- **read** each `.md` file already rendered, with headings, lists, tables and code;
- **jump to the previous or next file** in the same folder with one click;
- **ignore** everything that is not Markdown.

> 🚧 **Work in progress.** This is a personal learning project and it grows
> one step at a time: see the [Status](#status) section.

---

## How it works

The app has two parts that talk to each other:

| Part | Tech | What it does |
|---|---|---|
| `backend/` | Python, [FastAPI](https://fastapi.tiangolo.com), [uv](https://docs.astral.sh/uv) | Reads folders on disk and returns the list of Markdown files and their content |
| `frontend/` | [React](https://react.dev), [TypeScript](https://www.typescriptlang.org), [Vite](https://vite.dev) | The page in the browser: shows folders, the document and the navigation buttons |

The backend reads **only** inside the folder you choose. It cannot open files
outside of it.

---

## Requirements

- [uv](https://docs.astral.sh/uv/getting-started/installation/): it also installs
  the right Python version for the project
- [Node.js](https://nodejs.org) (LTS version): needed for the frontend

---

## Getting started

### Backend

From the `backend` folder:

```bash
uv sync
```

installs the dependencies exactly as pinned in `uv.lock`.

```bash
uv run fastapi dev main.py
```

starts the server in development mode: it reloads automatically when you save a file.

Then open in your browser:

- `http://127.0.0.1:8000`: the API
- `http://127.0.0.1:8000/docs`: the interactive API documentation generated
  by FastAPI, where you can try every route

### Configuration

<!-- TODO: explain how to choose the Markdown documents folder
     (once it is out of the code, e.g. in a .env file). -->

_Coming soon._

### Frontend

<!-- TODO: commands to install and start the frontend, once it exists. -->

_Coming soon._

---

## Status

- [x] Minimal FastAPI server
- [ ] List subfolders and Markdown files of a folder
- [ ] Protection: no access to files outside the chosen folder
- [ ] Read a file together with its neighbours (previous / next)
- [ ] Web page showing the folder contents
- [ ] Rendered Markdown view
- [ ] Navigation buttons and keyboard shortcuts

Ideas for later: remember the last opened file, dark mode, search by name.

---

## License

<!-- TODO: pick a license (see https://choosealicense.com)
     or keep "All rights reserved". -->

_To be decided._