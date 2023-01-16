# react-scratch-code

> A scratch card component for React

##### Improvement ✨
- Avoid preventDefault from passive event listeners

## Install

```bash
npm install --save react-scratch-code
```
or
```bash
yarn add react-scratch-code
```


## Usage

```tsx
import React, { useRef }  from 'react';
import ScratchCard from 'react-scratch-code';

import * as IMG from './img.jpg';

const App = () => {

  const ref = useRef<ScratchCard>(null);

  const onClickReset = () => {
    ref.current && ref.current.reset();
  }

  return (
    <div>
      <button onClick={onClickReset}>Reset</button>
      <ScratchCard
        width={320}
        height={226}
        image={IMG}
        finishPercent={80}
        onComplete={() => console.log('complete')}
      >
        <div style={{
          display: 'flex',
          width: '100%',
          height: '100%',
          alignItems: 'center',
          justifyContent: 'center'
        }}
        >
          <h1>Scratch card</h1>
        </div>
      </ScratchCard>
    </div>
  );
};
```

### Custom brush

```tsx
const App = () => {
  return (
    <div>
      <ScratchCard
        width={320}
        height={226}
        image={IMG}
        finishPercent={80}
        customBrush={{
          image: require('./brush.img'),
          width: 15,
          height: 15
        }}
      >
        <h1>Scratch card</h1>
      </ScratchCard>
    </div>
  );
};
```

or you can use CUSTOM_BRUSH_PRESET object

```tsx
import { CUSTOM_BRUSH_PRESET } from 'react-scratch-code';

const App = () => {
  return (
    <div>
      <ScratchCard
        width={320}
        height={226}
        image={IMG}
        finishPercent={80}
        customBrush={CUSTOM_BRUSH_PRESET}
      >
        <h1>Scratch card</h1>
      </ScratchCard>
    </div>
  )
}
```


## Type

### Props

| **name**          | **type**        | **default** |
|-------------------|-----------------|-------------|
| width             | number          |             |
| height            | number          |             |
| image             | File or Base64  |             |
| finishPercent     | ?number         | 70          |
| brushSize         | ?number         | 20          |
| fadeOutOnComplete | ?boolean        | true        |
| onComplete        | ?callback       |             |
| customBrush       | ?CustomBrush    |             |
| customCheckZone   | ?CustomCheckZone|             |

### CustomBrush

| **name** | **type**       |
|----------|----------------|
| width    | number         |
| height   | number         |
| image    | File or Base64 |

### CustomCheckZone

| **name** | **type**       |
|----------|----------------|
| x        | number         |
| y        | number         |
| width    | number         |
| height   | number         |



## License

MIT © [anujverma000](https://github.com/anujverma000)
