# Advenced-Grid-layout
Grid that covers most of needed usecases.

# How to use

```css
// Set grid variables
$heights: '' 80px, 'small' 50px; // ('' Npx) is required list element as default state
$column-max-height: 3;
$columns-max: 4;
$section-columns-max: 3;
$fixed-left-max: 2;
$fixed-right-max: 2;
$border-width: 1px;

$sizes-list:
  xs 0 580px,
  sm 580px 768px,
  md 768px 992px,
  lg 992px 1200px,
  xl 1200px 100000px;

// Import scss script with all predefinitions
@import 'src/advenced-grid.scss';

// Describe grid view
body {
  background-color: #f2f2f2;
}
@include cell-style(grey, ('active' lime, 'error' red)) {
  background-color: white;
  text-align: center;
  font-family: monospace;
  color: lightgrey;
  display: flex;
  justify-content: center;
  align-items: center;
  
  &.active {
    color: lime;
  }
  &.error {
    color: red;
  }
}

```

Some HTML:
```html
<div class="section-1x">
  <div class="grid-2x-f:0:1 small">
    <div class="cell-1x xs:sm-2x">1x1</div>
    <div class="cell-1x xs:sm-hide">2x1</div>
    <div class="cell-1x height-3">fixed</div>
    
    <div class="cell-1x xs:sm-2x">1x2</div>
    <div class="cell-1x xs:sm-hide">2x2</div>
    <div class="cell-1x xs:sm-2x">1x3</div>
    <div class="cell-1x xs:sm-hide">2x3</div>
  </div>
</div>
<div class="section-2x xs:sm-1x">
  <div class="grid-2x-f:0:2">
    <div class="cell-1x">1x1</div>
    <div class="cell-1x">2x1</div>
    <div class="cell-1x">fixed</div>
    <div class="cell-1x">fixed</div>
  </div>
  <div class="grid-2x-f:1:0">
    <div class="cell-1x">fixed</div>
    <div class="cell-1x">1x1</div>
    <div class="cell-1x">2x1</div>
  </div>
</div>
 ...
```

## Screenshot from CodePen
![Screenshot](https://i.snag.gy/yIHC4q.jpg)

[CodePen](https://codepen.io/anon/pen/KRgbgw?editors=1100)

# Performance

It compiles very slow, so recommendation to create a script, precompile and use it precompiled. For 12x grid it may take 15 sec to get css
