Set up the initial repository structure for **The Keep**.

The repository already contains:

- `README.md`
- `LICENSE`

Do not replace or modify these files.

## Create the structure

```text
/
├── code/
├── docs/
│   └── .gitkeep
├── prompts/
│   └── .gitkeep
├── README.md
├── LICENSE
└── .gitignore
```

## Vue app

Inside `/code`, initialise a minimal Vue 3 application using Vite and JavaScript.

Keep it very simple:

- Vue 3
- Vite
- JavaScript
- Plain CSS
- Single page
- Display `Hello World`
- Remove unnecessary starter/demo content

The app should run with:

```bash
cd code
npm install
npm run dev
```

## Git

Create or update the root `.gitignore` to exclude appropriate Node/Vite files such as:

```text
node_modules/
dist/
.DS_Store
```

Do not add additional frameworks, dependencies, features, or architecture at this stage.