# Config Vite project & deploy it to GitHub Pages

1. Download and install [Node.js](https://nodejs.org/en)
2. Install the dependencies, devDependencies, create `vite.config.js` and start the server:

```sh
npm create vite@latest
npm i
npm add -D gh-pages
npm add just-validate
touch vite.config.js
npm run dev
```

3. Add to `vite.config.js`:

```js
import { defineConfig } from "vite";

export default defineConfig({ base: "/enter-your-repo-name-here/" });
```

4. Add scripts to `package.json`:

```js
   ...
   "scripts": {
   ...,
   "predeploy": "npm run build",
   "deploy": "gh-pages -d dist"
   },
   ...
```

5. Remove demo-content:

- **Files**: `counter.js, javascript.svg, vite.svg`
- All **content** from:
  - _public_ folder
  - files: `style.css, index.html`:
  - `main.js` except line #1: `import './style.css'`

6. In `index.html`:

- Create base template with emmet command `!tab`.
- **Don't forget** to paste before `</body>`:

```html
<script type="module" src="/main.js"></script>
```

7. Drop assets _(fonts, pics etc.)_ to `public` folder.
8. Init your repo on GitHub.
9. Write your code.
10. **Don't forget** to commit and sync everything before deploying.
11. Deploy on GitHub Pages:

```sh
npm run deploy
```
