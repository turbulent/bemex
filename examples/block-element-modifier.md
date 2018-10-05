# BEMex Example
A table with a header and cell highlighting

## LESS/SASS
```
.c-table{
    display: flex;
    flex-direction: column;

    &__row{
        display: flex;
        flex-flow: row no-wrap;
        &--heading{
            border-bottom: solid 4px black;
        }
    }

    &__cell{
        flex: 1 1 10%;

        &--highlighted{
            background: yellow;
        }

        &--locked{
            background: grey;
            cursor: not-allowed;
        }

        &--wide{
            flex-basis: 50%;
        }

    }
}
```

## HTML
```
<div class="c-table">
    <div class="c-table__row c-table__row--heading">
        <div class="c-table__cell">
            Memory Name
        </div>
        <div class="c-table__cell c-table__cell--wide">
            Description
        </div>
        <div class="c-table__cell">
            Parental Dissapointment Level
        </div>
    </div>
    <div class="c-table__row">
        <div class="c-table__cell">
            School Dance
        </div>
        <div class="c-table__cell c-table__cell--wide">
            Asking a teacher to dance because no-one else would go with you
        </div>
        <div class="c-table__cell c-table__cell--locked">
            2.3
        </div>
    </div>
    <div class="c-table__row">
        <div class="c-table__cell">
            Career Choice
        </div>
        <div class="c-table__cell c-table__cell--wide">
            Deciding to learn Adobe Cold Fusion
        </div>
        <div class="c-table__cell">
            1.1
        </div>
    </div>
</div>
```