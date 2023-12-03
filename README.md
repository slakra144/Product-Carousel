# Product-Carousel

## HTML structure:

### 1. container
create a container div for entire carousel
```html
   <div class="slider">
     <!-- Carousel items will go here -->
   </div>
```
### 2. carousel Items
Inside the main container, add individaul items for each product
```html
 <div class="product">
     <div class="image">
          <img src="1.jpg" alt="">
     </div>
     <div class="information">
         <div class="title">Bose Headphones</div>
         <div class="price">$200</div>
      </div>
 </div>
```

## CSS Styling:

### 1. Container styling
Style the container to define its width, display, and overflow to hide overflowed content.

### 2. carousel Items
style the item width, margin, transition.

#### a) Item Image
style the width & height of Image

#### b) Item Information & Title & Price
styling the font regarding the details about the product

## JavaScript Functionality:

### 1. Variables:
Declare variables to keep track of the current slide and total number of slides.

```js
 const products = document.querySelectorAll(".slider .product");
```

### 2. Function to Move Carousel:
Create a function to move the carousel to the next or previous slide.
```js
 function left() {
  if (counter == 0) {
    counter = products.length / 3 - 1;
  } else {
    counter--;
  }

  scroll();
}

function right() {
  if (counter == products.length / 3 - 1) {
    counter = 0;
  } else {
    counter++;
  }
  scroll();
}

function scroll() {
  products.forEach(function (item) {
    item.style.transform = `translateX(-${counter * 1250}px)`;
  });
}
```

### 3. Function for auto-Transistion of Carousel:
Create a function to automatically transition to new items
```js
setInterval(function () {
  right();
}, 4000);
```
