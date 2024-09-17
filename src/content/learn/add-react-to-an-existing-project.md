---
title: ಅಸ್ತಿತ್ವದಲ್ಲಿರುವ ಪ್ರಾಜೆಕ್ಟ್ ಗೆ ರಿಯಾಕ್ಟ್ ಅನ್ನು ಸೇರಿಸಿ
---

<Intro>

ನಿಮ್ಮ ಅಸ್ತಿತ್ವದಲ್ಲಿರುವ ಯೋಜನೆಗೆ ಕೆಲವು ಸಂವಾದಾತ್ಮಕತೆಯನ್ನು ಸೇರಿಸಲು ನೀವು ಬಯಸಿದರೆ, ನೀವು ಅದನ್ನು ರಿಯಾಕ್ಟ್‌ನಲ್ಲಿ ಪುನಃ ಬರೆಯಬೇಕಾಗಿಲ್ಲ. ನಿಮ್ಮ ಅಸ್ತಿತ್ವದಲ್ಲಿರುವ ಸ್ಟಾಕ್‌ಗೆ ರಿಯಾಕ್ಟ್ ಅನ್ನು ಸೇರಿಸಿ ಮತ್ತು ಸಂವಾದಾತ್ಮಕ ರಿಯಾಕ್ಟ್ ಕೊಂಪೊನೆಂಟ್ಗಳನ್ನು ಎಲ್ಲಿಯಾದರೂ ರೆಂಡರ್ ಮಾಡಿ.

</Intro>

<Note>

**ಸ್ಥಳೀಯ ಅಭಿವೃದ್ಧಿಗಾಗಿ ನೀವು [Node.js](https://nodejs.org/en/) ಅನ್ನು ಸ್ಥಾಪಿಸಬೇಕಾಗಿದೆ.** ನೀವು ಆನ್‌ಲೈನ್‌ನಲ್ಲಿ ಅಥವಾ ಸರಳ HTML ನೊಂದಿಗೆ [try react](/learn/installation#try-react) ಮಾಡಬಹುದು, ವಾಸ್ತವಿಕವಾಗಿ ನೀವು ಅಭಿವೃದ್ಧಿಗಾಗಿ ಬಳಸಲು ಬಯಸುವ ಹೆಚ್ಚಿನ JavaScript ಟೂಲಿಂಗ್‌ಗೆ Node.js ಅಗತ್ಯವಿದೆ

</Note>

## ನಿಮ್ಮ ಅಸ್ತಿತ್ವದಲ್ಲಿರುವ ವೆಬ್‌ಸೈಟ್‌ನ ಸಂಪೂರ್ಣ ಸಬ್‌ರೂಟ್‌ಗಾಗಿ ರಿಯಾಕ್ಟ್ ಅನ್ನು ಬಳಸುವುದು {/* using-react-for-an-entire-subroute-of-your-existing-website */}

'example.com' ನಲ್ಲಿ ನೀವು ಅಸ್ತಿತ್ವದಲ್ಲಿರುವ ವೆಬ್ ಅಪ್ಲಿಕೇಶನ್ ಅನ್ನು ಇನ್ನೊಂದು ಸರ್ವರ್ ತಂತ್ರಜ್ಞಾನದೊಂದಿಗೆ (like Rails) ನಿರ್ಮಿಸಿದ್ದೀರಿ ಎಂದು ಹೇಳೋಣ ಮತ್ತು ನೀವು `example.com/some-app/` ನಿಂದ ಪ್ರಾರಂಭವಾಗುವ ಎಲ್ಲಾ ಮಾರ್ಗಗಳನ್ನು ಸಂಪೂರ್ಣವಾಗಿ React ನೊಂದಿಗೆ ಕಾರ್ಯಗತಗೊಳಿಸಲು ಬಯಸುತ್ತೀರಿ.

ಅದನ್ನು ಹೇಗೆ ಹೊಂದಿಸಲು ನಾವು ಶಿಫಾರಸು ಮಾಡುತ್ತೇವೆ ಎಂಬುದು ಇಲ್ಲಿದೆ:

1. [ರಿಯಾಕ್ಟ್ ಆಧಾರಿತ ಫ್ರೇಮ್‌ವರ್ಕ್‌ಗಳಲ್ಲಿ](/learn/start-a-new-react-project) ಒಂದನ್ನು ಬಳಸಿಕೊಂಡು ನಿಮ್ಮ **ಅಪ್ಲಿಕೇಶನ್‌ನ ರಿಯಾಕ್ಟ್ ಭಾಗವನ್ನು ನಿರ್ಮಿಸಿ**
2. **`/some-app` ಅನ್ನು _base path_ ಎಂದು ನಿರ್ದಿಷ್ಟಪಡಿಸಿ** ನಿಮ್ಮ ಫ್ರೇಮ್‌ವರ್ಕ್‌ನ ಕಾನ್ಫಿಗರೇಶನ್‌ನಲ್ಲಿ (ಹೇಗೆ ಇಲ್ಲಿದೆ: [Next.js](https://nextjs.org/docs/api-reference/next.config.js/basepath), [Gatsby](https://www.gatsbyjs.com/docs/how-to/previews-deploys-hosting/path-prefix/)).
3. **ನಿಮ್ಮ ಸರ್ವರ್ ಅಥವಾ ಪ್ರಾಕ್ಸಿಯನ್ನು ಕಾನ್ಫಿಗರ್ ಮಾಡಿ** ಇದರಿಂದ `/some-app/` ಅಡಿಯಲ್ಲಿ ಎಲ್ಲಾ ವಿನಂತಿಗಳನ್ನು ನಿಮ್ಮ ರಿಯಾಕ್ಟ್ ಅಪ್ಲಿಕೇಶನ್ ಮೂಲಕ ನಿರ್ವಹಿಸಲಾಗುತ್ತದೆ.

ನಿಮ್ಮ ಅಪ್ಲಿಕೇಶನ್‌ನ ರಿಯಾಕ್ಟ್ ಭಾಗವು ಆ ಫ್ರೇಮ್‌ವರ್ಕ್‌ಗಳಲ್ಲಿ ಸಂಯೋಜಿಸಲ್ಪಟ್ಟಿದೆ ಎಂದು ಖಚಿತಪಡಿಸುತ್ತದೆ [ಉತ್ತಮ ಅಭ್ಯಾಸಗಳಿಂದ ಪ್ರಯೋಜನ](/learn/start-a-new-react-project#can-i-use-react-without-a-framework).

ಅನೇಕ ರಿಯಾಕ್ಟ್-ಆಧಾರಿತ ಫ್ರೇಮ್‌ವರ್ಕ್‌ಗಳು ಫೂಲ್‍-ಸ್ಟಾಕ್ ಆಗಿರುತ್ತವೆ ಮತ್ತು ಸರ್ವರ್‌ನ ಪ್ರಯೋಜನವನ್ನು ಪಡೆಯಲು ನಿಮ್ಮ ರಿಯಾಕ್ಟ್ ಅಪ್ಲಿಕೇಶನ್ ಅನ್ನು ಸಕ್ರಿಯಗೊಳಿಸುತ್ತದೆ. ಆದಾಗ್ಯೂ, ನೀವು ಸರ್ವರ್‌ನಲ್ಲಿ JavaScript ಅನ್ನು ಚಲಾಯಿಸಲು ಸಾಧ್ಯವಾಗದಿದ್ದರೂ ಅಥವಾ ಬಯಸದಿದ್ದರೂ ಸಹ ನೀವು ಅದೇ ವಿಧಾನವನ್ನು ಬಳಸಬಹುದು. ಆ ಸಂದರ್ಭದಲ್ಲಿ, Next.js ಗಾಗಿ HTML/CSS/JS ರಫ್ತು ([`next export` output](https://nextjs.org/docs/advanced-features/static-html-export) ಅನ್ನು ಒದಗಿಸಿ, Gatsby ಗಾಗಿ ಡೀಫಾಲ್ಟ್) ಬದಲಿಗೆ `/some-app/` ನಲ್ಲಿ.

## ನಿಮ್ಮ ಅಸ್ತಿತ್ವದಲ್ಲಿರುವ ಪುಟದ ಒಂದು ಭಾಗಕ್ಕಾಗಿ ರಿಯಾಕ್ಟ್ ಅನ್ನು ಬಳಸುವುದು {/* using-react-for-a-part-of-your-existing-page */}

ನೀವು ಇನ್ನೊಂದು ತಂತ್ರಜ್ಞಾನದೊಂದಿಗೆ ನಿರ್ಮಿಸಲಾದ ಅಸ್ತಿತ್ವದಲ್ಲಿರುವ ಪುಟವನ್ನು ಹೊಂದಿರುವಿರಿ ಎಂದು ಹೇಳೋಣ (ರೈಲ್ಸ್‌ನಂತಹ ಸರ್ವರ್ ಅಥವಾ ಬ್ಯಾಕ್‌ಬೋನ್‌ನಂತಹ ಕ್ಲೈಂಟ್), ಮತ್ತು ಆ ಪುಟದಲ್ಲಿ ಎಲ್ಲೋ ಸಂವಾದಾತ್ಮಕ ಪ್ರತಿಕ್ರಿಯೆ ಕೊಂಪೊನೆಂಟ್ಗಳನ್ನು ರೆಂಡರ್ ಮಾಡಲು ನೀವು ಬಯಸುತ್ತೀರಿ. ರಿಯಾಕ್ಟ್ ಅನ್ನು ಸಂಯೋಜಿಸಲು ಇದು ಸಾಮಾನ್ಯ ಮಾರ್ಗವಾಗಿದೆ - ವಾಸ್ತವವಾಗಿ, ಹೆಚ್ಚಿನ ರಿಯಾಕ್ಟ್ ಬಳಕೆಯು ಹಲವು ವರ್ಷಗಳಿಂದ ಮೆಟಾವನ್ನು ಹೇಗೆ ನೋಡಿದೆ!

ನೀವು ಇದನ್ನು ಎರಡು ಹಂತಗಳಲ್ಲಿ ಮಾಡಬಹುದು:

1. **ಜಾವಾಸ್ಕ್ರಿಪ್ಟ್ ಪರಿಸರವನ್ನು ಸೆಟಪ್ ಮಾಡಿ** ಅದು ನಿಮಗೆ [JSX ಸಿಂಟ್ಯಾಕ್ಸ್](/Learn/writing-markup-with-jsx), ನಿಮ್ಮ ಕೋಡ್ ಅನ್ನು ಮಾಡ್ಯೂಲ್‌ಗಳಾಗಿ ವಿಭಜಿಸಿ[`import`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/import) / [`export`](https://developer.mozilla.org/en -US/docs/Web/JavaScript/Reference/Statements/export) ಸಿಂಟ್ಯಾಕ್ಸ್, ಮತ್ತು [npm](https://www.npmjs.com/) ಪ್ಯಾಕೇಜ್ ರಿಜಿಸ್ಟ್ರಿಯಿಂದ ಪ್ಯಾಕೇಜ್‌ಗಳನ್ನು ಬಳಸಿ (ಉದಾಹರಣೆಗೆ, ರಿಯಾಕ್ಟ್).
2. **ನಿಮ್ಮ ರಿಯಾಕ್ಟ್ ಕಾಂಪೊನೆಂಟ್‌ಗಳನ್ನು** ನೀವು ಪುಟದಲ್ಲಿ ನೋಡಲು ಬಯಸುವಲ್ಲಿ ರೆಂಡರ್ ಮಾಡಿ.

ನಿಖರವಾದ ವಿಧಾನವು ನಿಮ್ಮ ಅಸ್ತಿತ್ವದಲ್ಲಿರುವ ಪುಟದ ಸೆಟಪ್ ಅನ್ನು ಅವಲಂಬಿಸಿರುತ್ತದೆ, ಆದ್ದರಿಂದ ನಾವು ಕೆಲವು ವಿವರಗಳ ಮೂಲಕ ನಡೆಯೋಣ.

### Step 1: Set up a modular JavaScript environment {/* step-1-set-up-a-modular-javascript-environment */}

ಮಾಡ್ಯುಲರ್ ಜಾವಾಸ್ಕ್ರಿಪ್ಟ್ ಪರಿಸರವು ನಿಮ್ಮ ಎಲ್ಲಾ ಕೋಡ್ ಅನ್ನು ಒಂದೇ ಫೈಲ್‌ನಲ್ಲಿ ಬರೆಯುವುದಕ್ಕೆ ವಿರುದ್ಧವಾಗಿ ಪ್ರತ್ಯೇಕ ಫೈಲ್‌ಗಳಲ್ಲಿ ನಿಮ್ಮ ರಿಯಾಕ್ಟ್ ಕೊಂಪೊನೆಂಟ್ಗಳನ್ನು ಬರೆಯಲು ನಿಮಗೆ ಅನುಮತಿಸುತ್ತದೆ. [npm](https://www.npmjs.com/) ರಿಜಿಸ್ಟ್ರಿಯಲ್ಲಿ ಇತರ ಡೆವಲಪರ್‌ಗಳು ಪ್ರಕಟಿಸಿದ ಎಲ್ಲಾ ಅದ್ಭುತ ಪ್ಯಾಕೇಜ್‌ಗಳನ್ನು ಬಳಸಲು ಸಹ ಇದು ನಿಮಗೆ ಅನುಮತಿಸುತ್ತದೆ--ರಿಯಾಕ್ಟ್ ಸೇರಿದಂತೆ! ನೀವು ಇದನ್ನು ಹೇಗೆ ಮಾಡುತ್ತೀರಿ ಎಂಬುದು ನಿಮ್ಮ ಅಸ್ತಿತ್ವದಲ್ಲಿರುವ ಸೆಟಪ್ ಅನ್ನು ಅವಲಂಬಿಸಿರುತ್ತದೆ:

- **ನಿಮ್ಮ ಅಪ್ಲಿಕೇಶನ್ ಈಗಾಗಲೇ `import` ಹೇಳಿಕೆಗಳನ್ನು ಬಳಸುವ ಫೈಲ್‌ಗಳಾಗಿ ವಿಭಜಿಸಿದ್ದರೆ,** ನೀವು ಈಗಾಗಲೇ ಹೊಂದಿರುವ ಸೆಟಪ್ ಅನ್ನು ಬಳಸಲು ಪ್ರಯತ್ನಿಸಿ. ನಿಮ್ಮ JS ಕೋಡ್‌ನಲ್ಲಿ `<div />` ಬರೆಯುವುದು ಸಿಂಟ್ಯಾಕ್ಸ್ ಎರರ್ವನ್ನು ಉಂಟುಮಾಡುತ್ತದೆಯೇ ಎಂದು ಪರಿಶೀಲಿಸಿ. ಇದು ಸಿಂಟ್ಯಾಕ್ಸ್ ಎರರ್ವನ್ನು ಉಂಟುಮಾಡಿದರೆ, ನೀವು [Babel ನೊಂದಿಗೆ ನಿಮ್ಮ JavaScript ಕೋಡ್ ಅನ್ನು ರೂಪಾಂತರಿಸಬೇಕಾಗಬಹುದು](https://babeljs.io/setup), ಮತ್ತು [Babel React preset](https://babeljs.io/docs/babel-preset-react) JSX ಅನ್ನು ಬಳಸಲು.

- **ನಿಮ್ಮ ಅಪ್ಲಿಕೇಶನ್ JavaScript ಮಾಡ್ಯೂಲ್‌ಗಳನ್ನು ಕಂಪೈಲ್ ಮಾಡಲು ಅಸ್ತಿತ್ವದಲ್ಲಿರುವ ಸೆಟಪ್ ಅನ್ನು ಹೊಂದಿಲ್ಲದಿದ್ದರೆ**, ಅದನ್ನು [Vite](https://vitejs.dev/) ನೊಂದಿಗೆ ಸೆಟಪ್ ಮಾಡಿ. Vite ಸಮುದಾಯವು ರೈಲ್ಸ್, ಜಾಂಗೊ ಮತ್ತು ಲಾರಾವೆಲ್ ಸೇರಿದಂತೆ [ಬ್ಯಾಕೆಂಡ್ ಫ್ರೇಮ್‌ವರ್ಕ್‌ಗಳೊಂದಿಗೆ ಅನೇಕ ಏಕೀಕರಣಗಳನ್ನು](https://github.com/vitejs/awesome-vite#integrations-with-backends) ನಿರ್ವಹಿಸುತ್ತದೆ. ನಿಮ್ಮ ಬ್ಯಾಕೆಂಡ್ ಫ್ರೇಮ್‌ವರ್ಕ್ ಪಟ್ಟಿ ಮಾಡದಿದ್ದರೆ, ನಿಮ್ಮ ಬ್ಯಾಕೆಂಡ್‌ನೊಂದಿಗೆ ವೈಟ್ ಬಿಲ್ಡ್‌ಗಳನ್ನು ಹಸ್ತಚಾಲಿತವಾಗಿ ಸಂಯೋಜಿಸಲು [ಈ ಮಾರ್ಗದರ್ಶಿಯನ್ನು ಅನುಸರಿಸಿ](https://vitejs.dev/guide/backend-integration.html).

ನಿಮ್ಮ ಸೆಟಪ್ ಕಾರ್ಯನಿರ್ವಹಿಸುತ್ತದೆಯೇ ಎಂದು ಪರಿಶೀಲಿಸಲು, ನಿಮ್ಮ ಪ್ರಾಜೆಕ್ಟ್ ಫೋಲ್ಡರ್‌ನಲ್ಲಿ ಈ ಆಜ್ಞೆಯನ್ನು ಚಲಾಯಿಸಿ:

<TerminalBlock>npm install react react-dom</TerminalBlock>

ನಂತರ ನಿಮ್ಮ ಮುಖ್ಯ JavaScript ಫೈಲ್‌ನ ಮೇಲ್ಭಾಗದಲ್ಲಿ ಕೋಡ್‌ನ ಈ ಸಾಲುಗಳನ್ನು ಸೇರಿಸಿ (ಇದನ್ನು `index.js` ಅಥವಾ `main.js` ಎಂದು ಕರೆಯಬಹುದು):

<Sandpack>

```html index.html hidden
<!DOCTYPE html>
<html>
  <head>
    <title>My app</title>
  </head>
  <body>
    <!-- Your existing page content (in this example, it gets replaced) -->
  </body>
</html>
```

```js src/index.js active
import {createRoot} from 'react-dom/client';

// Clear the existing HTML content
document.body.innerHTML = '<div id="app"></div>';

// Render your React component instead
const root = createRoot(document.getElementById('app'));
root.render(<h1>Hello, world</h1>);
```

</Sandpack>

ನಿಮ್ಮ ಪುಟದ ಸಂಪೂರ್ಣ ವಿಷಯವನ್ನು "Hello, world!" ನಿಂದ ಬದಲಾಗಿದ್ದಾರೆ, ಎಲ್ಲವೂ ಕೆಲಸ ಮಾಡುತ್ತಿದ್ದೆ! ಓದುತ್ತಿರಿ.

<Note>

ಮೊದಲ ಬಾರಿಗೆ ಅಸ್ತಿತ್ವದಲ್ಲಿರುವ ಯೋಜನೆಗೆ ಮಾಡ್ಯುಲರ್ ಜಾವಾಸ್ಕ್ರಿಪ್ಟ್ ಪರಿಸರವನ್ನು ಸಂಯೋಜಿಸುವುದು ಬೆದರಿಸುವಂತೆ ಮಾಡಬಹುದು, ಆದರೆ ಇದು ಯೋಗ್ಯವಾಗಿದೆ! ನೀವು ಸಿಲುಕಿಕೊಂಡರೆ, ನಮ್ಮ [ಸಮುದಾಯ ಸಂಪನ್ಮೂಲಗಳು](/community) ಅಥವಾ [Vite Chat](https://chat.vitejs.dev/) ಪ್ರಯತ್ನಿಸಿ.

</Note>

### Step 2: ಪುಟದಲ್ಲಿ ಎಲ್ಲಿಯಾದರೂ ರಿಯಾಕ್ಟ್ ಕೊಂಪೊನೆಂಟ್ಗಳನ್ನು ಸಲ್ಲಿಸಿ {/* step-2-render-react-components-anywhere-on-the-page */}

ಹಿಂದಿನ ಹಂತದಲ್ಲಿ, ನೀವು ಈ ಕೋಡ್ ಅನ್ನು ನಿಮ್ಮ ಮುಖ್ಯ ಫೈಲ್‌ನ ಮೇಲ್ಭಾಗದಲ್ಲಿ ಇರಿಸಿದ್ದೀರಿ:

```js
import {createRoot} from 'react-dom/client';

// Clear the existing HTML content
document.body.innerHTML = '<div id="app"></div>';

// Render your React component instead
const root = createRoot(document.getElementById('app'));
root.render(<h1>Hello, world</h1>);
```

ಸಹಜವಾಗಿ, ಅಸ್ತಿತ್ವದಲ್ಲಿರುವ HTML ವಿಷಯವನ್ನು ತೆರವುಗೊಳಿಸಲು ನೀವು ನಿಜವಾಗಿಯೂ ಬಯಸುವುದಿಲ್ಲ!

ಈ ಕೋಡ್ ಅನ್ನು ಅಳಿಸಿ.

ಬದಲಾಗಿ, ನಿಮ್ಮ HTML ನಲ್ಲಿನ ನಿರ್ದಿಷ್ಟ ಸ್ಥಳಗಳಲ್ಲಿ ನಿಮ್ಮ ರಿಯಾಕ್ಟ್ ಕೊಂಪೊನೆಂಟ್ಗಳನ್ನು ನಿರೂಪಿಸಲು ನೀವು ಬಹುಶಃ ಬಯಸುತ್ತೀರಿ. ನಿಮ್ಮ HTML ಪುಟವನ್ನು ತೆರೆಯಿರಿ (ಅಥವಾ ಅದನ್ನು ಉತ್ಪಾದಿಸುವ ಸರ್ವರ್ ಟೆಂಪ್ಲೇಟ್‌ಗಳು) ಮತ್ತು ಯಾವುದಾದರೂ ಒಂದು ಅನನ್ಯ [`id`](https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes/id) ಆಟ್ರಿಬ್ಯೊಟ್ವನ್ನು ಸೇರಿಸಿ ಟ್ಯಾಗ್, ಉದಾಹರಣೆಗೆ:

```html
<!-- ... somewhere in your html ... -->
<nav id="navigation"></nav>
<!-- ... more html ... -->
```

ಇದು ನಿಮಗೆ HTML ಅಂಶವನ್ನು [`document.getElementById`](https://developer.mozilla.org/en-US/docs/Web/API/Document/getElementById) ಜೊತೆಗೆ ಹುಡುಕಲು ಮತ್ತು ಅದನ್ನು [`createRoot`](/reference/react-dom/client/createRoot) ಗೆ ರವಾನಿಸಲು ಅನುಮತಿಸುತ್ತದೆ ಇದರಿಂದ ನೀವು ನಿಮ್ಮ ಸ್ವಂತ ರಿಯಾಕ್ಟ್ ಕೊಂಪೊನೆಂಟ್ವನ್ನು ಒಳಗೆ ಸಲ್ಲಿಸಬಹುದು:

<Sandpack>

```html index.html
<!DOCTYPE html>
<html>
  <head>
    <title>My app</title>
  </head>
  <body>
    <p>This paragraph is a part of HTML.</p>
    <nav id="navigation"></nav>
    <p>This paragraph is also a part of HTML.</p>
  </body>
</html>
```

```js src/index.js active
import {createRoot} from 'react-dom/client';

function NavigationBar() {
  // TODO: Actually implement a navigation bar
  return <h1>Hello from React!</h1>;
}

const domNode = document.getElementById('navigation');
const root = createRoot(domNode);
root.render(<NavigationBar />);
```

</Sandpack>

`index.html` ನಿಂದ ಮೂಲ HTML ವಿಷಯವನ್ನು ಹೇಗೆ ಸಂರಕ್ಷಿಸಲಾಗಿದೆ ಎಂಬುದನ್ನು ಗಮನಿಸಿ, ಆದರೆ ನಿಮ್ಮ ಸ್ವಂತ `NavigationBar` ರಿಯಾಕ್ಟ್ ಘಟಕವು/ಕೊಂಪೊನೆಂಟ್ ಈಗ ನಿಮ್ಮ HTML ನಿಂದ `<nav id="navigation">` ಒಳಗೆ ಕಾಣಿಸಿಕೊಳ್ಳುತ್ತದೆ. ಅಸ್ತಿತ್ವದಲ್ಲಿರುವ HTML ಪುಟದಲ್ಲಿ ರಿಯಾಕ್ಟ್ ಕಾಂಪೊನೆಂಟ್‌ಗಳನ್ನು ರೆಂಡರಿಂಗ್ ಮಾಡುವ ಕುರಿತು ಇನ್ನಷ್ಟು ತಿಳಿದುಕೊಳ್ಳಲು [`createRoot` ಬಳಕೆಯ ದಸ್ತಾವೇಜನ್ನು](/reference/react-dom/client/createRoot#rendering-a-page-partially-built-with-react) ಓದಿ.

ಅಸ್ತಿತ್ವದಲ್ಲಿರುವ ಪ್ರಾಜೆಕ್ಟ್‌ನಲ್ಲಿ ನೀವು ರಿಯಾಕ್ಟ್ ಅನ್ನು ಅಳವಡಿಸಿಕೊಂಡಾಗ, ಸಣ್ಣ ಸಂವಾದಾತ್ಮಕ ಕೊಂಪೊನೆಂಟ್ಸ್(ಬಟನ್‌ಗಳಂತೆ) ಪ್ರಾರಂಭಿಸುವುದು ಸಾಮಾನ್ಯವಾಗಿದೆ ಮತ್ತು ಅಂತಿಮವಾಗಿ ನಿಮ್ಮ ಸಂಪೂರ್ಣ ಪುಟವನ್ನು ರಿಯಾಕ್ಟ್‌ನೊಂದಿಗೆ ನಿರ್ಮಿಸುವವರೆಗೆ ಕ್ರಮೇಣ "ಮೇಲ್ಮುಖವಾಗಿ ಚಲಿಸುತ್ತಿರಿ". ನೀವು ಎಂದಾದರೂ ಆ ಹಂತವನ್ನು ತಲುಪಿದರೆ, ರಿಯಾಕ್ಟ್‌ನಿಂದ ಹೆಚ್ಚಿನದನ್ನು ಪಡೆಯಲು [a React framework](/learn/start-a-new-react-project) ಗೆ ವಲಸೆ ಹೋಗಲು ನಾವು ಶಿಫಾರಸು ಮಾಡುತ್ತೇವೆ.

## ಅಸ್ತಿತ್ವದಲ್ಲಿರುವ ಸ್ಥಳೀಯ ಮೊಬೈಲ್ ಅಪ್ಲಿಕೇಶನ್‌ನಲ್ಲಿ ರಿಯಾಕ್ಟ್ ನೇಟಿವ್ ಅನ್ನು ಬಳಸುವುದು {/* using-react-native-in-an-existing-native-mobile-app */}

[ರಿಯಾಕ್ಟ್ ನೇಟಿವ್](https://reactnative.dev/) ಅನ್ನು ಅಸ್ತಿತ್ವದಲ್ಲಿರುವ ಸ್ಥಳೀಯ ಅಪ್ಲಿಕೇಶನ್‌ಗಳಲ್ಲಿ ಹೆಚ್ಚುತ್ತಿರುವ ರೀತಿಯಲ್ಲಿ ಸಂಯೋಜಿಸಬಹುದು. ನೀವು Android (Java ಅಥವಾ Kotlin) ಅಥವಾ iOS (Objective-C ಅಥವಾ Swift) ಗಾಗಿ ಅಸ್ತಿತ್ವದಲ್ಲಿರುವ ಸ್ಥಳೀಯ ಅಪ್ಲಿಕೇಶನ್ ಹೊಂದಿದ್ದರೆ, ಇದಕ್ಕೆ ಸ್ಥಳೀಯ ರಿಯಾಕ್ಟ್ ನೇಟಿವ್ ಸ್ಕ್ರೀನ್ನ್ನು ಸೇರಿಸಲು [ಈ ಮಾರ್ಗದರ್ಶಿಯನ್ನು ಅನುಸರಿಸಿ](https://reactnative.dev/docs/integration-with-existing-apps).