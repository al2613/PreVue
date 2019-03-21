
## WHAT IS PREVUE
PreVue aims to streamline the development process by making it easy to visualize the architecture of a Vue application. PreVue makes Vue more accessible by allowing users to prototype components. With PreVue, users can easily set up their Vue component architecture with ease and export necessary code.

## USING PREVUE
* Download for MacOS: https://www.prevue.io/
* Using PreVue locally
    1. Fork and clone
    2. `npm install`

## Core Features:
  - Component creation: Insert a name and select desired HTML elements. The created component will render as a box on the main canvas. Child relationships can be established during component creation. Note that at least two components need to be created to be able to view selectable components in the select child dropdown 
  - Routes creation: Create different routes as needed for different application views
  - Editable popup modal: Once a component is created, it is editable by double clicking 
  - Draggable HTML elements: In Edit Mode, additional HTML element can be selected. HTML elements can be nested by dragging accordingly.
  - Live HTML code display: As selected HTML elements are dragged, the code display will change accordingly. It will be a live preview of the Vue template code
  - Exportable code: When you are happy with your work, you can export the entire project. The exported directory structure includes:
    ```
    src/
      assets/
      App.vue
      components/
        yourCreatedComponent.vue
      views/
        HomeView.vue
        yourCreatedRoute
     ```
  
      ### Navigating the Editor:
         cmd/ctrl + s: save
         cmd/ctrl + o: open
         cmd/ctrl + n: new project tab
         cmd/ctrl + t: close project tab
  
## FEATURES TO COME
- Support for React
- Prop passing

## CREDITS
- Hubert Lin
- Franklin Pinnock
- Annette Lin
- Daniel Shu

## License
MIT
