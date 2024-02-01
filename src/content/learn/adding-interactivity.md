---
title: Adding Interactivity
---
<Intro>

ಬಳಕೆದಾರರ ಇನ್‌ಪುಟ್‌ಗೆ ಪ್ರತಿಕ್ರಿಯೆಯಾಗಿ ಸ್ಕ್ರೀನ್ ಮೇಲೆ ಕೆಲವು ವಿಷಯಗಳನ್ನು ನವೀಕರಿಸಲಾಗುತ್ತದೆ. ಉದಾಹರಣೆಗೆ, ಇಮೇಜ್ ಗ್ಯಾಲರಿಯನ್ನು ಕ್ಲಿಕ್ ಮಾಡುವುದರಿಂದ ಸಕ್ರಿಯ ಚಿತ್ರವನ್ನು ಬದಲಾಯಿಸುತ್ತದೆ. ರಿಯಾಕ್ಟ್‌ನಲ್ಲಿ, ಕಾಲಾನಂತರದಲ್ಲಿ ಬದಲಾಗುವ ಡೇಟಾವನ್ನು *ಸ್ಟೇಟ್* ಎಂದು ಕರೆಯಲಾಗುತ್ತದೆ. ನೀವು ಯಾವುದೇ ಕೊಂಪೊನೆಂಟಕ್ಕೆ ಸ್ಟೇಟನು ಸೇರಿಸಬಹುದು ಮತ್ತು ಅಗತ್ಯವಿರುವಂತೆ ಅದನ್ನು ನವೀಕರಿಸಬಹುದು.ಈ ಅಧ್ಯಾಯದಲ್ಲಿ, ಸಂವಹನಗಳನ್ನು ನಿರ್ವಹಿಸುವ, ಅವುಗಳ ಸ್ಟೇಟ್ ನವೀಕರಿಸುವ ಮತ್ತು ಕಾಲಾನಂತರದಲ್ಲಿ ವಿಭಿನ್ನ ಔಟ್‌ಪುಟ್ ಅನ್ನು ಪ್ರದರ್ಶಿಸುವ ಕೊಂಪೊನೆಂಟ್ಗಳನ್ನು ಹೇಗೆ ಬರೆಯುವುದು ಎಂಬುದನ್ನು ನೀವು ಕಲಿಯುವಿರಿ.

</Intro>

<YouWillLearn isChapter={true}>

* [ಬಳಕೆದಾರರು ಪ್ರಾರಂಭಿಸಿದ ಈವೆಂಟ್‌ಗಳನ್ನು ಹೇಗೆ ನಿರ್ವಹಿಸುವುದು](/learn/responding-to-events)
* [ಕೊಂಪೊನೆಂಟ್ಗಳನ್ನು ಸ್ಟೇಟ್ದೊಂದಿಗೆ ಮಾಹಿತಿಯನ್ನು "ನೆನಪಿಡೋದೋ" ಹೇಗೆ](/learn/state-a-components-memory)
* [ಹೇಗೆ ರಿಯಾಕ್ಟ್ ಎರಡು ಹಂತಗಳಲ್ಲಿ UI ಅನ್ನು ನವೀಕರಿಸುತ್ತದೆ](/learn/render-and-commit)
* [ನೀವು ಅದನ್ನು ಬದಲಾಯಿಸಿದ ತಕ್ಷಣ ಸ್ಟೇಟ್ ಏಕೆ ನವೀಕರಿಸುವುದಿಲ್ಲ](/learn/state-as-a-snapshot)
* [ಬಹು ಸ್ಟೇಟ್ ನವೀಕರಣಗಳನ್ನು ಸರತಿಯಲ್ಲಿ ಹೇಗೆ ಮಾಡುವುದು](/learn/queueing-a-series-of-state-updates)
* [ಸ್ಥಿತಿಯಲ್ಲಿ ಓಬ್ಜೆಕ್ಟ್ವನ್ನು ಹೇಗೆ ನವೀಕರಿಸುವುದು](/learn/updating-objects-in-state)
* [statealli ಒಂದು ಅರೆಯನ್ನು ನವೀಕರಿಸುವುದು ಹೇಗೆ](/learn/updating-arrays-in-state)

</YouWillLearn>

## ಈವೆಂಟ್ಗಳಿಗೆ ಪ್ರತಿಕ್ರಿಯಿಸುವುದು {/*responding-to-events*/}

ನಿಮ್ಮ JSX ಗೆ *ಈವೆಂಟ್ ಹ್ಯಾಂಡ್ಲರ್‌ಗಳನ್ನು* ಸೇರಿಸಲು ರಿಯಾಕ್ಟ್ ಅನುಮತಿಸುತ್ತದೆ. ಈವೆಂಟ್ ಹ್ಯಾಂಡ್ಲರ್‌ಗಳು ನಿಮ್ಮ ಸ್ವಂತ ಕಾರ್ಯಗಳಾಗಿದ್ದು, ಕ್ಲಿಕ್ ಮಾಡುವುದು, ಸುಳಿದಾಡುವುದು, ಫಾರ್ಮ್ ಇನ್‌ಪುಟ್‌ಗಳ ಮೇಲೆ ಕೇಂದ್ರೀಕರಿಸುವುದು ಮತ್ತು ಮುಂತಾದ ಬಳಕೆದಾರರ ಸಂವಹನಗಳಿಗೆ ಪ್ರತಿಕ್ರಿಯೆಯಾಗಿ ಟ್ರಿಗರ್ ಮಾಡಲಾಗುತ್ತದೆ.

`<button>` ನಂತಹ ಅಂತರ್ನಿರ್ಮಿತ ಕೊಂಪೊನೆಂಟ್ಗಳು `onClick` ನಂತಹ ಅಂತರ್ನಿರ್ಮಿತ ಬ್ರೌಸರ್ ಈವೆಂಟ್‌ಗಳನ್ನು ಮಾತ್ರ ಬೆಂಬಲಿಸುತ್ತವೆ. ಆದಾಗ್ಯೂ, ನೀವು ನಿಮ್ಮ ಸ್ವಂತ ಕೊಂಪೊನೆಂಟ್ಗಳನ್ನು ಸಹ ರಚಿಸಬಹುದು ಮತ್ತು ಅವರ ಈವೆಂಟ್ ಹ್ಯಾಂಡ್ಲರ್ ಪ್ರಾಪ್‌ಗಳಿಗೆ ನೀವು ಇಷ್ಟಪಡುವ ಯಾವುದೇ ಅಪ್ಲಿಕೇಶನ್-ನಿರ್ದಿಷ್ಟ ಹೆಸರುಗಳನ್ನು ನೀಡಬಹುದು.

<Sandpack>

```js
export default function App() {
  return (
    <Toolbar
      onPlayMovie={() => alert('Playing!')}
      onUploadImage={() => alert('Uploading!')}
    />
  );
}

function Toolbar({ onPlayMovie, onUploadImage }) {
  return (
    <div>
      <Button onClick={onPlayMovie}>
        Play Movie
      </Button>
      <Button onClick={onUploadImage}>
        Upload Image
      </Button>
    </div>
  );
}

function Button({ onClick, children }) {
  return (
    <button onClick={onClick}>
      {children}
    </button>
  );
}
```

```css
button { margin-right: 10px; }
```

</Sandpack>

<LearnMore path="/learn/responding-to-events">

Read **[ಈವೆಂಟ್ಗಳಿಗೆ ಪ್ರತಿಕ್ರಿಯಿಸುವುದು](/learn/responding-to-events)** to learn how to add event handlers.

</LearnMore>

## State: a component's memory {/*state-a-components-memory*/}

ಪರಸ್ಪರ ಕ್ರಿಯೆಯ ಪರಿಣಾಮವಾಗಿ ಸ್ಕ್ರೀನ್ ಮೇಲೆ ಏನಿದೆ ಎಂಬುದನ್ನು ಕೊಂಪೊನೆಂಟ್ಗಳು ಆಗಾಗ್ಗೆ ಬದಲಾಯಿಸಬೇಕಾಗುತ್ತದೆ. ಫಾರ್ಮ್‌ನಲ್ಲಿ ಟೈಪ್ ಮಾಡುವುದರಿಂದ ಇನ್‌ಪುಟ್ ಕ್ಷೇತ್ರವನ್ನು ನವೀಕರಿಸಬೇಕು, ಚಿತ್ರದ ಏರಿಳಿಕೆಯಲ್ಲಿ "next" ಕ್ಲಿಕ್ ಮಾಡುವುದರಿಂದ ಯಾವ ಚಿತ್ರವನ್ನು ಪ್ರದರ್ಶಿಸಲಾಗುತ್ತದೆ ಎಂಬುದನ್ನು ಬದಲಾಯಿಸಬೇಕು, "buy" ಕ್ಲಿಕ್ ಮಾಡುವುದರಿಂದ ಶಾಪಿಂಗ್ ಕಾರ್ಟ್‌ನಲ್ಲಿ ಉತ್ಪನ್ನವನ್ನು ಇರಿಸಲಾಗುತ್ತದೆ. ಕೊಂಪೊನೆಂಟ್ಗಳು ವಿಷಯಗಳನ್ನು "ನೆನಪಿಟ್ಟುಕೊಳ್ಳಬೇಕು": ಪ್ರಸ್ತುತ ಇನ್‌ಪುಟ್ ಮೌಲ್ಯ, ಪ್ರಸ್ತುತ ಚಿತ್ರ, ಶಾಪಿಂಗ್ ಕಾರ್ಟ್. ರಿಯಾಕ್ಟ್‌ನಲ್ಲಿ, ಈ ರೀತಿಯ ಘಟಕ-ನಿರ್ದಿಷ್ಟ ಸ್ಮರಣೆಯನ್ನು *ಸ್ಟೇಟ್* ಎಂದು ಕರೆಯಲಾಗುತ್ತದೆ.

ನೀವು [`useState`](/reference/react/useState) ಹುಕ್‌ನೊಂದಿಗೆ ಕೊಂಪೊನೆಂಟಕ್ಕೆ ಸ್ಟೇಟ್ ಸೇರಿಸಬಹುದು. *ಹುಕ್ಸ್* ವಿಶೇಷ ಫಂಕ್ಷನ್ಗಳಾಗಿವೆ ಅದು ನಿಮ್ಮ ಕೊಂಪೊನೆಂಟ್ಗಳನ್ನು ರಿಯಾಕ್ಟ್ ವೈಶಿಷ್ಟ್ಯಗಳನ್ನು ಬಳಸಲು ಅನುಮತಿಸುತ್ತದೆ (ಸ್ಟೇಟ್ ಆ ವೈಶಿಷ್ಟ್ಯಗಳಲ್ಲಿ ಒಂದಾಗಿದೆ). ಸ್ಟೇಟ್ ವೇರಿಯಬಲ್ ಅನ್ನು ಘೋಷಿಸಲು `useState` ಹುಕ್ ನಿಮಗೆ ಅನುಮತಿಸುತ್ತದೆ. ಇದು ಆರಂಭಿಕ ಸ್ಟೇಟನ್ನು ತೆಗೆದುಕೊಳ್ಳುತ್ತದೆ ಮತ್ತು ಒಂದು ಜೋಡಿ ಮೌಲ್ಯಗಳನ್ನು ಹಿಂತಿರುಗಿಸುತ್ತದೆ: ಪ್ರಸ್ತುತ ಸ್ಟೇಟ್, ಮತ್ತು ಅದನ್ನು ನವೀಕರಿಸಲು ನಿಮಗೆ ಅನುಮತಿಸುವ ಸ್ಟೇಟ್ ಸೆಟ್ಟರ್ ಫಂಕ್ಷನ್.

```js
const [index, setIndex] = useState(0);
const [showMore, setShowMore] = useState(false);
```

Here is how an image gallery uses and updates state on click:

<Sandpack>

```js
import { useState } from 'react';
import { sculptureList } from './data.js';

export default function Gallery() {
  const [index, setIndex] = useState(0);
  const [showMore, setShowMore] = useState(false);
  const hasNext = index < sculptureList.length - 1;

  function handleNextClick() {
    if (hasNext) {
      setIndex(index + 1);
    } else {
      setIndex(0);
    }
  }

  function handleMoreClick() {
    setShowMore(!showMore);
  }

  let sculpture = sculptureList[index];
  return (
    <>
      <button onClick={handleNextClick}>
        Next
      </button>
      <h2>
        <i>{sculpture.name} </i>
        by {sculpture.artist}
      </h2>
      <h3>
        ({index + 1} of {sculptureList.length})
      </h3>
      <button onClick={handleMoreClick}>
        {showMore ? 'Hide' : 'Show'} details
      </button>
      {showMore && <p>{sculpture.description}</p>}
      <img
        src={sculpture.url}
        alt={sculpture.alt}
      />
    </>
  );
}
```

```js src/data.js
export const sculptureList = [{
  name: 'Homenaje a la Neurocirugía',
  artist: 'Marta Colvin Andrade',
  description: 'Although Colvin is predominantly known for abstract themes that allude to pre-Hispanic symbols, this gigantic sculpture, an homage to neurosurgery, is one of her most recognizable public art pieces.',
  url: 'https://i.imgur.com/Mx7dA2Y.jpg',
  alt: 'A bronze statue of two crossed hands delicately holding a human brain in their fingertips.'
}, {
  name: 'Floralis Genérica',
  artist: 'Eduardo Catalano',
  description: 'This enormous (75 ft. or 23m) silver flower is located in Buenos Aires. It is designed to move, closing its petals in the evening or when strong winds blow and opening them in the morning.',
  url: 'https://i.imgur.com/ZF6s192m.jpg',
  alt: 'A gigantic metallic flower sculpture with reflective mirror-like petals and strong stamens.'
}, {
  name: 'Eternal Presence',
  artist: 'John Woodrow Wilson',
  description: 'Wilson was known for his preoccupation with equality, social justice, as well as the essential and spiritual qualities of humankind. This massive (7ft. or 2,13m) bronze represents what he described as "a symbolic Black presence infused with a sense of universal humanity."',
  url: 'https://i.imgur.com/aTtVpES.jpg',
  alt: 'The sculpture depicting a human head seems ever-present and solemn. It radiates calm and serenity.'
}, {
  name: 'Moai',
  artist: 'Unknown Artist',
  description: 'Located on the Easter Island, there are 1,000 moai, or extant monumental statues, created by the early Rapa Nui people, which some believe represented deified ancestors.',
  url: 'https://i.imgur.com/RCwLEoQm.jpg',
  alt: 'Three monumental stone busts with the heads that are disproportionately large with somber faces.'
}, {
  name: 'Blue Nana',
  artist: 'Niki de Saint Phalle',
  description: 'The Nanas are triumphant creatures, symbols of femininity and maternity. Initially, Saint Phalle used fabric and found objects for the Nanas, and later on introduced polyester to achieve a more vibrant effect.',
  url: 'https://i.imgur.com/Sd1AgUOm.jpg',
  alt: 'A large mosaic sculpture of a whimsical dancing female figure in a colorful costume emanating joy.'
}, {
  name: 'Ultimate Form',
  artist: 'Barbara Hepworth',
  description: 'This abstract bronze sculpture is a part of The Family of Man series located at Yorkshire Sculpture Park. Hepworth chose not to create literal representations of the world but developed abstract forms inspired by people and landscapes.',
  url: 'https://i.imgur.com/2heNQDcm.jpg',
  alt: 'A tall sculpture made of three elements stacked on each other reminding of a human figure.'
}, {
  name: 'Cavaliere',
  artist: 'Lamidi Olonade Fakeye',
  description: "Descended from four generations of woodcarvers, Fakeye's work blended traditional and contemporary Yoruba themes.",
  url: 'https://i.imgur.com/wIdGuZwm.png',
  alt: 'An intricate wood sculpture of a warrior with a focused face on a horse adorned with patterns.'
}, {
  name: 'Big Bellies',
  artist: 'Alina Szapocznikow',
  description: "Szapocznikow is known for her sculptures of the fragmented body as a metaphor for the fragility and impermanence of youth and beauty. This sculpture depicts two very realistic large bellies stacked on top of each other, each around five feet (1,5m) tall.",
  url: 'https://i.imgur.com/AlHTAdDm.jpg',
  alt: 'The sculpture reminds a cascade of folds, quite different from bellies in classical sculptures.'
}, {
  name: 'Terracotta Army',
  artist: 'Unknown Artist',
  description: 'The Terracotta Army is a collection of terracotta sculptures depicting the armies of Qin Shi Huang, the first Emperor of China. The army consisted of more than 8,000 soldiers, 130 chariots with 520 horses, and 150 cavalry horses.',
  url: 'https://i.imgur.com/HMFmH6m.jpg',
  alt: '12 terracotta sculptures of solemn warriors, each with a unique facial expression and armor.'
}, {
  name: 'Lunar Landscape',
  artist: 'Louise Nevelson',
  description: 'Nevelson was known for scavenging objects from New York City debris, which she would later assemble into monumental constructions. In this one, she used disparate parts like a bedpost, juggling pin, and seat fragment, nailing and gluing them into boxes that reflect the influence of Cubism’s geometric abstraction of space and form.',
  url: 'https://i.imgur.com/rN7hY6om.jpg',
  alt: 'A black matte sculpture where the individual elements are initially indistinguishable.'
}, {
  name: 'Aureole',
  artist: 'Ranjani Shettar',
  description: 'Shettar merges the traditional and the modern, the natural and the industrial. Her art focuses on the relationship between man and nature. Her work was described as compelling both abstractly and figuratively, gravity defying, and a "fine synthesis of unlikely materials."',
  url: 'https://i.imgur.com/okTpbHhm.jpg',
  alt: 'A pale wire-like sculpture mounted on concrete wall and descending on the floor. It appears light.'
}, {
  name: 'Hippos',
  artist: 'Taipei Zoo',
  description: 'The Taipei Zoo commissioned a Hippo Square featuring submerged hippos at play.',
  url: 'https://i.imgur.com/6o5Vuyu.jpg',
  alt: 'A group of bronze hippo sculptures emerging from the sett sidewalk as if they were swimming.'
}];
```

```css
h2 { margin-top: 10px; margin-bottom: 0; }
h3 {
 margin-top: 5px;
 font-weight: normal;
 font-size: 100%;
}
img { width: 120px; height: 120px; }
button {
  display: block;
  margin-top: 10px;
  margin-bottom: 10px;
}
```

</Sandpack>

<LearnMore path="/learn/state-a-components-memory">

Read **[State: A Component's Memory](/learn/state-a-components-memory)** to learn how to remember a value and update it on interaction.

</LearnMore>

## Render and commit {/*render-and-commit*/}

ನಿಮ್ಮ ಕೊಂಪೊನೆಂಟ್ಗಳನ್ನು ಸ್ಕ್ರೀನ್ ಮೇಲೆ ಪ್ರದರ್ಶಿಸುವ ಮೊದಲು, ಅವುಗಳನ್ನು ರಿಯಾಕ್ಟ್ ಮೂಲಕ ಸಲ್ಲಿಸಬೇಕು. ಈ ಪ್ರಕ್ರಿಯೆಯಲ್ಲಿನ ಹಂತಗಳನ್ನು ಅರ್ಥಮಾಡಿಕೊಳ್ಳುವುದು ನಿಮ್ಮ ಕೋಡ್ ಅನ್ನು ಹೇಗೆ ಕಾರ್ಯಗತಗೊಳಿಸುತ್ತದೆ ಮತ್ತು ಅದರ ನಡವಳಿಕೆಯನ್ನು ವಿವರಿಸಲು ನಿಮಗೆ ಸಹಾಯ ಮಾಡುತ್ತದೆ.

ನಿಮ್ಮ ಕೊಂಪೊನೆಂಟ್ಗಳು ಅಡುಗೆಮನೆಯಲ್ಲಿ ಅಡುಗೆಯವರು ಎಂದು ಊಹಿಸಿ, ಪದಾರ್ಥಗಳಿಂದ ಟೇಸ್ಟಿ ಭಕ್ಷ್ಯಗಳನ್ನು ಜೋಡಿಸಿ. ಈ ಸನ್ನಿವೇಶದಲ್ಲಿ, ಗ್ರಾಹಕರಿಂದ ವಿನಂತಿಗಳನ್ನು ಸಲ್ಲಿಸುವ ಮತ್ತು ಅವರ ಆದೇಶಗಳನ್ನು ತರುವ ಮಾಣಿಯೇ ರಿಯಾಕ್ಟ್. UI ಅನ್ನು ವಿನಂತಿಸುವ ಮತ್ತು ಸೇವೆ ಮಾಡುವ ಈ ಪ್ರಕ್ರಿಯೆಯು ಮೂರು ಹಂತಗಳನ್ನು ಹೊಂದಿದೆ

1. **ಟ್ರಿಗ್ಗರಿಂಗ್** ರೆಂಡರ್ (ಗ್ರಾಹಕರ ಆರ್ಡರ್ ಅನ್ನು ಅಡುಗೆ ಮನೆಗೆ ತಲುಪಿಸುವುದು)
2. **ರೆಂಡರಿಂಗ್** ಕೊಂಪೊನೆಂಟ್ (ಅಡುಗೆಮನೆಯಲ್ಲಿ ಆದೇಶವನ್ನು ಸಿದ್ಧಪಡಿಸುವುದು)
3. DOM ಗೆ **ಕಮ್ಮಿಟ್ ಮಾಡುವದು** (ಮೇಜಿನ ಮೇಲೆ ಆದೇಶವನ್ನು ಇರಿಸುವುದು)

<IllustrationBlock sequential>
  <Illustration caption="Trigger" alt="React as a server in a restaurant, fetching orders from the users and delivering them to the Component Kitchen." src="/images/docs/illustrations/i_render-and-commit1.png" />
  <Illustration caption="Render" alt="The Card Chef gives React a fresh Card component." src="/images/docs/illustrations/i_render-and-commit2.png" />
  <Illustration caption="Commit" alt="React delivers the Card to the user at their table." src="/images/docs/illustrations/i_render-and-commit3.png" />
</IllustrationBlock>

<LearnMore path="/learn/render-and-commit">

Read **[Render and Commit](/learn/render-and-commit)** to learn the lifecycle of a UI update.

</LearnMore>

## State as a snapshot {/*state-as-a-snapshot*/}

ಸಾಮಾನ್ಯ ಜಾವಾಸ್ಕ್ರಿಪ್ಟ್ ವೇರಿಯೇಬಲ್‌ಗಳಿಗಿಂತ ಭಿನ್ನವಾಗಿ, ರಿಯಾಕ್ಟ್ ಸ್ಟೇಟ್ ಸ್ನ್ಯಾಪ್‌ಶಾಟ್‌ನಂತೆ ವರ್ತಿಸುತ್ತದೆ. ಇದನ್ನು ಹೊಂದಿಸುವುದರಿಂದ ನೀವು ಈಗಾಗಲೇ ಹೊಂದಿರುವ ಸ್ಟೇಟ್ ವೇರಿಯಬಲ್ ಅನ್ನು ಬದಲಾಯಿಸುವುದಿಲ್ಲ, ಬದಲಿಗೆ ಮರು-ರೆಂಡರ್ ಅನ್ನು ಪ್ರಚೋದಿಸುತ್ತದೆ. ಇದು ಮೊದಲಿಗೆ ಆಶ್ಚರ್ಯವಾಗಬಹುದು!

```js
console.log(count);  // 0
setCount(count + 1); // Request a re-render with 1
console.log(count);  // Still 0!
```

ಈ ನಡವಳಿಕೆಯು ಸೂಕ್ಷ್ಮ ಬಗ್ಗಳನ್ನು ತಪ್ಪಿಸಲು ನಿಮಗೆ ಸಹಾಯ ಮಾಡುತ್ತದೆ. ಇಲ್ಲಿ ಸ್ವಲ್ಪ ಚಾಟ್ ಅಪ್ಲಿಕೇಶನ್ ಇದೆ. ನೀವು ಮೊದಲು "Send" ಒತ್ತಿ ಮತ್ತು *ನಂತರ* ಸ್ವೀಕರಿಸುವವರನ್ನು ಬಾಬ್‌ಗೆ ಬದಲಾಯಿಸಿದರೆ ಏನಾಗುತ್ತದೆ ಎಂದು ಊಹಿಸಲು ಪ್ರಯತ್ನಿಸಿ. ಐದು ಸೆಕೆಂಡುಗಳ ನಂತರ `ಎಚ್ಚರಿಕೆ~ಯಲ್ಲಿ ಯಾರ ಹೆಸರು ಕಾಣಿಸಿಕೊಳ್ಳುತ್ತದೆ?

<Sandpack>

```js
import { useState } from 'react';

export default function Form() {
  const [to, setTo] = useState('Alice');
  const [message, setMessage] = useState('Hello');

  function handleSubmit(e) {
    e.preventDefault();
    setTimeout(() => {
      alert(`You said ${message} to ${to}`);
    }, 5000);
  }

  return (
    <form onSubmit={handleSubmit}>
      <label>
        To:{' '}
        <select
          value={to}
          onChange={e => setTo(e.target.value)}>
          <option value="Alice">Alice</option>
          <option value="Bob">Bob</option>
        </select>
      </label>
      <textarea
        placeholder="Message"
        value={message}
        onChange={e => setMessage(e.target.value)}
      />
      <button type="submit">Send</button>
    </form>
  );
}
```

```css
label, textarea { margin-bottom: 10px; display: block; }
```

</Sandpack>


<LearnMore path="/learn/state-as-a-snapshot">

Read **[State as a Snapshot](/learn/state-as-a-snapshot)** to learn why state appears "fixed" and unchanging inside the event handlers.

</LearnMore>

## Queueing a series of state updates {/*queueing-a-series-of-state-updates*/}

ಈ ಕೊಂಪೊನೆಂಟ್ ದೋಷಯುಕ್ತವಾಗಿದೆ: "+3" ಅನ್ನು ಕ್ಲಿಕ್ ಮಾಡುವುದರಿಂದ ಸ್ಕೋರ್ ಅನ್ನು ಒಮ್ಮೆ ಮಾತ್ರ ಹೆಚ್ಚಿಸುತ್ತದೆ.

<Sandpack>

```js
import { useState } from 'react';

export default function Counter() {
  const [score, setScore] = useState(0);

  function increment() {
    setScore(score + 1);
  }

  return (
    <>
      <button onClick={() => increment()}>+1</button>
      <button onClick={() => {
        increment();
        increment();
        increment();
      }}>+3</button>
      <h1>Score: {score}</h1>
    </>
  )
}
```

```css
button { display: inline-block; margin: 10px; font-size: 20px; }
```

</Sandpack>

[State as a Snapshot](/learn/state-as-a-snapshot) explains why this is happening. Setting state requests a new re-render, but does not change it in the already running code. So `score` continues to be `0` right after you call `setScore(score + 1)`.

```js
console.log(score);  // 0
setScore(score + 1); // setScore(0 + 1);
console.log(score);  // 0
setScore(score + 1); // setScore(0 + 1);
console.log(score);  // 0
setScore(score + 1); // setScore(0 + 1);
console.log(score);  // 0
```

You can fix this by passing an *updater function* when setting state. Notice how replacing `setScore(score + 1)` with `setScore(s => s + 1)` fixes the "+3" button. This lets you queue multiple state updates.

<Sandpack>

```js
import { useState } from 'react';

export default function Counter() {
  const [score, setScore] = useState(0);

  function increment() {
    setScore(s => s + 1);
  }

  return (
    <>
      <button onClick={() => increment()}>+1</button>
      <button onClick={() => {
        increment();
        increment();
        increment();
      }}>+3</button>
      <h1>Score: {score}</h1>
    </>
  )
}
```

```css
button { display: inline-block; margin: 10px; font-size: 20px; }
```

</Sandpack>

<LearnMore path="/learn/queueing-a-series-of-state-updates">

Read **[Queueing a Series of State Updates](/learn/queueing-a-series-of-state-updates)** to learn how to queue a sequence of state updates.

</LearnMore>

## Updating objects in state {/*updating-objects-in-state*/}

ಆಬ್ಜೆಕ್ಟ್‌ಗಳು ಸೇರಿದಂತೆ ಯಾವುದೇ ರೀತಿಯ ಜಾವಾಸ್ಕ್ರಿಪ್ಟ್ ವೇರಿಯೇಬಲ್‌ವನ್ನು ಸ್ಟೇಟ್ ಹಿಡಿದಿಟ್ಟುಕೊಳ್ಳಬಹುದು. ಆದರೆ ನೀವು ನೇರವಾಗಿ ರಿಯಾಕ್ಟ್ ಸ್ಟೇಟ್‌ನಲ್ಲಿ ಹಿಡಿದಿರುವ ವಸ್ತುಗಳು ಮತ್ತು ಅರೇಗಳನ್ನು ಬದಲಾಯಿಸಬಾರದು. ಬದಲಾಗಿ, ನೀವು ಆಬ್ಜೆಕ್ಟ್ ಮತ್ತು ಅರೇಯನ್ನು ನವೀಕರಿಸಲು ಬಯಸಿದಾಗ, ನೀವು ಹೊಸದನ್ನು ರಚಿಸಬೇಕು (ಅಥವಾ ಅಸ್ತಿತ್ವದಲ್ಲಿರುವ ಒಂದರ ನಕಲನ್ನು ಮಾಡಿ), ತದನಂತರ ಆ ನಕಲನ್ನು ಬಳಸಲು ಸ್ಟೇಟ್ ನವೀಕರಿಸಿ.

ಸಾಮಾನ್ಯವಾಗಿ, ನೀವು ಬದಲಾಯಿಸಲು ಬಯಸುವ ಆಬ್ಜೆಕ್ಟ್‌ಗಳು ಮತ್ತು ಅರೇಗಳನ್ನು ನಕಲಿಸಲು ನೀವು `...` ಸ್ಪ್ರೆಡ್ ಸಿಂಟ್ಯಾಕ್ಸ್ ಅನ್ನು ಬಳಸುತ್ತೀರಿ. ಉದಾಹರಣೆಗೆ, ನೆಸ್ಟೆಡ್ ಆಬ್ಜೆಕ್ಟ್‌ವನ್ನು ನವೀಕರಿಸುವುದು ಈ ರೀತಿ ಕಾಣಿಸಬಹುದು:

<Sandpack>

```js
import { useState } from 'react';

export default function Form() {
  const [person, setPerson] = useState({
    name: 'Niki de Saint Phalle',
    artwork: {
      title: 'Blue Nana',
      city: 'Hamburg',
      image: 'https://i.imgur.com/Sd1AgUOm.jpg',
    }
  });

  function handleNameChange(e) {
    setPerson({
      ...person,
      name: e.target.value
    });
  }

  function handleTitleChange(e) {
    setPerson({
      ...person,
      artwork: {
        ...person.artwork,
        title: e.target.value
      }
    });
  }

  function handleCityChange(e) {
    setPerson({
      ...person,
      artwork: {
        ...person.artwork,
        city: e.target.value
      }
    });
  }

  function handleImageChange(e) {
    setPerson({
      ...person,
      artwork: {
        ...person.artwork,
        image: e.target.value
      }
    });
  }

  return (
    <>
      <label>
        Name:
        <input
          value={person.name}
          onChange={handleNameChange}
        />
      </label>
      <label>
        Title:
        <input
          value={person.artwork.title}
          onChange={handleTitleChange}
        />
      </label>
      <label>
        City:
        <input
          value={person.artwork.city}
          onChange={handleCityChange}
        />
      </label>
      <label>
        Image:
        <input
          value={person.artwork.image}
          onChange={handleImageChange}
        />
      </label>
      <p>
        <i>{person.artwork.title}</i>
        {' by '}
        {person.name}
        <br />
        (located in {person.artwork.city})
      </p>
      <img
        src={person.artwork.image}
        alt={person.artwork.title}
      />
    </>
  );
}
```

```css
label { display: block; }
input { margin-left: 5px; margin-bottom: 5px; }
img { width: 200px; height: 200px; }
```

</Sandpack>

ಕೋಡ್‌ನಲ್ಲಿ ಆಬ್ಜೆಕ್ಟ್ಗಳನ್ನು ನಕಲಿಸುವುದು ಬೇಸರದ ಸಂಗತಿಯಾದರೆ, ಪುನರಾವರ್ತಿತ ಕೋಡ್ ಅನ್ನು ಕಡಿಮೆ ಮಾಡಲು ನೀವು [Immer](https://github.com/immerjs/use-immer) ನಂತಹ ಲೈಬ್ರರಿಯನ್ನು ಬಳಸಬಹುದು:

<Sandpack>

```js
import { useImmer } from 'use-immer';

export default function Form() {
  const [person, updatePerson] = useImmer({
    name: 'Niki de Saint Phalle',
    artwork: {
      title: 'Blue Nana',
      city: 'Hamburg',
      image: 'https://i.imgur.com/Sd1AgUOm.jpg',
    }
  });

  function handleNameChange(e) {
    updatePerson(draft => {
      draft.name = e.target.value;
    });
  }

  function handleTitleChange(e) {
    updatePerson(draft => {
      draft.artwork.title = e.target.value;
    });
  }

  function handleCityChange(e) {
    updatePerson(draft => {
      draft.artwork.city = e.target.value;
    });
  }

  function handleImageChange(e) {
    updatePerson(draft => {
      draft.artwork.image = e.target.value;
    });
  }

  return (
    <>
      <label>
        Name:
        <input
          value={person.name}
          onChange={handleNameChange}
        />
      </label>
      <label>
        Title:
        <input
          value={person.artwork.title}
          onChange={handleTitleChange}
        />
      </label>
      <label>
        City:
        <input
          value={person.artwork.city}
          onChange={handleCityChange}
        />
      </label>
      <label>
        Image:
        <input
          value={person.artwork.image}
          onChange={handleImageChange}
        />
      </label>
      <p>
        <i>{person.artwork.title}</i>
        {' by '}
        {person.name}
        <br />
        (located in {person.artwork.city})
      </p>
      <img
        src={person.artwork.image}
        alt={person.artwork.title}
      />
    </>
  );
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

```css
label { display: block; }
input { margin-left: 5px; margin-bottom: 5px; }
img { width: 200px; height: 200px; }
```

</Sandpack>

<LearnMore path="/learn/updating-objects-in-state">

Read **[Updating Objects in State](/learn/updating-objects-in-state)** to learn how to update objects correctly.

</LearnMore>

## Updating arrays in state {/*updating-arrays-in-state*/}

ಅರೇಗಳು ನೀವು ಸ್ಟೇಟ್ ಸಂಗ್ರಹಿಸಬಹುದಾದ ಮತ್ತು ಓದಲು-ಮಾತ್ರ ಎಂದು ಪರಿಗಣಿಸಬೇಕಾದ ಮತ್ತೊಂದು ರೀತಿಯ ರೂಪಾಂತರಿತ JavaScript ಆಬ್ಜೆಕ್ಟ್‌ಗಳು. ಆಬ್ಜೆಕ್ಟ್‌ಗಳಂತೆಯೇ, ನೀವು ಸ್ಟೇಟ್ಲಲಿ ಸಂಗ್ರಹವಾಗಿರುವ ರಚನೆಯನ್ನು ನವೀಕರಿಸಲು ಬಯಸಿದಾಗ, ನೀವು ಹೊಸದನ್ನು ರಚಿಸುವ ಅಗತ್ಯವಿದೆ (ಅಥವಾ ಅಸ್ತಿತ್ವದಲ್ಲಿರುವ ಒಂದರ ನಕಲನ್ನು ಮಾಡಿ), ತದನಂತರ ಹೊಸ ರಚನೆಯನ್ನು ಬಳಸಲು ಸ್ಟೇಟ್ ಹೊಂದಿಸಿ:

<Sandpack>

```js
import { useState } from 'react';

let nextId = 3;
const initialList = [
  { id: 0, title: 'Big Bellies', seen: false },
  { id: 1, title: 'Lunar Landscape', seen: false },
  { id: 2, title: 'Terracotta Army', seen: true },
];

export default function BucketList() {
  const [list, setList] = useState(
    initialList
  );

  function handleToggle(artworkId, nextSeen) {
    setList(list.map(artwork => {
      if (artwork.id === artworkId) {
        return { ...artwork, seen: nextSeen };
      } else {
        return artwork;
      }
    }));
  }

  return (
    <>
      <h1>Art Bucket List</h1>
      <h2>My list of art to see:</h2>
      <ItemList
        artworks={list}
        onToggle={handleToggle} />
    </>
  );
}

function ItemList({ artworks, onToggle }) {
  return (
    <ul>
      {artworks.map(artwork => (
        <li key={artwork.id}>
          <label>
            <input
              type="checkbox"
              checked={artwork.seen}
              onChange={e => {
                onToggle(
                  artwork.id,
                  e.target.checked
                );
              }}
            />
            {artwork.title}
          </label>
        </li>
      ))}
    </ul>
  );
}
```

</Sandpack>

ಕೋಡ್‌ನಲ್ಲಿ ಆಬ್ಜೆಕ್ಟ್ಗಳನ್ನು ನಕಲಿಸುವುದು ಬೇಸರದ ಸಂಗತಿಯಾದರೆ, ಪುನರಾವರ್ತಿತ ಕೋಡ್ ಅನ್ನು ಕಡಿಮೆ ಮಾಡಲು ನೀವು [Immer](https://github.com/immerjs/use-immer) ನಂತಹ ಲೈಬ್ರರಿಯನ್ನು ಬಳಸಬಹುದು:

<Sandpack>

```js
import { useState } from 'react';
import { useImmer } from 'use-immer';

let nextId = 3;
const initialList = [
  { id: 0, title: 'Big Bellies', seen: false },
  { id: 1, title: 'Lunar Landscape', seen: false },
  { id: 2, title: 'Terracotta Army', seen: true },
];

export default function BucketList() {
  const [list, updateList] = useImmer(initialList);

  function handleToggle(artworkId, nextSeen) {
    updateList(draft => {
      const artwork = draft.find(a =>
        a.id === artworkId
      );
      artwork.seen = nextSeen;
    });
  }

  return (
    <>
      <h1>Art Bucket List</h1>
      <h2>My list of art to see:</h2>
      <ItemList
        artworks={list}
        onToggle={handleToggle} />
    </>
  );
}

function ItemList({ artworks, onToggle }) {
  return (
    <ul>
      {artworks.map(artwork => (
        <li key={artwork.id}>
          <label>
            <input
              type="checkbox"
              checked={artwork.seen}
              onChange={e => {
                onToggle(
                  artwork.id,
                  e.target.checked
                );
              }}
            />
            {artwork.title}
          </label>
        </li>
      ))}
    </ul>
  );
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

<LearnMore path="/learn/updating-arrays-in-state">

Read **[Updating Arrays in State](/learn/updating-arrays-in-state)** to learn how to update arrays correctly.

</LearnMore>

## What's next? {/*whats-next*/}

Head over to [Responding to Events](/learn/responding-to-events) to start reading this chapter page by page!

Or, if you're already familiar with these topics, why not read about [Managing State](/learn/managing-state)?
