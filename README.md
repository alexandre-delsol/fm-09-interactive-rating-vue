# Frontend Mentor - Interactive Rating Component

This is my solution to the [Interactive Rating Component challenge on Frontend Mentor](https://www.frontendmentor.io/challenges/interactive-rating-component-koxpeBUmI).

## Overview

### The challenge

Users should be able to:

* Select a rating from 1 to 5
* Submit their rating
* See a thank-you state displaying their selected rating
* Experience a responsive layout across different screen sizes

### Screenshot

![Interactive Rating Component](./design/desktop-design.jpg)

## Built with

* Vue.js
* TypeScript
* Vite
* Semantic HTML5
* CSS
* Flexbox
* Responsive design

## What I learned

This project helped me practice building an interactive component with Vue.js and TypeScript.

I worked with:

* Vue `ref()` for reactive state
* `v-if` / `v-else` for conditional rendering
* `v-for` for rendering the rating buttons
* Props with `defineProps()`
* Custom events with `defineEmits()`
* Passing data from a child component to a parent component
* Passing the selected rating from the parent to the thank-you component
* Component-based architecture
* Responsive CSS

### Component structure

```text
App.vue
├── RatingCard.vue
└── ThankYouCard.vue
```

The `RatingCard` manages the user's selection and emits the selected rating to `App.vue`.

`App.vue` stores the selected rating and controls which card is displayed.

`ThankYouCard` receives the selected rating through props.

```text
RatingCard
    │
    │ emit("submit", rating)
    ▼
  App.vue
    │
    │ :selectedRating
    ▼
ThankYouCard
```

## Continued development

I would like to continue improving my understanding of:

* Vue component communication
* Form and interaction accessibility
* More advanced Vue patterns
* Responsive design
* CSS architecture

## Useful resources

* [Vue.js Documentation](https://vuejs.org/)
* [TypeScript Documentation](https://www.typescriptlang.org/)
* [Frontend Mentor](https://www.frontendmentor.io/)

## Author

* Frontend Mentor - [@alexandre-delsol](https://www.frontendmentor.io/profile/alexandre-delsol)
* GitHub - [@alexandre-delsol](https://github.com/alexandre-delsol)
