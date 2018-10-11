![BEMex logo](images/logo.png "BEMex")

BEMex is an extended **B**lock **E**lement **M**odifier system featuring namespacing, layouts, states and js hooks. It's made to work well with component based javascript and unweildy long term projects that need a tidy CSS goal to work towards.

## Get Started

Get started by downloading the scaffolding for a generic component, page and variables file.

Download project scaffolding: [LESS](./scaffolding/less) | [SASS](./scaffolding/sass)

# Building on BEM
Here is the most obvious and easy example though to get your head around how basic BEM works.

```
<button class="button button--right"> <!-- The Block -->
    <span class="button__text button__text--inactive"> <!-- An Element -->
        OK
    </span>
    <span class="button__icon button__icon--checkbox"> <!-- An Element, with a modifier>
    </span>
</button>
```

The point of BEM is to make blocks reusuable, it's ugly and means you have a lot of HTML in your front end, but it works. It gets you out of deep inheritance which gets you in trouble, and uses the last declared class rule instead. It's a different sort of cascading for **C**ascading **S**tyle **S**heets.

# Extending with BEMex
Examples like the button above are everywhere but they don't reflect the difficult scenarios in the real world. In real life you change things on the outside of the button, and that affects the inside. Additionally you have other things like state and javascript hooks. That's why BEMex takes:

- Layouts
- States
- JS Hooks

out of the hands of a BEM component.


| Type       | Prefix   | Example | Description  | Typical CSS Properties |
|------------|----------|---------|--------------|------------|
| Component  | c-       | c-button c-list         | The blocks that form the backbone of an application and contain all of the cosmetics for a standalone block. A react component is not the same as a BEMex component | everything except sizing, positioning and margins
| Layout     | l-       | l-left l-container      | These modules are used to position c- blocks and structure an application’s layout. They can be built in a similar way to blocks but should never have anything other than positioning and sizing properties. | width, height, margin, padding, position
| Helpers     | h- | h-open h-visible h-uppercase      | Indicate different states that a c- block can have or when there is a minor change in one place on a global component. | display, opacity, animate, padding
| Javascript | js-      | js-next-page js-spinner | These indicate that JavaScript behavior is attached to a block. No styles should ever be associated with them; they are purely used to enable easier manipulation with script.                              | Never!

## The HTML
```
<!-- Centered Container  -->
<div class="l-container">

    <!-- Layout element, pushing it to the right -->
    <div class="l-container__right">

        <!-- Our button component. Has a JS hook. In a disabled state -->
        <button class="c-button js-ok h-disabled">

            <!-- The Text Element -->
            <span class="c-button__text">
                OK
            </span>

            <!-- Icon on the Element -->
            <span class="c-button__icon c-button__icon--checkbox"><span>
        </button>
    </div>
</div>
```

## The LESS/SASS

This code will work when run through both LESS or SASS
```
.l-container{
    display: flex;
    flex-direction: row;

    &__left, &__right{
         flex: 1 1 50%;
    }

    &__right{
        align-self: flex-end;
    }
    &__left{
        align-self: flex-start;
    }
}

.c-button{
    display: flex;
    /* Let the layout "l-" take care of how wide and where it is */
    flex-grow: 1;
    width: 100%;

    .h-disabled{
        color: grey;
    }

    &__text{
        justify-content: center;
    }

    &__icon{
        background-repeat: no-repeat;
        background-size: cover;
        background-position: center;
        width: 20px;
        height: 20px;

        &--checkbox{
            background-image: url('checkmark.png');
        }
    }

}
```

## When To BEMex
Deciding where to draw the line around the block when using BEMex is really difficult. For heading navigation, the block is the whole heading, the nav element or just the links. The answer is usually about as small an element as you can manage.

Here is an example of how the [Turbulent](http://www.turbulent.ca/) website could use BEMex.

![alt text](images/turbulentsite-css-example.png "Turbulent Home Page")

- ![#ff00ff](https://placehold.it/15/ff00ff/000000?text=+) **l-sidebar--left** The side container with a --left modifier
  - *l-sidebar__button* The container positions this button in place and gives it padding to keep it off the sides
    - ![#db4d37](https://placehold.it/15/db4d37/000000?text=+) c-button
      - *c-button__icon* The arrow icon
      - *c-button__text* The text inside the button
      - *c-button__hovertext* The text that is hidden until you hover

- ![#ff00ff](https://placehold.it/15/ff00ff/000000?text=+) **l-sidebar--right** The sidebar container with a --right modifier
  - *l-sidebar__button--bottomright h-hovered* The container positions this button in place. It has a bottom modifier to push it to the bottom.
      - ![#db4d37](https://placehold.it/15/db4d37/000000?text=+) **c-button**
      - *c-button__icon* The arrow icon
      - *c-button__text* The text inside the button
      - *c-button__hovertext* The text that is now visible because the h-hovered element is on
  -  *l-sidebar__navtoggle*  The container for the nav button
      - ![#db4d37](https://placehold.it/15/db4d37/000000?text=+) **c-icon** A block for an icon
        - *c-icon__icon c-icon__icon--nav* The actual icon that the block is for, and the modifier which makes it a nav icon

# Get Started

The order in precompiler files for both layouts and components is:

```
.c-component{
    flex-grow: 1; // The components own values

    .h-hidden{ } // Any direct component helpers

    &--modifiers{} // Any direct component modifiers

    &__element{ // The elements in the component

        color: red; // The elements own values

        .h-hidden{ } // Any direct element helpers

        &--modifiers{} // Any direct element modifiers
    }

    @media screen and (max-width: 800px){ //The media queries for the whole component
        flex-basis: 100%; // The component

        &__element{ // The elements in the component
            flex-basis: 100%;
        }
    }
}
```

# See Examples

- [Blocks vs Elements vs Modifiers](examples/block-element-modifier.md) A table with a header and cell highlighting showing the difference between the 3 parts of BEM
- [Helpers Example](examples/helper.md) Helpers being used to toggle between uppercase and lowercase
- [Nested Layouts](examples/nested-layouts.md) Showing sections and contents for nested positioning
- [Grid example](examples/grid.md) Example of a minimalist grid layout
