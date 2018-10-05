# Helper example

Basic content component with helper.

## LESS/SASS
```
/* Content component example */

.c-content {

  &__title {
    text-transform: uppercase;
  }
}

/* Text helpers example */

.h-text {
  &--lowercase {
    text-transform: lowercase;
  }

  &--uppercase {
    text-tranform: uppercase;
  }
}
```

## HTML
```
<div class="c-content">
  <h2 class="c-content__title h-text--lowercase">Title which is lowercase</h2>
  <p class="c-content__body">Paragraph content with some words in
    <span class="h-text--uppercase">uppercase</span>
  </p>
</div>
```