# React Dialog

React component for dialog widget.

## Installation

React Dialog is available as an [npm package](https://www.npmjs.org/package/react-dialog).
```sh
npm install react-dialog
```

Use [browserify](http://browserify.org/) and [reactify](https://github.com/andreypopp/reactify) for dependency management and JSX transformation.

All styles written in CSS and are in css/index.css

## Demo

[http://mohitgupta8888.github.io/react-dialog](https://mohitgupta8888.github.io/react-dialog/?selectedKind=React%20Dialog&selectedStory=basic&full=0&down=0&left=1&panelRight=0)

## Usage

```javascript
import React, { Component } from 'react';
import Dialog from 'react-dialog';

// Be sure to include styles at some point, probably during your bootstrapping
import 'react-dialog/css/index.css';

class Example extends Component {
  state = {
    isDialogOpen: false
  }

  openDialog = () => this.setState({ isDialogOpen: true })

  handleClose = () => this.setState({ isDialogOpen: false })

  render() {
    return (
      <div className="container">
        <button type="button" onClick={this.openDialog}>Open Dialog</button>
        {this.state.isDialogOpen &&
          <Dialog
            title="Dialog Title"
            modal
            onClose={this.handleClose}
            buttons={[{
              text: 'Close',
              onClick: () => this.handleClose()
            }]}
          >
            <h1>Dialog Content</h1>
            <p>More Content. Anything goes here</p>
          </Dialog>
        }
      </div>
    );
  }
}
```

## API

#### props.height

 - `Number` || `String`
 - default: `300`
 - Specifies the width of Dialog (String or Number) '80%' or '500'

#### props.width

 - `Number` || `String`
 - default: `500`
 - Whether overlay is added to dialog or not

#### props.modal

 - `Boolean`
 - default: `false`
 - Whether overlay is added to dialog or not

#### props.closeOnEscape

 - `Boolean`
 - Default: `true`
 - If true, the `props.onClose` event will be triggered if user presses Esc key on keyboard.

#### props.isDraggable

 - `Boolean`
 - default: `false`
 - Whether dialog is draggable

#### props.isResizable

 - `Boolean`
 - default: `false`
 - Whether dialog is resizable

#### props.title

 - `String` or `ReactElement`
 - default: `''`
 - Title of dialog box. Could be `string` or some react element.

#### props.hasCloseIcon

 - `Boolean`
 - default: `true`
 - Whether close icon is displayed at dialog title

#### props.allowMinimize

 - `Boolean`
 - default: `false`
 - Whether dialog can be minimized or not

#### props.allowMaximize

 - `Boolean`
 - default: `false`
 - Whether dialog can be maximized (full screen) or not 

#### props.onClose

 - `Function`
 - default: `null`
 - Function that will be triggered whenever there is a close event.

#### props.buttons

 ```
[{
    text: string,
    onClick: Function,
    className: string
}]
```
or
```
[ReactElements]
 ```
 - Default: `null`
 - Represents the collection of buttons to be render in dialog footer


#### props.position

```
{
    x: number,
    y: number
}
 ```
 - default: center of the screen:
```
{
    x: -250, // -width / 2
    y: -150  // -height / 2
}
 ```
 
 - The shift in the `x` and `y` axis relative to the center of the screen (`{ x: 0, y: 0 }`)

## License

MIT
