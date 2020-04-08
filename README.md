# Coding Challenge Experience Engineering

This project is setup using the Vue CLI.

## Project Notes

I tried to setup the project as much as I could with consideration as to how I'd set up a resuable layout. The layout components

```
ButtonGroup
```

and 

```
SectionContainer
```

Are components I'd usually create under directory for layouts that can be used as templates across a large enterprise site or application. In the time spent I was able to successfully load a primitive, load a model, update colors, and animate the primitive. I ran into issues with three.js integration with Vue.js, but I think that had more to do with my experience with three.js. 

A project setup with **AFRAME** is probably more ideal for rapid development on an enterprise level application. (I wanted to display basic competency for this exercise)

## NPM Modules used

- [three](https://www.npmjs.com/package/three)

## CSS

This exercise uses custom CSS with layout components to encapsulate and reuse containers. For a larger project a framework such as [buefy](https://buefy.org/) would be suitable to allow for faster development for enterprise.

## Completed Challenges

:white_check_mark: Load a primitive
:white_check_mark: Load a gLTF model
:white_check_mark: Added scene lighting
:white_check_mark: Updating primitive colors when clicking buttons
:white_check_mark: Animated primitive

## Project setup

```
npm install
```

### Compiles and hot-reloads for development

```
npm run serve
```

### Compiles and minifies for production

```
npm run build
```

### Customize configuration

See [Configuration Reference](https://cli.vuejs.org/config/).
