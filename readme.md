# TP MISE EN PLACE D'UN WORKFLOW GITHUB ACTIONS

## PRE-REQUIS

```
- Créer un dossier .gtihub dans le projet
- Créer un sous dossier workflows au 
```

### 1 - Créer un fichier  ci.yml dans le sous dossier workflows

Rajouter le contenu ci-dessous au sein du fichier

```
name: Node.js CI

on:
  push:
    branches: [main]
  pull_request:
    branches: [main]

jobs:
  build:
    runs-on: ubuntu-latest

    steps:
      - name: Checkout code
        uses: actions/checkout@v4

      - name: Use Node.js
        uses: actions/setup-node@v4
        with:
          node-version: "20"

      - name: Install dependencies
        run: npm ci

      - name: Run build (if present)
        run: npm run build --if-present

```

### 2 - Créer un repository github


### 3 - Pousser le projet sur github