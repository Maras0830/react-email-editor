# React Email Editor

The excellent drag-n-drop email editor by [Unroll.io](https://unroll.io) as a [React.js](http://facebook.github.io/react) component. This is the most powerful and developer friendly visual email builder for your app.

Video Overview |
:---: |
[![React Email Editor](https://s3.amazonaws.com/unroll-assets/unrollyoutube.png)](https://www.youtube.com/watch?v=IoY7-NZ8TcA) |
*Watch video overview: https://youtu.be/IoY7-NZ8TcA* |


## Live Demo

Check out the live demo here: http://react-email-editor-demo.netlify.com/ ([Source Code](https://github.com/unroll-io/react-email-editor/blob/master/demo/src/index.js))

## Blog Post

Here's a blog post with a quickstart guide: https://medium.com/unroll-blog/creating-a-drag-n-drop-email-editor-with-react-db1e9eb42386

## Installation

The easiest way to use React Email Editor is to install it from NPM and include it in your own React build process.

```
npm install react-email-editor --save
```

## Usage

Require the EmailEditor component and render it with JSX:

```javascript
import React, { Component } from 'react'
import { render } from 'react-dom'

import EmailEditor from 'react-email-editor'

class App extends Component {
  render() {
    return <div>
      <h1>react-email-editor Demo</h1>

      <div>
        <button onClick={this.exportHtml}>Export HTML</button>
      </div>

      <EmailEditor
        ref={designer => this.designer = designer}
      />
    </div>
  }

  exportHtml = () => {
    this.designer.exportHtml(data => {
      const { design, html } = data
      console.log('exportHtml', html)
    })
  }
}

render(<App />, document.getElementById('app'))
```

### Properties

* `style` `Object` style object for the editor container (default {})
* `minHeight` `String` minimum height to initialize the editor with (default 500px)
* `onLoad` `Function` called when the editor has finished loading
* `options` `Object` options passed to the Unroll editor instance (default {})

See the [Unroll Docs](https://docs.unroll.io/getting-started/) for all available options.

### Methods

* `loadDesign` - `function(Object data)` - Takes the design JSON and loads it in the editor
* `saveDesign` - `function(Function callback)` - Returns the design JSON in a callback function
* `exportHtml` - `function(Function callback)` - Returns the design HTML and JSON in a callback function

See the [example source](https://github.com/unroll-io/react-email-editor/blob/master/demo/src/index.js) for a reference implementation.

### License

Copyright (c) 2017 Unroll. [MIT](LICENSE) Licensed.
