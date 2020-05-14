# Boiled Page image component

Image SCSS component for Boiled Page frontend framework. It is intended to place, format and and align images.

## Install

Place `_image.scss` file to `/assets/css/components` directory, and add its path to components block in `assets/css/app.scss` file.

## Usage

### Classes

Class name | Description | Example
---------- | ----------- | -------
`image` | Applies an image. | `<div class="image"></div>`
`image--left` | Sets image left aligned. | `<div class="image image--left"></div>`
`image--right` | Sets image right aligned. | `<div class="image image--right"></div>`
`image--center` | Sets image center aligned. | `<div class="image image--right"></div>`
`image--fit` | Sets image width to fit parent element. | `<div class="image image--fit"></div>`

### Examples

#### Example 1

The following example shows a fitted image.

```html
<div class="image image--fit">
  <img src="https://picsum.photos/800/400" alt="Sample image" />
</div>
```

#### Example 2

The following example shows an image floats to the left in a text.

```html
<div class="image image--left">
  <img src="https://picsum.photos/400/300" alt="Sample image" />
</div>
<p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. In nec ex quam. Sed maximus maximus arcu, at tempor quam accumsan eleifend. Ut dictum mattis est, id porta velit tempus sit amet. Donec efficitur eu mauris nec cursus. Phasellus a ligula sit amet nibh egestas varius. Aenean malesuada turpis sapien, vel pellentesque dui viverra maximus. Vestibulum convallis erat ex, non varius justo bibendum sit amet. Nulla malesuada enim sed neque interdum, id laoreet libero dignissim. Maecenas fermentum tincidunt urna. Nullam volutpat ex a mi sollicitudin gravida a ac ipsum.</p>
<p>Quisque egestas gravida nisi, in cursus sem sagittis eu. Vestibulum lacinia ex mauris. Vivamus sit amet ante vel sem egestas pharetra non sed diam. Vivamus nec sapien at turpis semper vehicula a et purus. Ut nec magna arcu. Aenean elementum ex a risus placerat, sit amet tincidunt turpis pulvinar. Aliquam erat volutpat. Suspendisse nisl massa, sagittis sed consectetur vel, tempus vel odio. Vestibulum dictum odio sem, eu efficitur velit ultricies id. Aenean leo metus, egestas a sapien quis, scelerisque venenatis nisl. Donec tincidunt quam ac justo tincidunt pharetra. Nam vehicula augue a tortor condimentum, ut faucibus urna egestas.</p>

```

### Extension ideas

#### Cover image

```scss
// Image component variables
$image-cover-transition: 200ms ease;

/* Image component extensions */
div.image {

  // Image cover effect
  &.image--cover {
    position: relative;

    &:before {
      background-color: rgba($bg-color, 0);
      content: '';
      display: block;
      height: 100%;
      left: 0;
      position: absolute;
      top: 0;
      transition: background-color $image-cover-transition;
      width: 100%;
    }

    body.no-touch &:hover:before {
      background-color: rgba($bg-color,0.3);
    }
  }
}
```

#### Circle image

```scss
/* Image component extensions */
div.image {

  // Circle image
  &.image--circle {

    img, canvas {
      border-radius: 50%;
    }
  }
}
```

#### Lazy image

Use this extension idea for lazy image script.

```scss
/* Image component extensions */
div.image {

  // Lazy image
  &.image--lazy {
    overflow: hidden;

    img {
      filter: blur(40px);
      transition: filter 1.5s;

      &.is-loaded {
        filter: none;
      }
    }
  }
}
```
