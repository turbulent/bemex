# Grid layout example

BEMex bootstrap comming with a minimalist grid layout.

## LESS/SASS
```

/* Layout container */

.l-container {
    box-sizing: border-box;
    margin: 0 auto;
    width: 100%;
    max-width: 1200px;
    padding: 0 20px;
}

/* Layout grid */
/**
 * Grid
 * Default example of a l-grid component
 **/

.l-grid {
    box-sizing: border-box;
    display: flex;
    flex-wrap: wrap;
    flex-direction: row;

    &--align-center {
        align-items: center;
    }

    &--justify-center {
        justify-content: center;
    }

    &--justify-end {
        justify-content: flex-end;
    }

    &--direction-column {
        flex-direction: column;
    }

    &__item {
        box-sizing: border-box;
        padding: 0 15px;
        flex-grow: 1;

        &--full {
            width: 100%;
        }

        &--three-quarter {
            width: 75%;
        }

        &--two-third {
            width: calc(100%/3 * 2);
        }

        &--half {
            width: 50%;
        }

        &--third {
            width: calc(100%/3);
        }

        &--quarter {
            width: 25%;
        }
    }
}
```

## HTML
```
<div class="l-container">
    <div class="l-grid">

        <div class="l-grid__item l-grid__item--third">
            <div class="c-content">
                <h2 class="c-content__title">Title example</h2>
                <p class="c-content__body">Paragraph example</p>
            </div>
        </div>

        <div class="l-grid__item l-grid__item--third">
            <div class="c-content">
                <h2 class="c-content__title">Title example</h2>
                <p class="c-content__body">Paragraph example</p>
            </div>
        </div>

        <div class="l-grid__item l-grid__item--third">
            <div class="c-content">
                <h2 class="c-content__title">Title example</h2>
                <p class="c-content__body">Paragraph example</p>
            </div>
        </div>

        <div class="l-grid__item l-grid__item--full">
            <div class="c-content">
                <h2 class="c-content__title">Title example</h2>
                <p class="c-content__body">Paragraph example</p>
            </div>
        </div>

        <div class="l-grid__item l-grid__item--third">
            <div class="c-content">
                <h2 class="c-content__title">Title example</h2>
                <p class="c-content__body">Paragraph example</p>
            </div>
        </div>

        <div class="l-grid__item l-grid__item--two-third">
            <div class="c-content">
                <h2 class="c-content__title">Title example</h2>
                <p class="c-content__body">Paragraph example</p>
            </div>
        </div>

        <div class="l-grid__item l-grid__item--quarter">
            <div class="c-content">
                <h2 class="c-content__title">Title example</h2>
                <p class="c-content__body">Paragraph example</p>
            </div>
        </div>

        <div class="l-grid__item l-grid__item--quarter">
            <div class="c-content">
                <h2 class="c-content__title">Title example</h2>
                <p class="c-content__body">Paragraph example</p>
            </div>
        </div>

        <div class="l-grid__item l-grid__item--quarter">
            <div class="c-content">
                <h2 class="c-content__title">Title example</h2>
                <p class="c-content__body">Paragraph example</p>
            </div>
        </div>

        <div class="l-grid__item l-grid__item--quarter">
            <div class="c-content">
                <h2 class="c-content__title">Title example</h2>
                <p class="c-content__body">Paragraph example</p>
            </div>
        </div>
    </div>
</div>
```

## Nested grid

You can also provide nested grid

## HTML
```
<div class="l-container">
    <div class="l-grid">

        <div class="l-grid__item l-grid__item--two-third">
            <div class="l-grid">
                <div class="l-grid__item l-grid__item--quarter">
                    <div class="c-content">
                        <h2 class="c-content__title">Title example</h2>
                        <p class="c-content__body">Paragraph example</p>
                    </div>
                </div>

                <div class="l-grid__item l-grid__item--quarter">
                    <div class="c-content">
                        <h2 class="c-content__title">Title example</h2>
                        <p class="c-content__body">Paragraph example</p>
                    </div>
                </div>

                <div class="l-grid__item l-grid__item--quarter">
                    <div class="c-content">
                        <h2 class="c-content__title">Title example</h2>
                        <p class="c-content__body">Paragraph example</p>
                    </div>
                </div>

                <div class="l-grid__item l-grid__item--quarter">
                    <div class="c-content">
                        <h2 class="c-content__title">Title example</h2>
                        <p class="c-content__body">Paragraph example</p>
                    </div>
                </div>
            </div>
        </div>

        <div class="l-grid__item l-grid__item--third">
            <div class="c-content">
                <h2 class="c-content__title">Title example</h2>
                <p class="c-content__body">Paragraph example</p>
            </div>
        </div>

    </div>
</div>
```
