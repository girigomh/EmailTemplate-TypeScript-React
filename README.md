# React Email Editor

This is the most powerful and developer friendly visual email builder for your app.

|

## Live Demo

Check out the live demo here: http://react-email-editor-demo.netlify.com/ ([Source Code](https://github.com/girigomh/EmailTemplate-TypeScript-React))

## Installation

The easiest way to use React Email Editor is to install it from NPM and include it in your own React build process.

```
npm install react-email-editor --save
```

## Usage

Require the EmailEditor component and render it with JSX:

```javascript
import React, { useRef } from 'react';
import { render } from 'react-dom';

import EmailEditor from 'react-email-editor';

const App = (props) => {
  const emailEditorRef = useRef(null);

  const exportHtml = () => {
    emailEditorRef.current.editor.exportHtml((data) => {
      const { design, html } = data;
      console.log('exportHtml', html);
    });
  };

  const onReady = () => {
    // editor is ready
    // you can load your template here;
    // const templateJson = {};
    // emailEditorRef.current.editor.loadDesign(templateJson);
  };

  return (
    <div>
      <div>
        <button onClick={exportHtml}>Export HTML</button>
      </div>

      <EmailEditor ref={emailEditorRef} onReady={onReady} />
    </div>
  );
};

render(<App />, document.getElementById('app'));
```

### Methods

| method         | params              | description                                             |
| -------------- | ------------------- | ------------------------------------------------------- |
| **loadDesign** | `Object data`       | Takes the design JSON and loads it in the editor        |
| **saveDesign** | `Function callback` | Returns the design JSON in a callback function          |
| **exportHtml** | `Function callback` | Returns the design HTML and JSON in a callback function |

See the [example source](https://github.com/girigomh/EmailTemplate-TypeScript-React) for a reference implementation.
