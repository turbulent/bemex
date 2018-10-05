# Nested layouts examples

You can create complex structure with nested layouts.

In our example we are going to create a full-width block with background (`l-section`)
in which we have to put some content (`c-content`) component wrap inside a container (`l-container`).

## LESS/SASS
```
/* Layout section */

.l-section {
  padding: 50px 0;
  background: #313131;
}

/* Layout container */

.l-container {
  margin: 0 auto;
  width: 100%;
  max-width: 1200px;
  padding: 0 20px;

  @media screen and (min-width: @tabletWidth) {
    padding: 0 40px;
  }

  @media screen and (min-width: @desktopWidth) {
    padding: 0 60px;
  }
}
```

## HTML
```
<div class="l-section">
  <div class="l-container">
    <div class="c-content">
      <h2 class="c-content__title">Title example</h2>
      <p class="c-content__body">Paragraph example</p>
    </div>
  </div>
</div>
```