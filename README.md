# vue-simple-flowchart

## Introduction

a lightweight flowchart editor for Vue.js, code with vanillaJS,

Original Author: https://github.com/Jeffreyrn/vue-simple-flowchart

### Note

My sincerest apologies to the open source community for allowing this project to stagnate. I hope it was useful for some of you as a jumping-off point.

## Demo

Original Demo

[https://jeffreyrn.github.io/vue-simple-flowchart/demo/](https://jeffreyrn.github.io/vue-simple-flowchart/demo/)

![Gallery](https://i.imgur.com/c6F0zfL.png)

### Feature

- drag to connent two node, click to delete link
- support add, delete, save node
- reactive flowchart data

### Usage

import in script

```js
import SimpleFlowchart from "vue-simple-flowchart";
```

register the component, and add below to html:

```html
<simple-flowchart :scene.sync="data"></simple-flowchart>
```

then set data for flowchart component, for example:

```js
data() {
    return {
        data: {
            centerX: 1024,
                centerY: 140,
                scale: 1,
                nodes: [
                    {
                        id: 2,
                        x: -700,
                        y: -69,
                        type: 'Action',
                        label: 'test1',
                    },
                    {
                        id: 4,
                        x: -357,
                        y: 80,
                        type: 'Script',
                        label: 'test2',
                    },
                    {
                        id: 6,
                        x: -557,
                        y: 80,
                        type: 'Rule',
                        label: 'test3',
                    }
                    ],
                    links: [
                    {
                        id: 3,
                        from: 2, // node id the link start
                        to: 4,  // node id the link end
                    }
                ]
        },
    };
}
```

### Component

#### Attributes

- height, type: Number, default: 400

#### Events

- nodeClick, emit when node click, event = nodeID
- nodeUnselected, emit when node unselected, event = nodeID
- nodeDelete: emit when node deleted, event = nodeID
- linkBreak: emit when the selected link deleted, event = {id, from, to} (deleted link Object)
- linkAdded: emit when new link added, event = {id, from, to} (new link Object)
- canvasClick: emit when canvas click, event = { (Event Object) }

## TODO

- Add horizontal mode
- Optimizition for large node array
- Theme color configurable
- Remove Console.log in build mode
