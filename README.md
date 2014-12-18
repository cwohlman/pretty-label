pretty-label
============

A css/html only component for prettier labels. The goal for this project is to perfect the css needed for a meteor package to replace [label-better](http://www.thepetedesign.com/demos/label_better_demo.html). Right now this component is nothing but some specs.

Specs
------------
1. Css only - the animations/styling should be entirely triggered by adding/removing an 'active' class.
2. Minimal html - the less added markup, the better.
3. Cross browser support - should support all major browsers and ios/android
4. Should target bootstrap - the default styles should work out of the box for bootstrap input elements.
5. Label markup should be self-contained and should prepend or wrap input markup, eg:

  ```html
  <!-- nothing out here -->
  <div class="form-group">
    <div class="pretty-label-wrapper"> <!-- we can wrap the input with our markup -->
      <label class="pretty-label">Some Label</label> <!-- and/or insert our markup before the input -->
      <input class="form-control" type="text">
      <!-- nothing here -->
    </div>
    <!-- should be self contained, so nothing here -->
  </div>
  <!-- nothing out here -->
  ```
  
6. Shouldn't depend on any bootstrap styling - the styles/markup should work with pretty much any input (it's ok if weird stuff like absolutly positioned inputs doesn't work, we don't want a hack-fits-all approach, just a one-size-fits-most approach).
An example of something that should work out of the box is bootstrap inline forms which have different layout/display properties than a horizontal or vanilla form. 
7. Animation styles should be seperate from, and not dependant on presentation styles, including any height/margin adjustements needed for differently styled inputs, eg:
  ```css
  /* The developer shouldn't modify these styles unless he wants to change the transition */
    transition: 0.25s;
    opacity: 0;
  }
  .pretty-label.active {
    opacity: 1;
  }
  
  /* These styles should work for bootstrap out of the box,
  but the developer might need to modify them depending on the margin/padding of his input elements.
  Font and background styles could also go here. */
  .pretty-label {
    top: 0;
  }
  
  .pretty-label.active {
    top: -10px;
  }
  ```
