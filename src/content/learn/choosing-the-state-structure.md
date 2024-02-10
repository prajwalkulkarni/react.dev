---
title: Choosing the State Structure
---

<Intro>

ಸ್ಟೇಟ್ ಚೆನ್ನಾಗಿ ರಚಿಸುವುದರಿಂದ ಮಾರ್ಪಡಿಸಲು ಮತ್ತು ಡೀಬಗ್ ಮಾಡಲು ಆಹ್ಲಾದಕರವಾದ ಕೊಂಪೊನೆಂಟ್ ಮತ್ತು ಎರರ್ಗಳ ನಿರಂತರ ಮೂಲವಾಗಿರುವ ಒಂದು ಅಂಶದ ನಡುವೆ ವ್ಯತ್ಯಾಸವನ್ನು ಮಾಡಬಹುದು. ಸ್ಟೇಟ್ ರಚಿಸುವಾಗ ನೀವು ಪರಿಗಣಿಸಬೇಕಾದ ಕೆಲವು ಸಲಹೆಗಳು ಇಲ್ಲಿವೆ.

</Intro>

<YouWillLearn>

- ಏಕ ಮತ್ತು ಬಹು ಸ್ಟೇಟ್ ವೇರಿಯಬಲ್‌ಗಳನ್ನು ಯಾವಾಗ ಬಳಸಬೇಕು
- ಸ್ಟೇಟ್ ಸಂಘಟಿಸುವಾಗ ಏನು ತಪ್ಪಿಸಬೇಕು
- ಸ್ಟೇಟ್ ರಚನೆಯೊಂದಿಗೆ ಸಾಮಾನ್ಯ ಸಮಸ್ಯೆಗಳನ್ನು ಹೇಗೆ ಸರಿಪಡಿಸುವುದು

</YouWillLearn>

## ಸ್ಟೇಟ್ ರಚನೆಯ ತತ್ವಗಳು {/* principles-for-structuring-state */}

ನೀವು ಕೆಲವು ಸ್ಟೇಟ್ ಹೊಂದಿರುವ ಕೊಂಪೊನೆಂಟ್ವನ್ನು ಬರೆಯುವಾಗ, ಎಷ್ಟು ಸ್ಟೇಟ್ ವೇರಿಯಬಲ್‌ಗಳನ್ನು ಬಳಸಬೇಕು ಮತ್ತು ಅವುಗಳ ಡೇಟಾದ ಆಕಾರ ಹೇಗಿರಬೇಕು ಎಂಬುದರ ಕುರಿತು ನೀವು ಆಯ್ಕೆಗಳನ್ನು ಮಾಡಬೇಕಾಗುತ್ತದೆ. ಉಪಸೂಕ್ತ ಸ್ಟೇಟ್ ರಚನೆಯೊಂದಿಗೆ ಸರಿಯಾದ ಪ್ರೋಗ್ರಾಂಗಳನ್ನು ಬರೆಯಲು ಸಾಧ್ಯವಾದರೆ, ಉತ್ತಮ ಆಯ್ಕೆಗಳನ್ನು ಮಾಡಲು ನಿಮಗೆ ಮಾರ್ಗದರ್ಶನ ನೀಡುವ ಕೆಲವು ತತ್ವಗಳಿವೆ:

1. **ಗುಂಪು ಸಂಬಂಧಿತ ಸ್ಟೇಟ್.** ನೀವು ಯಾವಾಗಲೂ ಒಂದೇ ಸಮಯದಲ್ಲಿ ಎರಡು ಅಥವಾ ಹೆಚ್ಚಿನ ಸ್ಟೇಟ್ ವೇರಿಯೇಬಲ್‌ಗಳನ್ನು ನವೀಕರಿಸಿದರೆ, ಅವುಗಳನ್ನು ಒಂದೇ ಸ್ಟೇಟ್ ವೇರಿಯಬಲ್‌ಗೆ ವಿಲೀನಗೊಳಿಸುವುದನ್ನು ಪರಿಗಣಿಸಿ.
2. **ಸ್ಟೇಟ್ಲಲಿ ವಿರೋಧಾಭಾಸಗಳನ್ನು ತಪ್ಪಿಸಿ.** ಸ್ಟೇಟ್ ಹಲವಾರು ತುಣುಕುಗಳು ಪರಸ್ಪರ ವಿರುದ್ಧವಾಗಿ ಮತ್ತು "ಸಮ್ಮತಿಸದಿರುವ" ರೀತಿಯಲ್ಲಿ ಸ್ಟೇಟ್ ರಚಿಸಿದಾಗ, ನೀವು ತಪ್ಪುಗಳಿಗೆ ಜಾಗವನ್ನು ಬಿಡುತ್ತೀರಿ. ಇದನ್ನು ತಪ್ಪಿಸಲು ಪ್ರಯತ್ನಿಸಿ.
3. **ಅನಗತ್ಯ ಸ್ಟೇಟ್ ತಪ್ಪಿಸಿ.** ರೆಂಡರಿಂಗ್ ಸಮಯದಲ್ಲಿ ನೀವು ಕಾಂಪೊನೆಂಟ್‌ನ ಪ್ರಾಪ್ಸ್ ಅಥವಾ ಅದರ ಅಸ್ತಿತ್ವದಲ್ಲಿರುವ ಸ್ಟೇಟ್ ವೇರಿಯೇಬಲ್‌ಗಳಿಂದ ಕೆಲವು ಮಾಹಿತಿಯನ್ನು ಲೆಕ್ಕಾಚಾರ ಮಾಡಿದರೆ, ನೀವು ಆ ಮಾಹಿತಿಯನ್ನು ಆ ಕೊಂಪೊನೆಂಟ್ ಸ್ಟೇಟ್ಗೆ ಹಾಕಬಾರದು.
4. **ಸ್ಟೇಟ್ ನಕಲು ಮಾಡುವುದನ್ನು ತಪ್ಪಿಸಿ.** ಒಂದೇ ಡೇಟಾವನ್ನು ಬಹು ಸ್ಟೇಟ್ ವೇರಿಯಬಲ್‌ಗಳ ನಡುವೆ ಅಥವಾ ನೆಸ್ಟೆಡ್ ಆಬ್ಜೆಕ್ಟ್‌ಗಳ ನಡುವೆ ನಕಲು ಮಾಡಿದಾಗ, ಅವುಗಳನ್ನು ಸಿಂಕ್‌ನಲ್ಲಿ ಇರಿಸಲು ಕಷ್ಟವಾಗುತ್ತದೆ. ನಿಮಗೆ ಸಾಧ್ಯವಾದಾಗ ನಕಲು ಕಡಿಮೆ ಮಾಡಿ.
5. **ಆಳವಾಗಿ ನೆಸ್ಟೆಡ್ ಸ್ಟೇಟ್ ತಪ್ಪಿಸಿ.** ಆಳವಾದ ಕ್ರಮಾನುಗತ ಸ್ಟೇಟ್ ನವೀಕರಿಸಲು ತುಂಬಾ ಅನುಕೂಲಕರವಾಗಿಲ್ಲ. ಸಾಧ್ಯವಾದಾಗ, ಸಮತಟ್ಟಾದ ರೀತಿಯಲ್ಲಿ ಸ್ಟೇಟ್ ರಚಿಸಲು ಆದ್ಯತೆ ನೀಡಿ.

ಈ ತತ್ವಗಳ ಹಿಂದಿನ ಗುರಿಯು _ತಪ್ಪುಗಳನ್ನು ಪರಿಚಯಿಸದೆ ಸ್ಟೇಟ್ ಸುಲಭವಾಗಿ ನವೀಕರಿಸುವುದು_. ಸ್ಟೇಟ್ದಿಂದ ಅನಗತ್ಯ ಮತ್ತು ನಕಲಿ ಡೇಟಾವನ್ನು ತೆಗೆದುಹಾಕುವುದು ಅದರ ಎಲ್ಲಾ ತುಣುಕುಗಳು ಸಿಂಕ್ ಆಗಿರುವುದನ್ನು ಖಚಿತಪಡಿಸಿಕೊಳ್ಳಲು ಸಹಾಯ ಮಾಡುತ್ತದೆ. ಇದು ಡೇಟಾಬೇಸ್ ಇಂಜಿನಿಯರ್ ದೋಷಗಳ ಸಾಧ್ಯತೆಯನ್ನು ಕಡಿಮೆ ಮಾಡಲು [ಡೇಟಾಬೇಸ್ ರಚನೆಯನ್ನು "ಸಾಮಾನ್ಯಗೊಳಿಸಲು"](https://docs.microsoft.com/en-us/office/troubleshoot/access/database-normalization-description) ಹೇಗೆ ಬಯಸಬಹುದು ಎಂಬುದನ್ನು ಹೋಲುತ್ತದೆ. ಆಲ್ಬರ್ಟ್ ಐನ್‌ಸ್ಟೈನ್‌ನನ್ನು ಪ್ಯಾರಾಫ್ರೇಸ್ ಮಾಡಲು, **"ನಿಮ್ಮ ಸ್ಥಿತಿಯನ್ನು ಸಾಧ್ಯವಾದಷ್ಟು ಸರಳಗೊಳಿಸಿ - ಆದರೆ ಸರಳವಾಗಿಲ್ಲ."**

ಈ ತತ್ವಗಳು ಕ್ರಿಯೆಯಲ್ಲಿ ಹೇಗೆ ಅನ್ವಯಿಸುತ್ತವೆ ಎಂಬುದನ್ನು ಈಗ ನೋಡೋಣ.

## ಗುಂಪು ಸಂಬಂಧಿತ ಸ್ಟೇಟ್ {/* group-related-state */}

ಏಕ ಅಥವಾ ಬಹು ಸ್ಟೇಟ್ ಅಸ್ಥಿರಗಳನ್ನು ಬಳಸುವ ನಡುವೆ ನೀವು ಕೆಲವೊಮ್ಮೆ ಖಚಿತವಾಗಿರುವುದಿಲ್ಲ.

ನೀವು ಇದನ್ನು ಮಾಡಬೇಕೇ?

```js
const [x, setX] = useState(0);
const [y, setY] = useState(0);
```

ಅಥವಾ ಇದು?

```js
const [position, setPosition] = useState({x: 0, y: 0});
```

ತಾಂತ್ರಿಕವಾಗಿ, ನೀವು ಈ ವಿಧಾನಗಳಲ್ಲಿ ಒಂದನ್ನು ಬಳಸಬಹುದು. ಆದರೆ **ಕೆಲವು ಎರಡು ಸ್ಟೇಟ್ ವೇರಿಯೇಬಲ್‌ಗಳು ಯಾವಾಗಲೂ ಒಟ್ಟಿಗೆ ಬದಲಾದರೆ, ಅವುಗಳನ್ನು ಒಂದೇ ಸ್ಟೇಟ್ ವೇರಿಯೇಬಲ್ ಆಗಿ ಏಕೀಕರಿಸುವುದು ಒಳ್ಳೆಯದು**. ನಂತರ ಅವುಗಳನ್ನು ಯಾವಾಗಲೂ ಸಿಂಕ್‌ನಲ್ಲಿ ಇರಿಸಲು ನೀವು ಮರೆಯುವುದಿಲ್ಲ, ಈ ಉದಾಹರಣೆಯಲ್ಲಿ ಕರ್ಸರ್ ಅನ್ನು ಚಲಿಸುವಾಗ ಕೆಂಪು ಚುಕ್ಕೆಯ ಎರಡೂ ನಿರ್ದೇಶಾಂಕಗಳನ್ನು ನವೀಕರಿಸಲಾಗುತ್ತದೆ:

<Sandpack>

```js
import {useState} from 'react';

export default function MovingDot() {
  const [position, setPosition] = useState({
    x: 0,
    y: 0,
  });
  return (
    <div
      onPointerMove={(e) => {
        setPosition({
          x: e.clientX,
          y: e.clientY,
        });
      }}
      style={{
        position: 'relative',
        width: '100vw',
        height: '100vh',
      }}>
      <div
        style={{
          position: 'absolute',
          backgroundColor: 'red',
          borderRadius: '50%',
          transform: `translate(${position.x}px, ${position.y}px)`,
          left: -10,
          top: -10,
          width: 20,
          height: 20,
        }}
      />
    </div>
  );
}
```

```css
body {
  margin: 0;
  padding: 0;
  height: 250px;
}
```

</Sandpack>

ನಿಮಗೆ ಎಷ್ಟು ಸ್ಟೇಟ್ ತುಣುಕುಗಳು ಬೇಕು ಎಂದು ನಿಮಗೆ ತಿಳಿದಿಲ್ಲದಿದ್ದಾಗ ನೀವು ಡೇಟಾವನ್ನು ಆಬ್ಜೆಕ್ಟ್ ಅಥವಾ ಅರೇ ಆಗಿ ಗುಂಪು ಮಾಡುವ ಇನ್ನೊಂದು ಸಂದರ್ಭವಾಗಿದೆ. ಉದಾಹರಣೆಗೆ, ಬಳಕೆದಾರರು ಕಸ್ಟಮ್ ಕ್ಷೇತ್ರಗಳನ್ನು ಸೇರಿಸಬಹುದಾದ ಫಾರ್ಮ್ ಅನ್ನು ನೀವು ಹೊಂದಿರುವಾಗ ಇದು ಸಹಾಯಕವಾಗಿರುತ್ತದೆ.

<Pitfall>

ನಿಮ್ಮ ಸ್ಟೇಟ್ ವೇರಿಯೇಬಲ್ ಒಂದು ಆಬ್ಜೆಕ್ಟ್ ಆಗಿದ್ದರೆ, ಇತರ ಕ್ಷೇತ್ರಗಳನ್ನು ಸ್ಪಷ್ಟವಾಗಿ ನಕಲಿಸದೆಯೇ [ನೀವು ಅದರಲ್ಲಿ ಒಂದು ಕ್ಷೇತ್ರವನ್ನು ಮಾತ್ರ ನವೀಕರಿಸಲು ಸಾಧ್ಯವಿಲ್ಲ](/learn/updating-objects-in-state) ಎಂಬುದನ್ನು ನೆನಪಿಡಿ. ಉದಾಹರಣೆಗೆ, ಮೇಲಿನ ಉದಾಹರಣೆಯಲ್ಲಿ ನೀವು `setPosition({ x: 100 })` ಮಾಡಲು ಸಾಧ್ಯವಿಲ್ಲ ಏಕೆಂದರೆ ಅದು `y` ಆಸ್ತಿಯನ್ನು ಹೊಂದಿರುವುದಿಲ್ಲ! ಬದಲಿಗೆ, ನೀವು `x` ಅನ್ನು ಏಕಾಂಗಿಯಾಗಿ ಹೊಂದಿಸಲು ಬಯಸಿದರೆ, ನೀವು `setPosition({ ...position, x: 100 })` ಅಥವಾ ಅವುಗಳನ್ನು ಎರಡು ರಾಜ್ಯ ವೇರಿಯೇಬಲ್‌ಗಳಾಗಿ ವಿಭಜಿಸಿ ಮತ್ತು `setX(100)` ಅನ್ನು ಮಾಡಿ.

</Pitfall>

## ಸ್ಟೇಟ್ ವಿರೋಧಾಭಾಸಗಳನ್ನು ತಪ್ಪಿಸಿ {/* avoid-contradictions-in-state */}

`isSending` ಮತ್ತು `isSent` ಸ್ಟೇಟ್ ವೇರಿಯೇಬಲ್‌ಗಳೊಂದಿಗೆ ಹೋಟೆಲ್ ಪ್ರತಿಕ್ರಿಯೆ ಫಾರ್ಮ್ ಇಲ್ಲಿದೆ:

<Sandpack>

```js
import {useState} from 'react';

export default function FeedbackForm() {
  const [text, setText] = useState('');
  const [isSending, setIsSending] = useState(false);
  const [isSent, setIsSent] = useState(false);

  async function handleSubmit(e) {
    e.preventDefault();
    setIsSending(true);
    await sendMessage(text);
    setIsSending(false);
    setIsSent(true);
  }

  if (isSent) {
    return <h1>Thanks for feedback!</h1>;
  }

  return (
    <form onSubmit={handleSubmit}>
      <p>How was your stay at The Prancing Pony?</p>
      <textarea
        disabled={isSending}
        value={text}
        onChange={(e) => setText(e.target.value)}
      />
      <br />
      <button disabled={isSending} type="submit">
        Send
      </button>
      {isSending && <p>Sending...</p>}
    </form>
  );
}

// Pretend to send a message.
function sendMessage(text) {
  return new Promise((resolve) => {
    setTimeout(resolve, 2000);
  });
}
```

</Sandpack>

ಈ ಕೋಡ್ ಕಾರ್ಯನಿರ್ವಹಿಸುತ್ತಿರುವಾಗ, ಅದು "ಅಸಾಧ್ಯ" ಸ್ಥಿತಿಗಳಿಗೆ ಬಾಗಿಲು ತೆರೆದಿರುತ್ತದೆ. ಉದಾಹರಣೆಗೆ, ನೀವು `setIsSent` ಮತ್ತು `setIsSending` ಅನ್ನು ಒಟ್ಟಿಗೆ ಕರೆಯಲು ಮರೆತರೆ, ಒಂದೇ ಸಮಯದಲ್ಲಿ `isSending` ಮತ್ತು `isSent` ಎರಡೂ `true` ಆಗಿರುವ ಪರಿಸ್ಥಿತಿಯಲ್ಲಿ ನೀವು ಕೊನೆಗೊಳ್ಳಬಹುದು. ನಿಮ್ಮ ಕೊಂಪೊನೆಂಟ್ ಹೆಚ್ಚು ಸಂಕೀರ್ಣವಾಗಿದ್ದರೆ, ಏನಾಯಿತು ಎಂಬುದನ್ನು ಅರ್ಥಮಾಡಿಕೊಳ್ಳುವುದು ಕಷ್ಟ.

**`isSending` ಮತ್ತು `isSent` ಒಂದೇ ಸಮಯದಲ್ಲಿ ಎಂದಿಗೂ `true` ಆಗಿರಬಾರದು ಎಂಬ ಕಾರಣದಿಂದ, ಅವುಗಳನ್ನು ಒಂದು `status` ಸ್ಟೇಟ್ ವೇರಿಯಬಲ್‌ನೊಂದಿಗೆ ಬದಲಾಯಿಸುವುದು ಉತ್ತಮವಾಗಿದೆ ಅದು _ಮೂರು_ ಮಾನ್ಯ ಸ್ಥಿತಿಗಳಲ್ಲಿ ಒಂದನ್ನು ತೆಗೆದುಕೊಳ್ಳಬಹುದು:** `typing'` (ಆರಂಭಿಕ ), `'sending'`, ಮತ್ತು `'sent'`:

<Sandpack>

```js
import {useState} from 'react';

export default function FeedbackForm() {
  const [text, setText] = useState('');
  const [status, setStatus] = useState('typing');

  async function handleSubmit(e) {
    e.preventDefault();
    setStatus('sending');
    await sendMessage(text);
    setStatus('sent');
  }

  const isSending = status === 'sending';
  const isSent = status === 'sent';

  if (isSent) {
    return <h1>Thanks for feedback!</h1>;
  }

  return (
    <form onSubmit={handleSubmit}>
      <p>How was your stay at The Prancing Pony?</p>
      <textarea
        disabled={isSending}
        value={text}
        onChange={(e) => setText(e.target.value)}
      />
      <br />
      <button disabled={isSending} type="submit">
        Send
      </button>
      {isSending && <p>Sending...</p>}
    </form>
  );
}

// Pretend to send a message.
function sendMessage(text) {
  return new Promise((resolve) => {
    setTimeout(resolve, 2000);
  });
}
```

</Sandpack>

ಓದಲು ನೀವು ಇನ್ನೂ ಕೆಲವು ಕೊಂಸ್ಟಂಟ್ಗಳನ್ನು ಘೋಷಿಸಬಹುದು:

```js
const isSending = status === 'sending';
const isSent = status === 'sent';
```

ಆದರೆ ಅವು ಸ್ಟೇಟ್ ವೇರಿಯೇಬಲ್‌ಗಳಲ್ಲ, ಆದ್ದರಿಂದ ಅವುಗಳು ಪರಸ್ಪರ ಸಿಂಕ್‌ನಿಂದ ಹೊರಬರುವ ಬಗ್ಗೆ ನೀವು ಚಿಂತಿಸಬೇಕಾಗಿಲ್ಲ.

## ಅನಗತ್ಯ ಸ್ಟೇಟ್ ತಪ್ಪಿಸಿ {/* avoid-redundant-state */}

ರೆಂಡರಿಂಗ್ ಸಮಯದಲ್ಲಿ ನೀವು ಕಾಂಪೊನೆಂಟ್‌ನ ಪ್ರಾಪ್ಸ್ ಅಥವಾ ಅದರ ಅಸ್ತಿತ್ವದಲ್ಲಿರುವ ಸ್ಟೇಟ್ ವೇರಿಯಬಲ್‌ಗಳಿಂದ ಕೆಲವು ಮಾಹಿತಿಯನ್ನು ಲೆಕ್ಕ ಹಾಕಬಹುದಾದರೆ, ನೀವು ಆ ಮಾಹಿತಿಯನ್ನು ಆ ಕೊಂಪೊನೆಂಟ್ ಸ್ಟೇಟ್ಗೆ **ಹಾಕಬಾರದು.**

ಉದಾಹರಣೆಗೆ, ಈ ಫಾರ್ಮ್ ಅನ್ನು ತೆಗೆದುಕೊಳ್ಳಿ. ಇದು ಕಾರ್ಯನಿರ್ವಹಿಸುತ್ತದೆ, ಆದರೆ ನೀವು ಅದರಲ್ಲಿ ಯಾವುದೇ ಅನಗತ್ಯ ಸ್ಟೇಟ್ ಕಂಡುಹಿಡಿಯಬಹುದೇ?

<Sandpack>

```js
import {useState} from 'react';

export default function Form() {
  const [firstName, setFirstName] = useState('');
  const [lastName, setLastName] = useState('');
  const [fullName, setFullName] = useState('');

  function handleFirstNameChange(e) {
    setFirstName(e.target.value);
    setFullName(e.target.value + ' ' + lastName);
  }

  function handleLastNameChange(e) {
    setLastName(e.target.value);
    setFullName(firstName + ' ' + e.target.value);
  }

  return (
    <>
      <h2>Let’s check you in</h2>
      <label>
        First name: <input value={firstName} onChange={handleFirstNameChange} />
      </label>
      <label>
        Last name: <input value={lastName} onChange={handleLastNameChange} />
      </label>
      <p>
        Your ticket will be issued to: <b>{fullName}</b>
      </p>
    </>
  );
}
```

```css
label {
  display: block;
  margin-bottom: 5px;
}
```

</Sandpack>

ಈ ಫಾರ್ಮ್ ಮೂರು ಸ್ಟೇಟ್ ವೇರಿಯಬಲ್‌ಗಳನ್ನು ಹೊಂದಿದೆ: `firstName`, `lastName`, ಮತ್ತು `fullName`. ಆದಾಗ್ಯೂ, `fullName` ಅನಗತ್ಯವಾಗಿದೆ. **ನೀವು ಯಾವಾಗಲೂ `firstName` ಮತ್ತು `lastName` ನಿಂದ `fullName` ಅನ್ನು ಲೆಕ್ಕ ಹಾಕಬಹುದು, ಆದ್ದರಿಂದ ಅದನ್ನು ಸ್ಟೇಟ್ದಿಂದ ತೆಗೆದುಹಾಕಿ.**

ನೀವು ಇದನ್ನು ಈ ರೀತಿ ಮಾಡಿ:

<Sandpack>

```js
import {useState} from 'react';

export default function Form() {
  const [firstName, setFirstName] = useState('');
  const [lastName, setLastName] = useState('');

  const fullName = firstName + ' ' + lastName;

  function handleFirstNameChange(e) {
    setFirstName(e.target.value);
  }

  function handleLastNameChange(e) {
    setLastName(e.target.value);
  }

  return (
    <>
      <h2>Let’s check you in</h2>
      <label>
        First name: <input value={firstName} onChange={handleFirstNameChange} />
      </label>
      <label>
        Last name: <input value={lastName} onChange={handleLastNameChange} />
      </label>
      <p>
        Your ticket will be issued to: <b>{fullName}</b>
      </p>
    </>
  );
}
```

```css
label {
  display: block;
  margin-bottom: 5px;
}
```

</Sandpack>

ಇಲ್ಲಿ, `fullName` ಒಂದು ಸ್ಟೇಟ್ ವೇರಿಯಬಲ್ _ಆಗಿಲ್ಲ_. ಬದಲಾಗಿ, ರೆಂಡರ್ ಸಮಯದಲ್ಲಿ ಇದನ್ನು ಲೆಕ್ಕಹಾಕಲಾಗುತ್ತದೆ:

```js
const fullName = firstName + ' ' + lastName;
```

ಪರಿಣಾಮವಾಗಿ, ಬದಲಾವಣೆ ನಿರ್ವಾಹಕರು ಅದನ್ನು ನವೀಕರಿಸಲು ವಿಶೇಷವಾದ ಏನನ್ನೂ ಮಾಡಬೇಕಾಗಿಲ್ಲ. ನೀವು `setFirstName` ಅಥವಾ `setLastName` ಎಂದು ಕರೆ ಮಾಡಿದಾಗ, ನೀವು ಮರು-ರೆಂಡರ್ ಅನ್ನು ಪ್ರಚೋದಿಸುತ್ತೀರಿ ಮತ್ತು ನಂತರ ಮುಂದಿನ `fullName` ಅನ್ನು ತಾಜಾ ಡೇಟಾದಿಂದ ಲೆಕ್ಕಹಾಕಲಾಗುತ್ತದೆ.

<DeepDive>

#### ಸ್ಟೇಟ್ದಲ್ಲಿ ಆಸರೆಗಳನ್ನು ಪ್ರತಿಬಿಂಬಿಸಬೇಡಿ {/* don-t-mirror-props-in-state */}

ಅನಗತ್ಯ ಸ್ಟೇಟ್ ಸಾಮಾನ್ಯ ಉದಾಹರಣೆಯೆಂದರೆ ಈ ರೀತಿಯ ಕೋಡ್:

```js
function Message({ messageColor }) {
  const [color, setColor] = useState(messageColor);
```

ಇಲ್ಲಿ, `color` ಸ್ಟೇಟ್ ವೇರಿಯೇಬಲ್ ಅನ್ನು `messageColor` ಪ್ರಾಪ್‌ಗೆ ಆರಂಭಿಸಲಾಗಿದೆ. ಸಮಸ್ಯೆ ಏನೆಂದರೆ **ಮೂಲ ಕೊಂಪೊನೆಂಟ್ ನಂತರ `messageColor` ನ ವಿಭಿನ್ನ ಮೌಲ್ಯವನ್ನು ರವಾನಿಸಿದರೆ (ಉದಾಹರಣೆಗೆ, `'blue'` ಬದಲಿಗೆ `'red'`), `color` _ಸ್ಟೇಟ್ ವೇರಿಯಬಲ್_ ಅನ್ನು ನವೀಕರಿಸಲಾಗುವುದಿಲ್ಲ!** ಮೊದಲ ರೆಂಡರ್ ಸಮಯದಲ್ಲಿ ಮಾತ್ರ ಸ್ಟೇಟ್ ಪ್ರಾರಂಭಿಸಲಾಗುತ್ತದೆ.

ಇದಕ್ಕಾಗಿಯೇ ಸ್ಟೇಟ್ ವೇರಿಯಬಲ್‌ನಲ್ಲಿ ಕೆಲವು ಆಸರೆಗಳನ್ನು "ಪ್ರತಿಬಿಂಬಿಸುವುದು" ಗೊಂದಲಕ್ಕೆ ಕಾರಣವಾಗಬಹುದು. ಬದಲಿಗೆ, ನಿಮ್ಮ ಕೋಡ್‌ನಲ್ಲಿ ನೇರವಾಗಿ `messageColor` ಪ್ರಾಪ್ ಅನ್ನು ಬಳಸಿ. ನೀವು ಚಿಕ್ಕ ಹೆಸರನ್ನು ನೀಡಲು ಬಯಸಿದರೆ, ಕೊಂಸ್ಟಂಟ್ವನ್ನು ಬಳಸಿ:

```js
function Message({ messageColor }) {
  const color = messageColor;
```

ಈ ರೀತಿಯಲ್ಲಿ ಇದು ಮೂಲ ಕೊಂಪೊನೆಂಟ್ದಿಂದ ರವಾನಿಸಲಾದ ಪ್ರಾಪ್‌ನೊಂದಿಗೆ ಸಿಂಕ್‌ನಿಂದ ಹೊರಬರುವುದಿಲ್ಲ.

ನಿರ್ದಿಷ್ಟ ಪ್ರಾಪ್‌ಗಾಗಿ ಎಲ್ಲಾ ನವೀಕರಣಗಳನ್ನು ನಿರ್ಲಕ್ಷಿಸಲು ನೀವು _ಬಯಸಿದಾಗ_ ಮಾತ್ರ ಪ್ರಾಪ್‌ಗಳನ್ನು ಸ್ಟೇಟ್ಗೆ ಪ್ರತಿಬಿಂಬಿಸುವುದು ಅರ್ಥಪೂರ್ಣವಾಗಿರುತ್ತದೆ. ಸಂಪ್ರದಾಯದ ಮೂಲಕ, ಅದರ ಹೊಸ ಮೌಲ್ಯಗಳನ್ನು ನಿರ್ಲಕ್ಷಿಸಲಾಗಿದೆ ಎಂಬುದನ್ನು ಸ್ಪಷ್ಟಪಡಿಸಲು ಪ್ರಾಪ್ ಹೆಸರನ್ನು `initial` ಅಥವಾ `default` ನೊಂದಿಗೆ ಪ್ರಾರಂಭಿಸಿ:

```js
function Message({ initialColor }) {
  // The `color` state variable holds the *first* value of `initialColor`.
  // Further changes to the `initialColor` prop are ignored.
  const [color, setColor] = useState(initialColor);
```

</DeepDive>

## ಸ್ಟೇಟ್ದಲ್ಲಿ ನಕಲು ಮಾಡುವುದನ್ನು ತಪ್ಪಿಸಿ {/* avoid-duplication-in-state */}

ಈ ಮೆನು ಪಟ್ಟಿ ಕೊಂಪೊನೆಂಟ್ ನಿಮಗೆ ಹಲವಾರು ಪ್ರಯಾಣದ ತಿಂಡಿಗಳನ್ನು ಆಯ್ಕೆ ಮಾಡಲು ಅನುಮತಿಸುತ್ತದೆ:

<Sandpack>

```js
import {useState} from 'react';

const initialItems = [
  {title: 'pretzels', id: 0},
  {title: 'crispy seaweed', id: 1},
  {title: 'granola bar', id: 2},
];

export default function Menu() {
  const [items, setItems] = useState(initialItems);
  const [selectedItem, setSelectedItem] = useState(items[0]);

  return (
    <>
      <h2>What's your travel snack?</h2>
      <ul>
        {items.map((item) => (
          <li key={item.id}>
            {item.title}{' '}
            <button
              onClick={() => {
                setSelectedItem(item);
              }}>
              Choose
            </button>
          </li>
        ))}
      </ul>
      <p>You picked {selectedItem.title}.</p>
    </>
  );
}
```

```css
button {
  margin-top: 10px;
}
```

</Sandpack>

ಪ್ರಸ್ತುತ, ಇದು ಆಯ್ದ ಐಟಂ ಅನ್ನು ಆಬ್ಜೆಕ್ಟನಂತೆ `selectedItem` ಸ್ಟೇಟ್ ವೇರಿಯೇಬಲ್‌ನಲ್ಲಿ ಸಂಗ್ರಹಿಸುತ್ತದೆ. ಆದಾಗ್ಯೂ, ಇದು ಉತ್ತಮವಾಗಿಲ್ಲ: **`selectedItem` ವಿಷಯಗಳು `items` ಪಟ್ಟಿಯೊಳಗಿನ ಐಟಂಗಳಲ್ಲಿ ಒಂದರಂತೆಯೇ ಒಂದೇ ಆಬ್ಜೆಕ್ಟವಾಗಿದೆ.** ಇದರರ್ಥ ಐಟಂ ಬಗ್ಗೆ ಮಾಹಿತಿಯನ್ನು ಎರಡು ಸ್ಥಳಗಳಲ್ಲಿ ನಕಲು ಮಾಡಲಾಗಿದೆ.

ಇದು ಏಕೆ ಸಮಸ್ಯೆಯಾಗಿದೆ? ಪ್ರತಿಯೊಂದು ಐಟಂ ಅನ್ನು ತಿದ್ದುವಂತೆ ಮಾಡೋಣ:

<Sandpack>

```js
import {useState} from 'react';

const initialItems = [
  {title: 'pretzels', id: 0},
  {title: 'crispy seaweed', id: 1},
  {title: 'granola bar', id: 2},
];

export default function Menu() {
  const [items, setItems] = useState(initialItems);
  const [selectedItem, setSelectedItem] = useState(items[0]);

  function handleItemChange(id, e) {
    setItems(
      items.map((item) => {
        if (item.id === id) {
          return {
            ...item,
            title: e.target.value,
          };
        } else {
          return item;
        }
      })
    );
  }

  return (
    <>
      <h2>What's your travel snack?</h2>
      <ul>
        {items.map((item, index) => (
          <li key={item.id}>
            <input
              value={item.title}
              onChange={(e) => {
                handleItemChange(item.id, e);
              }}
            />{' '}
            <button
              onClick={() => {
                setSelectedItem(item);
              }}>
              Choose
            </button>
          </li>
        ))}
      </ul>
      <p>You picked {selectedItem.title}.</p>
    </>
  );
}
```

```css
button {
  margin-top: 10px;
}
```

</Sandpack>

ನೀವು ಮೊದಲು ಐಟಂ ಮೇಲೆ "Choose" ಕ್ಲಿಕ್ ಮಾಡಿ _ನಂತರ_ ಅದನ್ನು ಎಡಿಟ್ ಮಾಡಿದರೆ, **ಇನ್‌ಪುಟ್ ಅನ್ನು ನವೀಕರಿಸಲಾಗುತ್ತದೆ ಆದರೆ ಕೆಳಭಾಗದಲ್ಲಿರುವ ಲೇಬಲ್ ಸಂಪಾದನೆಗಳನ್ನು ಪ್ರತಿಬಿಂಬಿಸುವುದಿಲ್ಲ.** ಏಕೆಂದರೆ ನೀವು ನಕಲು ಸ್ಟೇಟ್ ಹೊಂದಿದ್ದೀರಿ ಮತ್ತು ನೀವು `selectedItem` ಅನ್ನು ನವೀಕರಿಸಲು ಮರೆತಿದ್ದೀರಿ..

ನೀವು `selectedItem` ಅನ್ನು ನವೀಕರಿಸಬಹುದಾದರೂ, ನಕಲು ತೆಗೆದುಹಾಕುವುದು ಸುಲಭವಾದ ಪರಿಹಾರವಾಗಿದೆ. ಈ ಉದಾಹರಣೆಯಲ್ಲಿ, `selectedItem` ಆಬ್ಜೆಕ್ಟ್‌ನ ಬದಲಿಗೆ (ಇದು `items` ಒಳಗೆ ವಸ್ತುಗಳೊಂದಿಗೆ ನಕಲು ರಚಿಸುತ್ತದೆ), ನೀವು `selectedId` ಅನ್ನು ಸ್ಟೇಟ್ದಲ್ಲಿ ಹಿಡಿದಿಟ್ಟುಕೊಳ್ಳಿ, _ನಂತರ_ `items` ಅರೇ ಅನ್ನು ಹುಡುಕುವ ಮೂಲಕ `selectedItem` ಅನ್ನು ಪಡೆಯಿರಿ ಆ ಐಡಿ ಹೊಂದಿರುವ ಐಟಂ:

<Sandpack>

```js
import {useState} from 'react';

const initialItems = [
  {title: 'pretzels', id: 0},
  {title: 'crispy seaweed', id: 1},
  {title: 'granola bar', id: 2},
];

export default function Menu() {
  const [items, setItems] = useState(initialItems);
  const [selectedId, setSelectedId] = useState(0);

  const selectedItem = items.find((item) => item.id === selectedId);

  function handleItemChange(id, e) {
    setItems(
      items.map((item) => {
        if (item.id === id) {
          return {
            ...item,
            title: e.target.value,
          };
        } else {
          return item;
        }
      })
    );
  }

  return (
    <>
      <h2>What's your travel snack?</h2>
      <ul>
        {items.map((item, index) => (
          <li key={item.id}>
            <input
              value={item.title}
              onChange={(e) => {
                handleItemChange(item.id, e);
              }}
            />{' '}
            <button
              onClick={() => {
                setSelectedId(item.id);
              }}>
              Choose
            </button>
          </li>
        ))}
      </ul>
      <p>You picked {selectedItem.title}.</p>
    </>
  );
}
```

```css
button {
  margin-top: 10px;
}
```

</Sandpack>

(ಪರ್ಯಾಯವಾಗಿ, ನೀವು ಆಯ್ಕೆಮಾಡಿದ ಸೂಚಿಯನ್ನು ಸ್ಟೇಟ್ದಲ್ಲಿ ಹಿಡಿದಿಟ್ಟುಕೊಳ್ಳಬಹುದು.)
ಸ್ಟೇಟ್ವನ್ನು ಈ ರೀತಿ ನಕಲು ಮಾಡಲಾಗುತ್ತಿತ್ತು:

- `items = [{ id: 0, title: 'pretzels'}, ...]`
- `selectedItem = {id: 0, title: 'pretzels'}`

ಆದರೆ ಬದಲಾವಣೆಯ ನಂತರ ಅದು ಹೀಗಿದೆ:

- `items = [{ id: 0, title: 'pretzels'}, ...]`
- `selectedId = 0`

ನಕಲು ಹೋಗಿದೆ, ಮತ್ತು ನೀವು ಅಗತ್ಯ ಸ್ಟೇಟ್ ಮಾತ್ರ ಇಟ್ಟುಕೊಳ್ಳುತ್ತೀರಿ!

ಈಗ ನೀವು _ಆಯ್ಕೆ ಮಾಡಿದ_ ಐಟಂ ಅನ್ನು ಎಡಿಟ್ ಮಾಡಿದರೆ, ಕೆಳಗಿನ ಸಂದೇಶವು ತಕ್ಷಣವೇ ನವೀಕರಿಸುತ್ತದೆ. ಏಕೆಂದರೆ `setItems` ಮರು-ರೆಂಡರ್ ಅನ್ನು ಪ್ರಚೋದಿಸುತ್ತದೆ ಮತ್ತು `items.find(...)` ನವೀಕರಿಸಿದ ಶೀರ್ಷಿಕೆಯೊಂದಿಗೆ ಐಟಂ ಅನ್ನು ಹುಡುಕುತ್ತದೆ. ನೀವು _ಆಯ್ಕೆ ಮಾಡಿದ ಐಟಂ_ ಅನ್ನು ಸ್ಟೇಟ್ದಲ್ಲಿ ಹಿಡಿದಿಟ್ಟುಕೊಳ್ಳುವ ಅಗತ್ಯವಿಲ್ಲ, ಏಕೆಂದರೆ _ಆಯ್ಕೆ ಮಾಡಿದ ID_ ಮಾತ್ರ ಅತ್ಯಗತ್ಯ. ರೆಂಡರ್ ಸಮಯದಲ್ಲಿ ಉಳಿದವನ್ನು ಲೆಕ್ಕ ಹಾಕಬಹುದು.

## ಆಳವಾಗಿ ನೆಸ್ಟೆಡ್ ಸ್ಟೇಟ್ ತಪ್ಪಿಸಿ {/* avoid-deeply-nested-state */}

ಗ್ರಹಗಳು, ಖಂಡಗಳು ಮತ್ತು ದೇಶಗಳನ್ನು ಒಳಗೊಂಡಿರುವ ಪ್ರಯಾಣದ ಯೋಜನೆಯನ್ನು ಕಲ್ಪಿಸಿಕೊಳ್ಳಿ. ಈ ಉದಾಹರಣೆಯಲ್ಲಿರುವಂತೆ ನೆಸ್ಟೆಡ್ ಆಬ್ಜೆಕ್ಟ್‌ಗಳು ಮತ್ತು ಅರೇಗಳನ್ನು ಬಳಸಿಕೊಂಡು ಅದರ ಸ್ಟೇಟ್ ರಚಿಸಲು ನೀವು ಪ್ರಚೋದಿಸಬಹುದು:

<Sandpack>

```js
import {useState} from 'react';
import {initialTravelPlan} from './places.js';

function PlaceTree({place}) {
  const childPlaces = place.childPlaces;
  return (
    <li>
      {place.title}
      {childPlaces.length > 0 && (
        <ol>
          {childPlaces.map((place) => (
            <PlaceTree key={place.id} place={place} />
          ))}
        </ol>
      )}
    </li>
  );
}

export default function TravelPlan() {
  const [plan, setPlan] = useState(initialTravelPlan);
  const planets = plan.childPlaces;
  return (
    <>
      <h2>Places to visit</h2>
      <ol>
        {planets.map((place) => (
          <PlaceTree key={place.id} place={place} />
        ))}
      </ol>
    </>
  );
}
```

```js src/places.js active
export const initialTravelPlan = {
  id: 0,
  title: '(Root)',
  childPlaces: [
    {
      id: 1,
      title: 'Earth',
      childPlaces: [
        {
          id: 2,
          title: 'Africa',
          childPlaces: [
            {
              id: 3,
              title: 'Botswana',
              childPlaces: [],
            },
            {
              id: 4,
              title: 'Egypt',
              childPlaces: [],
            },
            {
              id: 5,
              title: 'Kenya',
              childPlaces: [],
            },
            {
              id: 6,
              title: 'Madagascar',
              childPlaces: [],
            },
            {
              id: 7,
              title: 'Morocco',
              childPlaces: [],
            },
            {
              id: 8,
              title: 'Nigeria',
              childPlaces: [],
            },
            {
              id: 9,
              title: 'South Africa',
              childPlaces: [],
            },
          ],
        },
        {
          id: 10,
          title: 'Americas',
          childPlaces: [
            {
              id: 11,
              title: 'Argentina',
              childPlaces: [],
            },
            {
              id: 12,
              title: 'Brazil',
              childPlaces: [],
            },
            {
              id: 13,
              title: 'Barbados',
              childPlaces: [],
            },
            {
              id: 14,
              title: 'Canada',
              childPlaces: [],
            },
            {
              id: 15,
              title: 'Jamaica',
              childPlaces: [],
            },
            {
              id: 16,
              title: 'Mexico',
              childPlaces: [],
            },
            {
              id: 17,
              title: 'Trinidad and Tobago',
              childPlaces: [],
            },
            {
              id: 18,
              title: 'Venezuela',
              childPlaces: [],
            },
          ],
        },
        {
          id: 19,
          title: 'Asia',
          childPlaces: [
            {
              id: 20,
              title: 'China',
              childPlaces: [],
            },
            {
              id: 21,
              title: 'India',
              childPlaces: [],
            },
            {
              id: 22,
              title: 'Singapore',
              childPlaces: [],
            },
            {
              id: 23,
              title: 'South Korea',
              childPlaces: [],
            },
            {
              id: 24,
              title: 'Thailand',
              childPlaces: [],
            },
            {
              id: 25,
              title: 'Vietnam',
              childPlaces: [],
            },
          ],
        },
        {
          id: 26,
          title: 'Europe',
          childPlaces: [
            {
              id: 27,
              title: 'Croatia',
              childPlaces: [],
            },
            {
              id: 28,
              title: 'France',
              childPlaces: [],
            },
            {
              id: 29,
              title: 'Germany',
              childPlaces: [],
            },
            {
              id: 30,
              title: 'Italy',
              childPlaces: [],
            },
            {
              id: 31,
              title: 'Portugal',
              childPlaces: [],
            },
            {
              id: 32,
              title: 'Spain',
              childPlaces: [],
            },
            {
              id: 33,
              title: 'Turkey',
              childPlaces: [],
            },
          ],
        },
        {
          id: 34,
          title: 'Oceania',
          childPlaces: [
            {
              id: 35,
              title: 'Australia',
              childPlaces: [],
            },
            {
              id: 36,
              title: 'Bora Bora (French Polynesia)',
              childPlaces: [],
            },
            {
              id: 37,
              title: 'Easter Island (Chile)',
              childPlaces: [],
            },
            {
              id: 38,
              title: 'Fiji',
              childPlaces: [],
            },
            {
              id: 39,
              title: 'Hawaii (the USA)',
              childPlaces: [],
            },
            {
              id: 40,
              title: 'New Zealand',
              childPlaces: [],
            },
            {
              id: 41,
              title: 'Vanuatu',
              childPlaces: [],
            },
          ],
        },
      ],
    },
    {
      id: 42,
      title: 'Moon',
      childPlaces: [
        {
          id: 43,
          title: 'Rheita',
          childPlaces: [],
        },
        {
          id: 44,
          title: 'Piccolomini',
          childPlaces: [],
        },
        {
          id: 45,
          title: 'Tycho',
          childPlaces: [],
        },
      ],
    },
    {
      id: 46,
      title: 'Mars',
      childPlaces: [
        {
          id: 47,
          title: 'Corn Town',
          childPlaces: [],
        },
        {
          id: 48,
          title: 'Green Hill',
          childPlaces: [],
        },
      ],
    },
  ],
};
```

</Sandpack>

ಈಗ ನೀವು ಈಗಾಗಲೇ ಭೇಟಿ ನೀಡಿದ ಸ್ಥಳವನ್ನು ಅಳಿಸಲು ನೀವು ಬಟನ್ ಅನ್ನು ಸೇರಿಸಲು ಬಯಸುತ್ತೀರಿ ಎಂದು ಹೇಳೋಣ. ನೀವು ಅದರ ಬಗ್ಗೆ ಹೇಗೆ ಹೋಗುತ್ತೀರಿ? [ಅಪ್‌ಡೇಟ್ ನೆಸ್ಟೆಡ್ ಸ್ಟೇಟ್](/learn/updating-objects-in-state#updating-a-nested-object) ಬದಲಾದ ಭಾಗದಿಂದ ಎಲ್ಲಾ ರೀತಿಯಲ್ಲಿ ಆಬ್ಜೆಕ್ಟಗಳ ನಕಲು ಮಾಡುವುದನ್ನು ಒಳಗೊಂಡಿರುತ್ತದೆ. ಆಳವಾದ ನೆಸ್ಟೆಡ್ ಸ್ಟೇಟವನ್ನು ಅಳಿಸುವುದು ಅದರ ಸಂಪೂರ್ಣ ಪೋಷಕ ಸ್ಥಳ ಸರಪಳಿಯನ್ನು ನಕಲಿಸುವುದನ್ನು ಒಳಗೊಂಡಿರುತ್ತದೆ. ಅಂತಹ ಕೋಡ್ ತುಂಬಾ ಮೌಖಿಕವಾಗಿರಬಹುದು.

**ಸ್ಟೇಟ್ ಸುಲಭವಾಗಿ ನವೀಕರಿಸಲು ತುಂಬಾ ನೆಸ್ಟೆಡ್ ಆಗಿದ್ದರೆ, ಅದನ್ನು "ಫ್ಲಾಟ್" ಮಾಡಲು ಪರಿಗಣಿಸಿ.** ಈ ಡೇಟಾವನ್ನು ನೀವು ಪುನರ್ರಚಿಸುವ ಒಂದು ಮಾರ್ಗ ಇಲ್ಲಿದೆ. ಪ್ರತಿ `place` _ಅದರ ಮಕ್ಕಳ ಸ್ಥಳಗಳ_ ಅರೇಯನ್ನು ಹೊಂದಿರುವ ಮರದಂತಹ ರಚನೆಯ ಬದಲಿಗೆ, ನೀವು ಪ್ರತಿ ಸ್ಥಳವು _ಅದರ ಮಕ್ಕಳ ಸ್ಥಳ ID ಗಳ_ ಅರೇಯನ್ನು ಹಿಡಿದಿಟ್ಟುಕೊಳ್ಳಬಹುದು. ನಂತರ ಪ್ರತಿ ಸ್ಥಳದ ID ಯಿಂದ ಅನುಗುಣವಾದ ಸ್ಥಳಕ್ಕೆ ಮ್ಯಾಪಿಂಗ್ ಅನ್ನು ಸಂಗ್ರಹಿಸಿ.

ಈ ಡೇಟಾ ಪುನರ್ರಚನೆಯು ಡೇಟಾಬೇಸ್ ಟೇಬಲ್ ಅನ್ನು ನೋಡುವುದನ್ನು ನಿಮಗೆ ನೆನಪಿಸಬಹುದು:

<Sandpack>

```js
import {useState} from 'react';
import {initialTravelPlan} from './places.js';

function PlaceTree({id, placesById}) {
  const place = placesById[id];
  const childIds = place.childIds;
  return (
    <li>
      {place.title}
      {childIds.length > 0 && (
        <ol>
          {childIds.map((childId) => (
            <PlaceTree key={childId} id={childId} placesById={placesById} />
          ))}
        </ol>
      )}
    </li>
  );
}

export default function TravelPlan() {
  const [plan, setPlan] = useState(initialTravelPlan);
  const root = plan[0];
  const planetIds = root.childIds;
  return (
    <>
      <h2>Places to visit</h2>
      <ol>
        {planetIds.map((id) => (
          <PlaceTree key={id} id={id} placesById={plan} />
        ))}
      </ol>
    </>
  );
}
```

```js src/places.js active
export const initialTravelPlan = {
  0: {
    id: 0,
    title: '(Root)',
    childIds: [1, 42, 46],
  },
  1: {
    id: 1,
    title: 'Earth',
    childIds: [2, 10, 19, 26, 34],
  },
  2: {
    id: 2,
    title: 'Africa',
    childIds: [3, 4, 5, 6, 7, 8, 9],
  },
  3: {
    id: 3,
    title: 'Botswana',
    childIds: [],
  },
  4: {
    id: 4,
    title: 'Egypt',
    childIds: [],
  },
  5: {
    id: 5,
    title: 'Kenya',
    childIds: [],
  },
  6: {
    id: 6,
    title: 'Madagascar',
    childIds: [],
  },
  7: {
    id: 7,
    title: 'Morocco',
    childIds: [],
  },
  8: {
    id: 8,
    title: 'Nigeria',
    childIds: [],
  },
  9: {
    id: 9,
    title: 'South Africa',
    childIds: [],
  },
  10: {
    id: 10,
    title: 'Americas',
    childIds: [11, 12, 13, 14, 15, 16, 17, 18],
  },
  11: {
    id: 11,
    title: 'Argentina',
    childIds: [],
  },
  12: {
    id: 12,
    title: 'Brazil',
    childIds: [],
  },
  13: {
    id: 13,
    title: 'Barbados',
    childIds: [],
  },
  14: {
    id: 14,
    title: 'Canada',
    childIds: [],
  },
  15: {
    id: 15,
    title: 'Jamaica',
    childIds: [],
  },
  16: {
    id: 16,
    title: 'Mexico',
    childIds: [],
  },
  17: {
    id: 17,
    title: 'Trinidad and Tobago',
    childIds: [],
  },
  18: {
    id: 18,
    title: 'Venezuela',
    childIds: [],
  },
  19: {
    id: 19,
    title: 'Asia',
    childIds: [20, 21, 22, 23, 24, 25],
  },
  20: {
    id: 20,
    title: 'China',
    childIds: [],
  },
  21: {
    id: 21,
    title: 'India',
    childIds: [],
  },
  22: {
    id: 22,
    title: 'Singapore',
    childIds: [],
  },
  23: {
    id: 23,
    title: 'South Korea',
    childIds: [],
  },
  24: {
    id: 24,
    title: 'Thailand',
    childIds: [],
  },
  25: {
    id: 25,
    title: 'Vietnam',
    childIds: [],
  },
  26: {
    id: 26,
    title: 'Europe',
    childIds: [27, 28, 29, 30, 31, 32, 33],
  },
  27: {
    id: 27,
    title: 'Croatia',
    childIds: [],
  },
  28: {
    id: 28,
    title: 'France',
    childIds: [],
  },
  29: {
    id: 29,
    title: 'Germany',
    childIds: [],
  },
  30: {
    id: 30,
    title: 'Italy',
    childIds: [],
  },
  31: {
    id: 31,
    title: 'Portugal',
    childIds: [],
  },
  32: {
    id: 32,
    title: 'Spain',
    childIds: [],
  },
  33: {
    id: 33,
    title: 'Turkey',
    childIds: [],
  },
  34: {
    id: 34,
    title: 'Oceania',
    childIds: [35, 36, 37, 38, 39, 40, 41],
  },
  35: {
    id: 35,
    title: 'Australia',
    childIds: [],
  },
  36: {
    id: 36,
    title: 'Bora Bora (French Polynesia)',
    childIds: [],
  },
  37: {
    id: 37,
    title: 'Easter Island (Chile)',
    childIds: [],
  },
  38: {
    id: 38,
    title: 'Fiji',
    childIds: [],
  },
  39: {
    id: 40,
    title: 'Hawaii (the USA)',
    childIds: [],
  },
  40: {
    id: 40,
    title: 'New Zealand',
    childIds: [],
  },
  41: {
    id: 41,
    title: 'Vanuatu',
    childIds: [],
  },
  42: {
    id: 42,
    title: 'Moon',
    childIds: [43, 44, 45],
  },
  43: {
    id: 43,
    title: 'Rheita',
    childIds: [],
  },
  44: {
    id: 44,
    title: 'Piccolomini',
    childIds: [],
  },
  45: {
    id: 45,
    title: 'Tycho',
    childIds: [],
  },
  46: {
    id: 46,
    title: 'Mars',
    childIds: [47, 48],
  },
  47: {
    id: 47,
    title: 'Corn Town',
    childIds: [],
  },
  48: {
    id: 48,
    title: 'Green Hill',
    childIds: [],
  },
};
```

</Sandpack>

**ಈಗ ಸ್ಟೇಟ್ "ಫ್ಲಾಟ್" ಆಗಿದೆ (ಇದನ್ನು "ನೊರ್ಮಲ್ಯ್ಜ಼ೆಡ್" ಎಂದೂ ಕರೆಯಲಾಗುತ್ತದೆ), ನೆಸ್ಟೆಡ್ ಐಟಂಗಳನ್ನು ನವೀಕರಿಸುವುದು ಸುಲಭವಾಗುತ್ತದೆ.**

ಇದೀಗ ಸ್ಥಳವನ್ನು ತೆಗೆದುಹಾಕಲು, ನೀವು ಕೇವಲ ಎರಡು ಹಂತದ ಸ್ಟೇಟ್ ನವೀಕರಿಸಬೇಕಾಗಿದೆ:

- ಅದರ _ಪೋಷಕ_ ಸ್ಥಳದ ನವೀಕರಿಸಿದ ಆವೃತ್ತಿಯು ತೆಗೆದುಹಾಕಲಾದ ID ಅನ್ನು ಅದರ `childIds` ಅರೇಯಿಂದ ಹೊರಗಿಡಬೇಕು.
- ಮೂಲ "ಟೇಬಲ್" ವಸ್ತುವಿನ ನವೀಕರಿಸಿದ ಆವೃತ್ತಿಯು ಮೂಲ ಸ್ಥಳದ ನವೀಕರಿಸಿದ ಆವೃತ್ತಿಯನ್ನು ಒಳಗೊಂಡಿರಬೇಕು.

ನೀವು ಅದರ ಬಗ್ಗೆ ಹೇಗೆ ಹೋಗಬಹುದು ಎಂಬುದರ ಉದಾಹರಣೆ ಇಲ್ಲಿದೆ:

<Sandpack>

```js
import {useState} from 'react';
import {initialTravelPlan} from './places.js';

export default function TravelPlan() {
  const [plan, setPlan] = useState(initialTravelPlan);

  function handleComplete(parentId, childId) {
    const parent = plan[parentId];
    // Create a new version of the parent place
    // that doesn't include this child ID.
    const nextParent = {
      ...parent,
      childIds: parent.childIds.filter((id) => id !== childId),
    };
    // Update the root state object...
    setPlan({
      ...plan,
      // ...so that it has the updated parent.
      [parentId]: nextParent,
    });
  }

  const root = plan[0];
  const planetIds = root.childIds;
  return (
    <>
      <h2>Places to visit</h2>
      <ol>
        {planetIds.map((id) => (
          <PlaceTree
            key={id}
            id={id}
            parentId={0}
            placesById={plan}
            onComplete={handleComplete}
          />
        ))}
      </ol>
    </>
  );
}

function PlaceTree({id, parentId, placesById, onComplete}) {
  const place = placesById[id];
  const childIds = place.childIds;
  return (
    <li>
      {place.title}
      <button
        onClick={() => {
          onComplete(parentId, id);
        }}>
        Complete
      </button>
      {childIds.length > 0 && (
        <ol>
          {childIds.map((childId) => (
            <PlaceTree
              key={childId}
              id={childId}
              parentId={id}
              placesById={placesById}
              onComplete={onComplete}
            />
          ))}
        </ol>
      )}
    </li>
  );
}
```

```js src/places.js
export const initialTravelPlan = {
  0: {
    id: 0,
    title: '(Root)',
    childIds: [1, 42, 46],
  },
  1: {
    id: 1,
    title: 'Earth',
    childIds: [2, 10, 19, 26, 34],
  },
  2: {
    id: 2,
    title: 'Africa',
    childIds: [3, 4, 5, 6, 7, 8, 9],
  },
  3: {
    id: 3,
    title: 'Botswana',
    childIds: [],
  },
  4: {
    id: 4,
    title: 'Egypt',
    childIds: [],
  },
  5: {
    id: 5,
    title: 'Kenya',
    childIds: [],
  },
  6: {
    id: 6,
    title: 'Madagascar',
    childIds: [],
  },
  7: {
    id: 7,
    title: 'Morocco',
    childIds: [],
  },
  8: {
    id: 8,
    title: 'Nigeria',
    childIds: [],
  },
  9: {
    id: 9,
    title: 'South Africa',
    childIds: [],
  },
  10: {
    id: 10,
    title: 'Americas',
    childIds: [11, 12, 13, 14, 15, 16, 17, 18],
  },
  11: {
    id: 11,
    title: 'Argentina',
    childIds: [],
  },
  12: {
    id: 12,
    title: 'Brazil',
    childIds: [],
  },
  13: {
    id: 13,
    title: 'Barbados',
    childIds: [],
  },
  14: {
    id: 14,
    title: 'Canada',
    childIds: [],
  },
  15: {
    id: 15,
    title: 'Jamaica',
    childIds: [],
  },
  16: {
    id: 16,
    title: 'Mexico',
    childIds: [],
  },
  17: {
    id: 17,
    title: 'Trinidad and Tobago',
    childIds: [],
  },
  18: {
    id: 18,
    title: 'Venezuela',
    childIds: [],
  },
  19: {
    id: 19,
    title: 'Asia',
    childIds: [20, 21, 22, 23, 24, 25],
  },
  20: {
    id: 20,
    title: 'China',
    childIds: [],
  },
  21: {
    id: 21,
    title: 'India',
    childIds: [],
  },
  22: {
    id: 22,
    title: 'Singapore',
    childIds: [],
  },
  23: {
    id: 23,
    title: 'South Korea',
    childIds: [],
  },
  24: {
    id: 24,
    title: 'Thailand',
    childIds: [],
  },
  25: {
    id: 25,
    title: 'Vietnam',
    childIds: [],
  },
  26: {
    id: 26,
    title: 'Europe',
    childIds: [27, 28, 29, 30, 31, 32, 33],
  },
  27: {
    id: 27,
    title: 'Croatia',
    childIds: [],
  },
  28: {
    id: 28,
    title: 'France',
    childIds: [],
  },
  29: {
    id: 29,
    title: 'Germany',
    childIds: [],
  },
  30: {
    id: 30,
    title: 'Italy',
    childIds: [],
  },
  31: {
    id: 31,
    title: 'Portugal',
    childIds: [],
  },
  32: {
    id: 32,
    title: 'Spain',
    childIds: [],
  },
  33: {
    id: 33,
    title: 'Turkey',
    childIds: [],
  },
  34: {
    id: 34,
    title: 'Oceania',
    childIds: [35, 36, 37, 38, 39, 40, 41],
  },
  35: {
    id: 35,
    title: 'Australia',
    childIds: [],
  },
  36: {
    id: 36,
    title: 'Bora Bora (French Polynesia)',
    childIds: [],
  },
  37: {
    id: 37,
    title: 'Easter Island (Chile)',
    childIds: [],
  },
  38: {
    id: 38,
    title: 'Fiji',
    childIds: [],
  },
  39: {
    id: 39,
    title: 'Hawaii (the USA)',
    childIds: [],
  },
  40: {
    id: 40,
    title: 'New Zealand',
    childIds: [],
  },
  41: {
    id: 41,
    title: 'Vanuatu',
    childIds: [],
  },
  42: {
    id: 42,
    title: 'Moon',
    childIds: [43, 44, 45],
  },
  43: {
    id: 43,
    title: 'Rheita',
    childIds: [],
  },
  44: {
    id: 44,
    title: 'Piccolomini',
    childIds: [],
  },
  45: {
    id: 45,
    title: 'Tycho',
    childIds: [],
  },
  46: {
    id: 46,
    title: 'Mars',
    childIds: [47, 48],
  },
  47: {
    id: 47,
    title: 'Corn Town',
    childIds: [],
  },
  48: {
    id: 48,
    title: 'Green Hill',
    childIds: [],
  },
};
```

```css
button {
  margin: 10px;
}
```

</Sandpack>

ನೀವು ಇಷ್ಟಪಡುವಷ್ಟು ಗೂಡಿನ ಸ್ಟೇಟ್ ನೀವು ಮಾಡಬಹುದು, ಆದರೆ ಅದನ್ನು "ಫ್ಲಾಟ್" ಮಾಡುವುದರಿಂದ ಹಲವಾರು ಸಮಸ್ಯೆಗಳನ್ನು ಪರಿಹರಿಸಬಹುದು. ಇದು ಸ್ಟೇಟ್ ನವೀಕರಿಸಲು ಸುಲಭಗೊಳಿಸುತ್ತದೆ ಮತ್ತು ನೆಸ್ಟೆಡ್ ಆಬ್ಜೆಕ್ಟವಿನ ವಿವಿಧ ಭಾಗಗಳಲ್ಲಿ ನೀವು ನಕಲು ಹೊಂದಿಲ್ಲ ಎಂದು ಖಚಿತಪಡಿಸಿಕೊಳ್ಳಲು ಇದು ಸಹಾಯ ಮಾಡುತ್ತದೆ.

<DeepDive>

#### ಮೆಮೊರಿ ಬಳಕೆಯನ್ನು ಸುಧಾರಿಸುವುದು {/* improving-memory-usage */}

ತಾತ್ತ್ವಿಕವಾಗಿ, ಮೆಮೊರಿ ಬಳಕೆಯನ್ನು ಸುಧಾರಿಸಲು ನೀವು "ಟೇಬಲ್" ಆಬ್ಜೆಕ್ಟನಿಂದ ಅಳಿಸಲಾದ ಐಟಂಗಳನ್ನು (ಮತ್ತು ಅವರ ಮಕ್ಕಳು!) ತೆಗೆದುಹಾಕುತ್ತೀರಿ. ಈ ಆವೃತ್ತಿಯು ಅದನ್ನು ಮಾಡುತ್ತದೆ. ಅಪ್‌ಡೇಟ್ ತರ್ಕವನ್ನು ಹೆಚ್ಚು ಸಂಕ್ಷಿಪ್ತಗೊಳಿಸಲು ಇದು [ಇಮ್ಮರ್ ಅನ್ನು ಬಳಸುತ್ತದೆ](/learn/updating-objects-in-state#write-concise-update-logic-with-immer).

<Sandpack>

```js
import {useImmer} from 'use-immer';
import {initialTravelPlan} from './places.js';

export default function TravelPlan() {
  const [plan, updatePlan] = useImmer(initialTravelPlan);

  function handleComplete(parentId, childId) {
    updatePlan((draft) => {
      // Remove from the parent place's child IDs.
      const parent = draft[parentId];
      parent.childIds = parent.childIds.filter((id) => id !== childId);

      // Forget this place and all its subtree.
      deleteAllChildren(childId);
      function deleteAllChildren(id) {
        const place = draft[id];
        place.childIds.forEach(deleteAllChildren);
        delete draft[id];
      }
    });
  }

  const root = plan[0];
  const planetIds = root.childIds;
  return (
    <>
      <h2>Places to visit</h2>
      <ol>
        {planetIds.map((id) => (
          <PlaceTree
            key={id}
            id={id}
            parentId={0}
            placesById={plan}
            onComplete={handleComplete}
          />
        ))}
      </ol>
    </>
  );
}

function PlaceTree({id, parentId, placesById, onComplete}) {
  const place = placesById[id];
  const childIds = place.childIds;
  return (
    <li>
      {place.title}
      <button
        onClick={() => {
          onComplete(parentId, id);
        }}>
        Complete
      </button>
      {childIds.length > 0 && (
        <ol>
          {childIds.map((childId) => (
            <PlaceTree
              key={childId}
              id={childId}
              parentId={id}
              placesById={placesById}
              onComplete={onComplete}
            />
          ))}
        </ol>
      )}
    </li>
  );
}
```

```js src/places.js
export const initialTravelPlan = {
  0: {
    id: 0,
    title: '(Root)',
    childIds: [1, 42, 46],
  },
  1: {
    id: 1,
    title: 'Earth',
    childIds: [2, 10, 19, 26, 34],
  },
  2: {
    id: 2,
    title: 'Africa',
    childIds: [3, 4, 5, 6, 7, 8, 9],
  },
  3: {
    id: 3,
    title: 'Botswana',
    childIds: [],
  },
  4: {
    id: 4,
    title: 'Egypt',
    childIds: [],
  },
  5: {
    id: 5,
    title: 'Kenya',
    childIds: [],
  },
  6: {
    id: 6,
    title: 'Madagascar',
    childIds: [],
  },
  7: {
    id: 7,
    title: 'Morocco',
    childIds: [],
  },
  8: {
    id: 8,
    title: 'Nigeria',
    childIds: [],
  },
  9: {
    id: 9,
    title: 'South Africa',
    childIds: [],
  },
  10: {
    id: 10,
    title: 'Americas',
    childIds: [11, 12, 13, 14, 15, 16, 17, 18],
  },
  11: {
    id: 11,
    title: 'Argentina',
    childIds: [],
  },
  12: {
    id: 12,
    title: 'Brazil',
    childIds: [],
  },
  13: {
    id: 13,
    title: 'Barbados',
    childIds: [],
  },
  14: {
    id: 14,
    title: 'Canada',
    childIds: [],
  },
  15: {
    id: 15,
    title: 'Jamaica',
    childIds: [],
  },
  16: {
    id: 16,
    title: 'Mexico',
    childIds: [],
  },
  17: {
    id: 17,
    title: 'Trinidad and Tobago',
    childIds: [],
  },
  18: {
    id: 18,
    title: 'Venezuela',
    childIds: [],
  },
  19: {
    id: 19,
    title: 'Asia',
    childIds: [20, 21, 22, 23, 24, 25],
  },
  20: {
    id: 20,
    title: 'China',
    childIds: [],
  },
  21: {
    id: 21,
    title: 'India',
    childIds: [],
  },
  22: {
    id: 22,
    title: 'Singapore',
    childIds: [],
  },
  23: {
    id: 23,
    title: 'South Korea',
    childIds: [],
  },
  24: {
    id: 24,
    title: 'Thailand',
    childIds: [],
  },
  25: {
    id: 25,
    title: 'Vietnam',
    childIds: [],
  },
  26: {
    id: 26,
    title: 'Europe',
    childIds: [27, 28, 29, 30, 31, 32, 33],
  },
  27: {
    id: 27,
    title: 'Croatia',
    childIds: [],
  },
  28: {
    id: 28,
    title: 'France',
    childIds: [],
  },
  29: {
    id: 29,
    title: 'Germany',
    childIds: [],
  },
  30: {
    id: 30,
    title: 'Italy',
    childIds: [],
  },
  31: {
    id: 31,
    title: 'Portugal',
    childIds: [],
  },
  32: {
    id: 32,
    title: 'Spain',
    childIds: [],
  },
  33: {
    id: 33,
    title: 'Turkey',
    childIds: [],
  },
  34: {
    id: 34,
    title: 'Oceania',
    childIds: [35, 36, 37, 38, 39, 40, , 41],
  },
  35: {
    id: 35,
    title: 'Australia',
    childIds: [],
  },
  36: {
    id: 36,
    title: 'Bora Bora (French Polynesia)',
    childIds: [],
  },
  37: {
    id: 37,
    title: 'Easter Island (Chile)',
    childIds: [],
  },
  38: {
    id: 38,
    title: 'Fiji',
    childIds: [],
  },
  39: {
    id: 39,
    title: 'Hawaii (the USA)',
    childIds: [],
  },
  40: {
    id: 40,
    title: 'New Zealand',
    childIds: [],
  },
  41: {
    id: 41,
    title: 'Vanuatu',
    childIds: [],
  },
  42: {
    id: 42,
    title: 'Moon',
    childIds: [43, 44, 45],
  },
  43: {
    id: 43,
    title: 'Rheita',
    childIds: [],
  },
  44: {
    id: 44,
    title: 'Piccolomini',
    childIds: [],
  },
  45: {
    id: 45,
    title: 'Tycho',
    childIds: [],
  },
  46: {
    id: 46,
    title: 'Mars',
    childIds: [47, 48],
  },
  47: {
    id: 47,
    title: 'Corn Town',
    childIds: [],
  },
  48: {
    id: 48,
    title: 'Green Hill',
    childIds: [],
  },
};
```

```css
button {
  margin: 10px;
}
```

```json package.json
{
  "dependencies": {
    "immer": "1.7.3",
    "react": "latest",
    "react-dom": "latest",
    "react-scripts": "latest",
    "use-immer": "0.5.1"
  },
  "scripts": {
    "start": "react-scripts start",
    "build": "react-scripts build",
    "test": "react-scripts test --env=jsdom",
    "eject": "react-scripts eject"
  }
}
```

</Sandpack>

</DeepDive>

ಕೆಲವೊಮ್ಮೆ, ನೀವು ನೆಸ್ಟೆಡ್ ಸ್ಟೇಟ್ ಅನ್ನು ಮಗುವಿನ ಕೊಂಪೊನೆಂಟಗಳಿಗೆ ಚಲಿಸುವ ಮೂಲಕ ಸ್ಟೇಟ್ ಗೂಡುಕಟ್ಟುವಿಕೆಯನ್ನು ಕಡಿಮೆ ಮಾಡಬಹುದು. ಐಟಂ ಅನ್ನು ಸುಳಿದಾಡುವಂತೆಯೇ ಸಂಗ್ರಹಿಸುವ ಅಗತ್ಯವಿಲ್ಲದ ಅಲ್ಪಕಾಲಿಕ UI ಸ್ಥಿತಿಗೆ ಇದು ಉತ್ತಮವಾಗಿ ಕಾರ್ಯನಿರ್ವಹಿಸುತ್ತದೆ.

<Recap>

- ಎರಡು ಸ್ಟೇಟ್ ವೇರಿಯಬಲ್‌ಗಳು ಯಾವಾಗಲೂ ಒಟ್ಟಿಗೆ ಅಪ್‌ಡೇಟ್ ಆಗಿದ್ದರೆ, ಅವುಗಳನ್ನು ಒಂದಾಗಿ ವಿಲೀನಗೊಳಿಸುವುದನ್ನು ಪರಿಗಣಿಸಿ.
- "ಅಸಾಧ್ಯ" ಸ್ಟೇಟ್ಗಳನ್ನು ರಚಿಸುವುದನ್ನು ತಪ್ಪಿಸಲು ನಿಮ್ಮ ಸ್ಟೇಟ್ ಅಸ್ಥಿರಗಳನ್ನು ಎಚ್ಚರಿಕೆಯಿಂದ ಆರಿಸಿ.
- ನಿಮ್ಮ ಸ್ಟೇಟ್ ನವೀಕರಿಸುವಾಗ ನೀವು ತಪ್ಪು ಮಾಡುವ ಸಾಧ್ಯತೆಗಳನ್ನು ಕಡಿಮೆ ಮಾಡುವ ರೀತಿಯಲ್ಲಿ ರಚನೆ ಮಾಡಿ.
- ಅನಗತ್ಯ ಮತ್ತು ನಕಲು ಸ್ಟೇಟ್ ತಪ್ಪಿಸಿ ಇದರಿಂದ ನೀವು ಅದನ್ನು ಸಿಂಕ್‌ನಲ್ಲಿ ಇರಿಸಿಕೊಳ್ಳುವ ಅಗತ್ಯವಿಲ್ಲ.
- ನೀವು ನಿರ್ದಿಷ್ಟವಾಗಿ ಅಪ್‌ಡೇಟ್‌ಗಳನ್ನು ತಡೆಯಲು ಬಯಸದ ಹೊರತು ಪ್ರಾಪ್ಸ್ ಅನ್ನು ಸ್ಟೇಟಗೆ ಹಾಕಬೇಡಿ.
- ಆಯ್ಕೆಯಂತಹ UI ಮಾದರಿಗಳಿಗಾಗಿ, ಆಬ್ಜೆಕ್ಟ್ ಬದಲಿಗೆ ID ಅಥವಾ ಸೂಚಿಯನ್ನು ಸ್ಥಿತಿಯಲ್ಲಿ ಇರಿಸಿ.
- ಆಳವಾಗಿ ನೆಸ್ಟೆಡ್ ಸ್ಥಿತಿಯನ್ನು ನವೀಕರಿಸುವುದು ಸಂಕೀರ್ಣವಾಗಿದ್ದರೆ, ಅದನ್ನು ಚಪ್ಪಟೆಗೊಳಿಸಲು ಪ್ರಯತ್ನಿಸಿ.

</Recap>

<Challenges>

#### ನವೀಕರಿಸದ ಕೊಂಪೊನೆಂಟ್ವನ್ನು ಸರಿಪಡಿಸಿ {/* fix-a-component-thats-not-updating */}

ಈ `Clock` ಕೊಂಪೊನೆಂಟ್ ಎರಡು ಪ್ರಾಪಗಳನ್ನು ಪಡೆಯುತ್ತದೆ: `color` ಮತ್ತು `time`. ಆಯ್ಕೆ ಬಾಕ್ಸ್‌ನಲ್ಲಿ ನೀವು ಬೇರೆ ಬಣ್ಣವನ್ನು ಆಯ್ಕೆ ಮಾಡಿದಾಗ, `Clock` ಕೊಂಪೊನೆಂಟ್ ಅದರ ಮೂಲ ಕೊಂಪೊನೆಂಟದಿಂದ ಬೇರೆ `color` ಪ್ರಾಪ್ ಅನ್ನು ಪಡೆಯುತ್ತದೆ. ಆದಾಗ್ಯೂ, ಕೆಲವು ಕಾರಣಗಳಿಗಾಗಿ, ಪ್ರದರ್ಶಿಸಲಾದ ಬಣ್ಣವು ನವೀಕರಿಸುವುದಿಲ್ಲ. ಏಕೆ? ಸಮಸ್ಯೆಯನ್ನು ಸರಿಪಡಿಸಿ.

<Sandpack>

```js src/Clock.js active
import {useState} from 'react';

export default function Clock(props) {
  const [color, setColor] = useState(props.color);
  return <h1 style={{color: color}}>{props.time}</h1>;
}
```

```js src/App.js hidden
import {useState, useEffect} from 'react';
import Clock from './Clock.js';

function useTime() {
  const [time, setTime] = useState(() => new Date());
  useEffect(() => {
    const id = setInterval(() => {
      setTime(new Date());
    }, 1000);
    return () => clearInterval(id);
  }, []);
  return time;
}

export default function App() {
  const time = useTime();
  const [color, setColor] = useState('lightcoral');
  return (
    <div>
      <p>
        Pick a color:{' '}
        <select value={color} onChange={(e) => setColor(e.target.value)}>
          <option value="lightcoral">lightcoral</option>
          <option value="midnightblue">midnightblue</option>
          <option value="rebeccapurple">rebeccapurple</option>
        </select>
      </p>
      <Clock color={color} time={time.toLocaleTimeString()} />
    </div>
  );
}
```

</Sandpack>

<Solution>

ಸಮಸ್ಯೆ ಏನೆಂದರೆ, ಈ ಕೊಂಪೊನೆಂಟ್ `color` ಸ್ಟೇಟ್ `color` ಪ್ರಾಪ್‌ನ ಆರಂಭಿಕ ಮೌಲ್ಯದೊಂದಿಗೆ ಆರಂಭಿಸಿದೆ. ಆದರೆ `color` ಪ್ರಾಪ್ ಬದಲಾದಾಗ, ಇದು ಸ್ಟೇಟ್ ವೇರಿಯಬಲ್ ಮೇಲೆ ಪರಿಣಾಮ ಬೀರುವುದಿಲ್ಲ! ಆದ್ದರಿಂದ ಅವರು ಸಿಂಕ್ನಿಂದ ಹೊರಬರುತ್ತಾರೆ. ಈ ಸಮಸ್ಯೆಯನ್ನು ಸರಿಪಡಿಸಲು, ಸ್ಟೇಟ್ ವೇರಿಯೇಬಲ್ ಅನ್ನು ಸಂಪೂರ್ಣವಾಗಿ ತೆಗೆದುಹಾಕಿ ಮತ್ತು ನೇರವಾಗಿ `color` ಪ್ರಾಪ್ ಅನ್ನು ಬಳಸಿ.

<Sandpack>

```js src/Clock.js active
import {useState} from 'react';

export default function Clock(props) {
  return <h1 style={{color: props.color}}>{props.time}</h1>;
}
```

```js src/App.js hidden
import {useState, useEffect} from 'react';
import Clock from './Clock.js';

function useTime() {
  const [time, setTime] = useState(() => new Date());
  useEffect(() => {
    const id = setInterval(() => {
      setTime(new Date());
    }, 1000);
    return () => clearInterval(id);
  }, []);
  return time;
}

export default function App() {
  const time = useTime();
  const [color, setColor] = useState('lightcoral');
  return (
    <div>
      <p>
        Pick a color:{' '}
        <select value={color} onChange={(e) => setColor(e.target.value)}>
          <option value="lightcoral">lightcoral</option>
          <option value="midnightblue">midnightblue</option>
          <option value="rebeccapurple">rebeccapurple</option>
        </select>
      </p>
      <Clock color={color} time={time.toLocaleTimeString()} />
    </div>
  );
}
```

</Sandpack>

ಅಥವಾ, ಡಿಸ್ಟ್ರಕ್ಚರಿಂಗ್ ಸಿಂಟ್ಯಾಕ್ಸ್ ಬಳಸಿ:

<Sandpack>

```js src/Clock.js active
import {useState} from 'react';

export default function Clock({color, time}) {
  return <h1 style={{color: color}}>{time}</h1>;
}
```

```js src/App.js hidden
import {useState, useEffect} from 'react';
import Clock from './Clock.js';

function useTime() {
  const [time, setTime] = useState(() => new Date());
  useEffect(() => {
    const id = setInterval(() => {
      setTime(new Date());
    }, 1000);
    return () => clearInterval(id);
  }, []);
  return time;
}

export default function App() {
  const time = useTime();
  const [color, setColor] = useState('lightcoral');
  return (
    <div>
      <p>
        Pick a color:{' '}
        <select value={color} onChange={(e) => setColor(e.target.value)}>
          <option value="lightcoral">lightcoral</option>
          <option value="midnightblue">midnightblue</option>
          <option value="rebeccapurple">rebeccapurple</option>
        </select>
      </p>
      <Clock color={color} time={time.toLocaleTimeString()} />
    </div>
  );
}
```

</Sandpack>

</Solution>

#### ಮುರಿದ ಪ್ಯಾಕಿಂಗ್ ಲಿಸ್ಟ್ ಸರಿಪಡಿಸಿ {/* fix-a-broken-packing-list */}

ಈ ಪ್ಯಾಕಿಂಗ್ ಲಿಸ್ಟ್ ಅಡಿಟಿಪ್ಪಣಿಯನ್ನು ಹೊಂದಿದ್ದು ಅದು ಎಷ್ಟು ಐಟಂಗಳನ್ನು ಪ್ಯಾಕ್ ಮಾಡಲಾಗಿದೆ ಮತ್ತು ಒಟ್ಟಾರೆಯಾಗಿ ಎಷ್ಟು ಐಟಂಗಳಿವೆ ಎಂಬುದನ್ನು ತೋರಿಸುತ್ತದೆ. ಇದು ಮೊದಲಿಗೆ ಕೆಲಸ ಮಾಡುತ್ತದೆ ಎಂದು ತೋರುತ್ತದೆ, ಆದರೆ ಇದು ದೋಷಯುಕ್ತವಾಗಿದೆ. ಉದಾಹರಣೆಗೆ, ನೀವು ಐಟಂ ಅನ್ನು ಪ್ಯಾಕ್ ಮಾಡಲಾಗಿದೆ ಎಂದು ಗುರುತಿಸಿ ನಂತರ ಅದನ್ನು ಅಳಿಸಿದರೆ, ಕೌಂಟರ್ ಅನ್ನು ಸರಿಯಾಗಿ ನವೀಕರಿಸಲಾಗುವುದಿಲ್ಲ. ಕೌಂಟರ್ ಅನ್ನು ಸರಿಪಡಿಸಿ ಇದರಿಂದ ಅದು ಯಾವಾಗಲೂ ಸರಿಯಾಗಿ ಕಾರ್ಯನಿರ್ವಹಿಸುತ್ತದೆ.

<Hint>

ಈ ಉದಾಹರಣೆಯಲ್ಲಿ ಯಾವುದೇ ಸ್ಟೇಟ್ ಅನಗತ್ಯವಾಗಿದೆಯೇ?

</Hint>

<Sandpack>

```js src/App.js
import {useState} from 'react';
import AddItem from './AddItem.js';
import PackingList from './PackingList.js';

let nextId = 3;
const initialItems = [
  {id: 0, title: 'Warm socks', packed: true},
  {id: 1, title: 'Travel journal', packed: false},
  {id: 2, title: 'Watercolors', packed: false},
];

export default function TravelPlan() {
  const [items, setItems] = useState(initialItems);
  const [total, setTotal] = useState(3);
  const [packed, setPacked] = useState(1);

  function handleAddItem(title) {
    setTotal(total + 1);
    setItems([
      ...items,
      {
        id: nextId++,
        title: title,
        packed: false,
      },
    ]);
  }

  function handleChangeItem(nextItem) {
    if (nextItem.packed) {
      setPacked(packed + 1);
    } else {
      setPacked(packed - 1);
    }
    setItems(
      items.map((item) => {
        if (item.id === nextItem.id) {
          return nextItem;
        } else {
          return item;
        }
      })
    );
  }

  function handleDeleteItem(itemId) {
    setTotal(total - 1);
    setItems(items.filter((item) => item.id !== itemId));
  }

  return (
    <>
      <AddItem onAddItem={handleAddItem} />
      <PackingList
        items={items}
        onChangeItem={handleChangeItem}
        onDeleteItem={handleDeleteItem}
      />
      <hr />
      <b>
        {packed} out of {total} packed!
      </b>
    </>
  );
}
```

```js src/AddItem.js hidden
import {useState} from 'react';

export default function AddItem({onAddItem}) {
  const [title, setTitle] = useState('');
  return (
    <>
      <input
        placeholder="Add item"
        value={title}
        onChange={(e) => setTitle(e.target.value)}
      />
      <button
        onClick={() => {
          setTitle('');
          onAddItem(title);
        }}>
        Add
      </button>
    </>
  );
}
```

```js src/PackingList.js hidden
import {useState} from 'react';

export default function PackingList({items, onChangeItem, onDeleteItem}) {
  return (
    <ul>
      {items.map((item) => (
        <li key={item.id}>
          <label>
            <input
              type="checkbox"
              checked={item.packed}
              onChange={(e) => {
                onChangeItem({
                  ...item,
                  packed: e.target.checked,
                });
              }}
            />{' '}
            {item.title}
          </label>
          <button onClick={() => onDeleteItem(item.id)}>Delete</button>
        </li>
      ))}
    </ul>
  );
}
```

```css
button {
  margin: 5px;
}
li {
  list-style-type: none;
}
ul,
li {
  margin: 0;
  padding: 0;
}
```

</Sandpack>

<Solution>

`total` ಮತ್ತು `packed` ಮಾಡಿದ ಕೌಂಟರ್‌ಗಳನ್ನು ಸರಿಯಾಗಿ ನವೀಕರಿಸಲು ನೀವು ಪ್ರತಿ ಈವೆಂಟ್ ಹ್ಯಾಂಡ್ಲರ್ ಅನ್ನು ಎಚ್ಚರಿಕೆಯಿಂದ ಬದಲಾಯಿಸಬಹುದಾದರೂ, ಮೂಲ ಸಮಸ್ಯೆಯೆಂದರೆ ಈ ಸ್ಟೇಟ್ ವೇರಿಯಬಲ್‌ಗಳು ಅಸ್ತಿತ್ವದಲ್ಲಿವೆ. ಅವುಗಳು ಅನಗತ್ಯವಾಗಿರುತ್ತವೆ ಏಕೆಂದರೆ ನೀವು ಯಾವಾಗಲೂ `items` ಅರೇಯಿಂದಲೇ ಐಟಂಗಳ ಸಂಖ್ಯೆಯನ್ನು (ಪ್ಯಾಕ್ ಮಾಡಿದ ಅಥವಾ ಒಟ್ಟು) ಲೆಕ್ಕಾಚಾರ ಮಾಡಬಹುದು. ದೋಷವನ್ನು ಸರಿಪಡಿಸಲು ಅನಗತ್ಯ ಸ್ಥಿತಿಯನ್ನು ತೆಗೆದುಹಾಕಿ:

<Sandpack>

```js src/App.js
import {useState} from 'react';
import AddItem from './AddItem.js';
import PackingList from './PackingList.js';

let nextId = 3;
const initialItems = [
  {id: 0, title: 'Warm socks', packed: true},
  {id: 1, title: 'Travel journal', packed: false},
  {id: 2, title: 'Watercolors', packed: false},
];

export default function TravelPlan() {
  const [items, setItems] = useState(initialItems);

  const total = items.length;
  const packed = items.filter((item) => item.packed).length;

  function handleAddItem(title) {
    setItems([
      ...items,
      {
        id: nextId++,
        title: title,
        packed: false,
      },
    ]);
  }

  function handleChangeItem(nextItem) {
    setItems(
      items.map((item) => {
        if (item.id === nextItem.id) {
          return nextItem;
        } else {
          return item;
        }
      })
    );
  }

  function handleDeleteItem(itemId) {
    setItems(items.filter((item) => item.id !== itemId));
  }

  return (
    <>
      <AddItem onAddItem={handleAddItem} />
      <PackingList
        items={items}
        onChangeItem={handleChangeItem}
        onDeleteItem={handleDeleteItem}
      />
      <hr />
      <b>
        {packed} out of {total} packed!
      </b>
    </>
  );
}
```

```js src/AddItem.js hidden
import {useState} from 'react';

export default function AddItem({onAddItem}) {
  const [title, setTitle] = useState('');
  return (
    <>
      <input
        placeholder="Add item"
        value={title}
        onChange={(e) => setTitle(e.target.value)}
      />
      <button
        onClick={() => {
          setTitle('');
          onAddItem(title);
        }}>
        Add
      </button>
    </>
  );
}
```

```js src/PackingList.js hidden
import {useState} from 'react';

export default function PackingList({items, onChangeItem, onDeleteItem}) {
  return (
    <ul>
      {items.map((item) => (
        <li key={item.id}>
          <label>
            <input
              type="checkbox"
              checked={item.packed}
              onChange={(e) => {
                onChangeItem({
                  ...item,
                  packed: e.target.checked,
                });
              }}
            />{' '}
            {item.title}
          </label>
          <button onClick={() => onDeleteItem(item.id)}>Delete</button>
        </li>
      ))}
    </ul>
  );
}
```

```css
button {
  margin: 5px;
}
li {
  list-style-type: none;
}
ul,
li {
  margin: 0;
  padding: 0;
}
```

</Sandpack>

ಈ ಬದಲಾವಣೆಯ ನಂತರ ಈವೆಂಟ್ ಹ್ಯಾಂಡ್ಲರ್‌ಗಳು ಕೇವಲ `setItems` ಎಂದು ಕರೆಯಲು ಹೇಗೆ ಕಾಳಜಿ ವಹಿಸುತ್ತಾರೆ ಎಂಬುದನ್ನು ಗಮನಿಸಿ. ಐಟಂ ಎಣಿಕೆಗಳನ್ನು ಈಗ `items' ಮುಂದಿನ ರೆಂಡರ್ ಸಮಯದಲ್ಲಿ ಲೆಕ್ಕಹಾಕಲಾಗುತ್ತದೆ, ಆದ್ದರಿಂದ ಅವು ಯಾವಾಗಲೂ ನವೀಕೃತವಾಗಿರುತ್ತವೆ.

</Solution>

#### ಕಣ್ಮರೆಯಾಗುತ್ತಿರುವ ಆಯ್ಕೆಯನ್ನು ಸರಿಪಡಿಸಿ {/* fix-the-disappearing-selection */}

ಸ್ಟೇಟದಲ್ಲಿ `letters` ಲಿಸ್ಟ್ ಇದೆ. ನೀವು ನಿರ್ದಿಷ್ಟ ಅಕ್ಷರವನ್ನು ಸುಳಿದಾಡಿದಾಗ ಅಥವಾ ಕೇಂದ್ರೀಕರಿಸಿದಾಗ, ಅದು ಹೈಲೈಟ್ ಆಗುತ್ತದೆ. ಪ್ರಸ್ತುತ ಹೈಲೈಟ್ ಮಾಡಲಾದ ಅಕ್ಷರವನ್ನು `highlightedLetter` ಸ್ಟೇಟ್ ವೇರಿಯೇಬಲ್‌ನಲ್ಲಿ ಸಂಗ್ರಹಿಸಲಾಗಿದೆ. ನೀವು ಪ್ರತ್ಯೇಕ ಅಕ್ಷರಗಳನ್ನು "ಸ್ಟಾರ್" ಮತ್ತು "ಅನ್‌ಸ್ಟಾರ್" ಮಾಡಬಹುದು, ಇದು ಸ್ಟೇಟದಲ್ಲಿನ `letters` ಅರೇಯನ್ನು ನವೀಕರಿಸುತ್ತದೆ.

ಈ ಕೋಡ್ ಕಾರ್ಯನಿರ್ವಹಿಸುತ್ತದೆ, ಆದರೆ ಸಣ್ಣ UI ಗ್ಲಿಚ್ ಇದೆ. ನೀವು "ಸ್ಟಾರ್" ಅಥವಾ "ಅನ್‌ಸ್ಟಾರ್" ಅನ್ನು ಒತ್ತಿದಾಗ, ಹೈಲೈಟ್ ಮಾಡುವಿಕೆಯು ಒಂದು ಕ್ಷಣ ಕಣ್ಮರೆಯಾಗುತ್ತದೆ. ಆದಾಗ್ಯೂ, ನೀವು ನಿಮ್ಮ ಪಾಯಿಂಟರ್ ಅನ್ನು ಸರಿಸಿದಾಗ ಅಥವಾ ಕೀಬೋರ್ಡ್‌ನೊಂದಿಗೆ ಮತ್ತೊಂದು ಅಕ್ಷರಕ್ಕೆ ಬದಲಾಯಿಸಿದ ತಕ್ಷಣ ಅದು ಮತ್ತೆ ಕಾಣಿಸಿಕೊಳ್ಳುತ್ತದೆ. ಇದು ಏಕೆ ನಡೆಯುತ್ತಿದೆ? ಬಟನ್ ಕ್ಲಿಕ್ ಮಾಡಿದ ನಂತರ ಹೈಲೈಟ್ ಮಾಡುವಿಕೆಯು ಕಣ್ಮರೆಯಾಗದಂತೆ ಅದನ್ನು ಸರಿಪಡಿಸಿ.

<Sandpack>

```js src/App.js
import {useState} from 'react';
import {initialLetters} from './data.js';
import Letter from './Letter.js';

export default function MailClient() {
  const [letters, setLetters] = useState(initialLetters);
  const [highlightedLetter, setHighlightedLetter] = useState(null);

  function handleHover(letter) {
    setHighlightedLetter(letter);
  }

  function handleStar(starred) {
    setLetters(
      letters.map((letter) => {
        if (letter.id === starred.id) {
          return {
            ...letter,
            isStarred: !letter.isStarred,
          };
        } else {
          return letter;
        }
      })
    );
  }

  return (
    <>
      <h2>Inbox</h2>
      <ul>
        {letters.map((letter) => (
          <Letter
            key={letter.id}
            letter={letter}
            isHighlighted={letter === highlightedLetter}
            onHover={handleHover}
            onToggleStar={handleStar}
          />
        ))}
      </ul>
    </>
  );
}
```

```js src/Letter.js
export default function Letter({letter, isHighlighted, onHover, onToggleStar}) {
  return (
    <li
      className={isHighlighted ? 'highlighted' : ''}
      onFocus={() => {
        onHover(letter);
      }}
      onPointerMove={() => {
        onHover(letter);
      }}>
      <button
        onClick={() => {
          onToggleStar(letter);
        }}>
        {letter.isStarred ? 'Unstar' : 'Star'}
      </button>
      {letter.subject}
    </li>
  );
}
```

```js src/data.js
export const initialLetters = [
  {
    id: 0,
    subject: 'Ready for adventure?',
    isStarred: true,
  },
  {
    id: 1,
    subject: 'Time to check in!',
    isStarred: false,
  },
  {
    id: 2,
    subject: 'Festival Begins in Just SEVEN Days!',
    isStarred: false,
  },
];
```

```css
button {
  margin: 5px;
}
li {
  border-radius: 5px;
}
.highlighted {
  background: #d2eaff;
}
```

</Sandpack>

<Solution>

ಸಮಸ್ಯೆಯೆಂದರೆ ನೀವು ಅಕ್ಷರದ ಆಬ್ಜೆಕ್ಟವನ್ನು `highlightedLetter` ನಲ್ಲಿ ಹಿಡಿದಿರುವಿರಿ. ಆದರೆ ನೀವು ಅದೇ ಮಾಹಿತಿಯನ್ನು `letters` ಅರೇಯಲ್ಲಿ ಹಿಡಿದಿರುವಿರಿ. ಆದ್ದರಿಂದ ನಿಮ್ಮ ಸ್ಟೇಟ್ ನಕಲು ಹೊಂದಿದೆ! ಬಟನ್ ಕ್ಲಿಕ್ ಮಾಡಿದ ನಂತರ ನೀವು `letters` ಅರೇ ಅನ್ನು ನವೀಕರಿಸಿದಾಗ, ನೀವು ಹೊಸ ಅಕ್ಷರದ ಆಬ್ಜೆಕ್ಟವನ್ನು ರಚಿಸುತ್ತೀರಿ ಅದು `highlightedLetter` ಗಿಂತ ಭಿನ್ನವಾಗಿರುತ್ತದೆ. ಇದಕ್ಕಾಗಿಯೇ `highlightedLetter === letter` ಚೆಕ್ `false` ಆಗುತ್ತದೆ ಮತ್ತು ಹೈಲೈಟ್ ಕಣ್ಮರೆಯಾಗುತ್ತದೆ. ಪಾಯಿಂಟರ್ ಚಲಿಸಿದಾಗ ನೀವು ಮುಂದಿನ ಬಾರಿ `setHighlightedLetter` ಎಂದು ಕರೆ ಮಾಡಿದಾಗ ಅದು ಮತ್ತೆ ಕಾಣಿಸಿಕೊಳ್ಳುತ್ತದೆ.

ಸಮಸ್ಯೆಯನ್ನು ಪರಿಹರಿಸಲು, ಸ್ಟೇಟದಿಂದ ನಕಲು ತೆಗೆದುಹಾಕಿ. _ಅಕ್ಷರವನ್ನೇ_ ಎರಡು ಸ್ಥಳಗಳಲ್ಲಿ ಸಂಗ್ರಹಿಸುವ ಬದಲು, `highlightedId` ಅನ್ನು ಸಂಗ್ರಹಿಸಿ. ನಂತರ ನೀವು ಪ್ರತಿ ಅಕ್ಷರಕ್ಕೆ `isHighlighted` ಅನ್ನು `letter.id === highlightedId` ನೊಂದಿಗೆ ಪರಿಶೀಲಿಸಬಹುದು, ಇದು ಕೊನೆಯ ರೆಂಡರ್‌ನಿಂದ `letter` ಆಬ್ಜೆಕ್ಟ್ ಬದಲಾಗಿದ್ದರೂ ಸಹ ಕಾರ್ಯನಿರ್ವಹಿಸುತ್ತದೆ.

<Sandpack>

```js src/App.js
import {useState} from 'react';
import {initialLetters} from './data.js';
import Letter from './Letter.js';

export default function MailClient() {
  const [letters, setLetters] = useState(initialLetters);
  const [highlightedId, setHighlightedId] = useState(null);

  function handleHover(letterId) {
    setHighlightedId(letterId);
  }

  function handleStar(starredId) {
    setLetters(
      letters.map((letter) => {
        if (letter.id === starredId) {
          return {
            ...letter,
            isStarred: !letter.isStarred,
          };
        } else {
          return letter;
        }
      })
    );
  }

  return (
    <>
      <h2>Inbox</h2>
      <ul>
        {letters.map((letter) => (
          <Letter
            key={letter.id}
            letter={letter}
            isHighlighted={letter.id === highlightedId}
            onHover={handleHover}
            onToggleStar={handleStar}
          />
        ))}
      </ul>
    </>
  );
}
```

```js src/Letter.js
export default function Letter({letter, isHighlighted, onHover, onToggleStar}) {
  return (
    <li
      className={isHighlighted ? 'highlighted' : ''}
      onFocus={() => {
        onHover(letter.id);
      }}
      onPointerMove={() => {
        onHover(letter.id);
      }}>
      <button
        onClick={() => {
          onToggleStar(letter.id);
        }}>
        {letter.isStarred ? 'Unstar' : 'Star'}
      </button>
      {letter.subject}
    </li>
  );
}
```

```js src/data.js
export const initialLetters = [
  {
    id: 0,
    subject: 'Ready for adventure?',
    isStarred: true,
  },
  {
    id: 1,
    subject: 'Time to check in!',
    isStarred: false,
  },
  {
    id: 2,
    subject: 'Festival Begins in Just SEVEN Days!',
    isStarred: false,
  },
];
```

```css
button {
  margin: 5px;
}
li {
  border-radius: 5px;
}
.highlighted {
  background: #d2eaff;
}
```

</Sandpack>

</Solution>

#### ಬಹು ಆಯ್ಕೆಯನ್ನು ಕಾರ್ಯಗತಗೊಳಿಸಿ {/* implement-multiple-selection */}

ಈ ಉದಾಹರಣೆಯಲ್ಲಿ, ಪ್ರತಿ `Letter` ಒಂದು `isSelected` ಪ್ರಾಪ್ ಮತ್ತು `onToggle` ಹ್ಯಾಂಡ್ಲರ್ ಅನ್ನು ಹೊಂದಿದ್ದು ಅದನ್ನು ಆಯ್ಕೆ ಮಾಡಿದೆ ಎಂದು ಗುರುತಿಸುತ್ತದೆ. ಇದು ಕಾರ್ಯನಿರ್ವಹಿಸುತ್ತದೆ, ಆದರೆ ಸ್ಟೇಟ್ `selectedId` (`null` ಅಥವಾ ಐಡಿ) ಎಂದು ಸಂಗ್ರಹಿಸಲಾಗುತ್ತದೆ, ಆದ್ದರಿಂದ ಯಾವುದೇ ಸಮಯದಲ್ಲಿ ಒಂದು ಅಕ್ಷರವನ್ನು ಮಾತ್ರ ಆಯ್ಕೆ ಮಾಡಬಹುದು.

ಬಹು ಆಯ್ಕೆಯನ್ನು ಬೆಂಬಲಿಸಲು ಸ್ಟೇಟ್ ರಚನೆಯನ್ನು ಬದಲಾಯಿಸಿ. (ನೀವು ಅದನ್ನು ಹೇಗೆ ರಚಿಸುತ್ತೀರಿ? ಕೋಡ್ ಬರೆಯುವ ಮೊದಲು ಇದರ ಬಗ್ಗೆ ಯೋಚಿಸಿ.) ಪ್ರತಿಯೊಂದು ಚೆಕ್‌ಬಾಕ್ಸ್ ಇತರರಿಂದ ಸ್ವತಂತ್ರವಾಗಿರಬೇಕು. ಆಯ್ದ ಅಕ್ಷರವನ್ನು ಕ್ಲಿಕ್ ಮಾಡುವುದರಿಂದ ಅದನ್ನು ಗುರುತಿಸಬೇಡಿ. ಅಂತಿಮವಾಗಿ, ಅಡಿಟಿಪ್ಪಣಿ ಆಯ್ಕೆ ಮಾಡಿದ ಐಟಂಗಳ ಸರಿಯಾದ ಸಂಖ್ಯೆಯನ್ನು ತೋರಿಸಬೇಕು.

<Hint>

ಒಂದೇ ಆಯ್ಕೆಮಾಡಿದ ID ಬದಲಿಗೆ, ನೀವು ಸ್ಟೇಟದಲ್ಲಿ ಒಂದು ಅರೇಯನ್ನು ಅಥವಾ ಆಯ್ಕೆಮಾಡಿದ ID ಗಳ [ಸೆಟ್](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Set) ಅನ್ನು ಹಿಡಿದಿಟ್ಟುಕೊಳ್ಳಲು ಬಯಸಬಹುದು.

</Hint>

<Sandpack>

```js src/App.js
import {useState} from 'react';
import {letters} from './data.js';
import Letter from './Letter.js';

export default function MailClient() {
  const [selectedId, setSelectedId] = useState(null);

  // TODO: allow multiple selection
  const selectedCount = 1;

  function handleToggle(toggledId) {
    // TODO: allow multiple selection
    setSelectedId(toggledId);
  }

  return (
    <>
      <h2>Inbox</h2>
      <ul>
        {letters.map((letter) => (
          <Letter
            key={letter.id}
            letter={letter}
            isSelected={
              // TODO: allow multiple selection
              letter.id === selectedId
            }
            onToggle={handleToggle}
          />
        ))}
        <hr />
        <p>
          <b>You selected {selectedCount} letters</b>
        </p>
      </ul>
    </>
  );
}
```

```js src/Letter.js
export default function Letter({letter, onToggle, isSelected}) {
  return (
    <li className={isSelected ? 'selected' : ''}>
      <label>
        <input
          type="checkbox"
          checked={isSelected}
          onChange={() => {
            onToggle(letter.id);
          }}
        />
        {letter.subject}
      </label>
    </li>
  );
}
```

```js src/data.js
export const letters = [
  {
    id: 0,
    subject: 'Ready for adventure?',
    isStarred: true,
  },
  {
    id: 1,
    subject: 'Time to check in!',
    isStarred: false,
  },
  {
    id: 2,
    subject: 'Festival Begins in Just SEVEN Days!',
    isStarred: false,
  },
];
```

```css
input {
  margin: 5px;
}
li {
  border-radius: 5px;
}
label {
  width: 100%;
  padding: 5px;
  display: inline-block;
}
.selected {
  background: #d2eaff;
}
```

</Sandpack>

<Solution>

ಒಂದೇ `selectedId` ಬದಲಿಗೆ, `selectedIds`_array_ ಅನ್ನು ಸ್ಟೇಟ್ ಇರಿಸಿಕೊಳ್ಳಿ. ಉದಾಹರಣೆಗೆ, ನೀವು ಮೊದಲ ಮತ್ತು ಕೊನೆಯ ಅಕ್ಷರವನ್ನು ಆರಿಸಿದರೆ, ಅದು `[0, 2]` ಅನ್ನು ಹೊಂದಿರುತ್ತದೆ. ಏನನ್ನೂ ಆಯ್ಕೆ ಮಾಡದಿದ್ದಾಗ, ಅದು ಖಾಲಿ `[]` ಅರೇ ಆಗಿರುತ್ತದೆ:

<Sandpack>

```js src/App.js
import {useState} from 'react';
import {letters} from './data.js';
import Letter from './Letter.js';

export default function MailClient() {
  const [selectedIds, setSelectedIds] = useState([]);

  const selectedCount = selectedIds.length;

  function handleToggle(toggledId) {
    // Was it previously selected?
    if (selectedIds.includes(toggledId)) {
      // Then remove this ID from the array.
      setSelectedIds(selectedIds.filter((id) => id !== toggledId));
    } else {
      // Otherwise, add this ID to the array.
      setSelectedIds([...selectedIds, toggledId]);
    }
  }

  return (
    <>
      <h2>Inbox</h2>
      <ul>
        {letters.map((letter) => (
          <Letter
            key={letter.id}
            letter={letter}
            isSelected={selectedIds.includes(letter.id)}
            onToggle={handleToggle}
          />
        ))}
        <hr />
        <p>
          <b>You selected {selectedCount} letters</b>
        </p>
      </ul>
    </>
  );
}
```

```js src/Letter.js
export default function Letter({letter, onToggle, isSelected}) {
  return (
    <li className={isSelected ? 'selected' : ''}>
      <label>
        <input
          type="checkbox"
          checked={isSelected}
          onChange={() => {
            onToggle(letter.id);
          }}
        />
        {letter.subject}
      </label>
    </li>
  );
}
```

```js src/data.js
export const letters = [
  {
    id: 0,
    subject: 'Ready for adventure?',
    isStarred: true,
  },
  {
    id: 1,
    subject: 'Time to check in!',
    isStarred: false,
  },
  {
    id: 2,
    subject: 'Festival Begins in Just SEVEN Days!',
    isStarred: false,
  },
];
```

```css
input {
  margin: 5px;
}
li {
  border-radius: 5px;
}
label {
  width: 100%;
  padding: 5px;
  display: inline-block;
}
.selected {
  background: #d2eaff;
}
```

</Sandpack>

ಅರೇಯನ್ನು ಬಳಸುವುದರ ಒಂದು ಸಣ್ಣ ತೊಂದರೆಯೆಂದರೆ, ಪ್ರತಿ ಐಟಂಗೆ, ಅದನ್ನು ಆಯ್ಕೆಮಾಡಲಾಗಿದೆಯೇ ಎಂದು ಪರಿಶೀಲಿಸಲು ನೀವು `selectedIds.includes(letter.id)` ಎಂದು ಕರೆಯುತ್ತಿರುವಿರಿ. ಅರೇ ತುಂಬಾ ದೊಡ್ಡದಾಗಿದ್ದರೆ, ಇದು ಕಾರ್ಯಕ್ಷಮತೆಯ ಸಮಸ್ಯೆಯಾಗಬಹುದು ಏಕೆಂದರೆ [`includes()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/includes) ನೊಂದಿಗೆ ಅರೇ ಹುಡುಕಾಟವು ರೇಖಾತ್ಮಕ ಸಮಯವನ್ನು ತೆಗೆದುಕೊಳ್ಳುತ್ತದೆ ಮತ್ತು ನೀವು ಪ್ರತಿಯೊಂದು ಐಟಂಗಾಗಿ ಈ ಹುಡುಕಾಟವನ್ನು ಮಾಡುತ್ತಿರುವಿರಿ.

ಇದನ್ನು ಸರಿಪಡಿಸಲು, ವೇಗವಾದ [`has()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Set/has) ಕಾರ್ಯಾಚರಣೆಯನ್ನು ಒದಗಿಸುವ [ಸೆಟ್](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Set) ಅನ್ನು ನೀವು ಸ್ಥಿತಿಯಲ್ಲಿ ಹಿಡಿದಿಟ್ಟುಕೊಳ್ಳಬಹುದು:

<Sandpack>

```js src/App.js
import {useState} from 'react';
import {letters} from './data.js';
import Letter from './Letter.js';

export default function MailClient() {
  const [selectedIds, setSelectedIds] = useState(new Set());

  const selectedCount = selectedIds.size;

  function handleToggle(toggledId) {
    // Create a copy (to avoid mutation).
    const nextIds = new Set(selectedIds);
    if (nextIds.has(toggledId)) {
      nextIds.delete(toggledId);
    } else {
      nextIds.add(toggledId);
    }
    setSelectedIds(nextIds);
  }

  return (
    <>
      <h2>Inbox</h2>
      <ul>
        {letters.map((letter) => (
          <Letter
            key={letter.id}
            letter={letter}
            isSelected={selectedIds.has(letter.id)}
            onToggle={handleToggle}
          />
        ))}
        <hr />
        <p>
          <b>You selected {selectedCount} letters</b>
        </p>
      </ul>
    </>
  );
}
```

```js src/Letter.js
export default function Letter({letter, onToggle, isSelected}) {
  return (
    <li className={isSelected ? 'selected' : ''}>
      <label>
        <input
          type="checkbox"
          checked={isSelected}
          onChange={() => {
            onToggle(letter.id);
          }}
        />
        {letter.subject}
      </label>
    </li>
  );
}
```

```js src/data.js
export const letters = [
  {
    id: 0,
    subject: 'Ready for adventure?',
    isStarred: true,
  },
  {
    id: 1,
    subject: 'Time to check in!',
    isStarred: false,
  },
  {
    id: 2,
    subject: 'Festival Begins in Just SEVEN Days!',
    isStarred: false,
  },
];
```

```css
input {
  margin: 5px;
}
li {
  border-radius: 5px;
}
label {
  width: 100%;
  padding: 5px;
  display: inline-block;
}
.selected {
  background: #d2eaff;
}
```

</Sandpack>

ಈಗ ಪ್ರತಿಯೊಂದು ಐಟಂ `selectedIds.has(letter.id)` ಚೆಕ್ ಅನ್ನು ಮಾಡುತ್ತದೆ, ಅದು ತುಂಬಾ ವೇಗವಾಗಿರುತ್ತದೆ.

ನೀವು [ಸ್ಟೇಟದಲ್ಲಿ ಆಬ್ಜೆಕ್ಟಗಳನ್ನು ರೂಪಾಂತರಿಸಬಾರದು](/learn/updating-objects-in-state), ಮತ್ತು ಅದು ಸೆಟ್‌ಗಳನ್ನು ಸಹ ಒಳಗೊಂಡಿರುತ್ತದೆ ಎಂಬುದನ್ನು ನೆನಪಿನಲ್ಲಿಡಿ. ಇದಕ್ಕಾಗಿಯೇ `handleToggle` ಫಂಕ್ಷನ್ ಮೊದಲು ಸೆಟ್‌ನ _ಕಾಪಿ_ ಅನ್ನು ರಚಿಸುತ್ತದೆ ಮತ್ತು ನಂತರ ಆ ನಕಲನ್ನು ನವೀಕರಿಸುತ್ತದೆ.

</Solution>

</Challenges>
