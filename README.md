# Jekyll Ideal Image Slider Include

Add image sliders to Jekyll with [Ideal Image Slider](https://github.com/Codeinwp/Ideal-Image-Slider-JS). HTML include version. No plugin necessary. Fully compatible with Github Pages.

View a [live demo running on Github Pages](https://jekylltools.github.io/jekyll-ideal-image-slider-include/examples/). The code and configuration for the demo is in the [gh-pages branch](https://github.com/jekylltools/jekyll-ideal-image-slider-include/tree/gh-pages).

## Installation

1. Add the [Ideal Image Slider](https://github.com/Codeinwp/Ideal-Image-Slider-JS) files to your site.

2. Add `_data/sliders.yml` to your site.

3. Add the `_includes` folder and all contents to your site.

4. Include `slider_styles.html` in your theme head. Change the paths in this file to point to wherever you put the Ideal Image Slider files.

  `{% include slider_styles.html %}`

5. Include `slider_scripts.html` in your theme just before the `</body>` tag. Change the paths in this file to point to wherever you put the Ideal Image Slider files.

  `{% include slider_scripts.html %}`

## Usage

Create a slider by adding data to `_data/sliders.yml`, adding a selector to the `image_sliders` front matter variable and including `slider.html` while passing in the slider selector. View the code in the [gh-pages branch](https://github.com/jekylltools/jekyll-ideal-image-slider-include/tree/gh-pages) for a live example.

### 1. Create slider data

Create a slider by adding data to `_data/sliders.yml`. The format for slider data is shown below. See the [Ideal Image Slider settings](https://github.com/Codeinwp/Ideal-Image-Slider-JS#settings) for a description of each setting. Note that `captions` is boolean (`true/false`) and `classes` is unsupported.

```
- selector:
  captions:
  images:
    - data-src:
      data-src-2x:
      src:
      title:
      alt:
      href:
  settings:
    height:
    initialHeight:
    maxHeight:
    interval:
    transitionDuration:
    effect:
    disableNav:
    keyboardNav:
    previousNavSelector:
    nextNavSelector:
```

Here is an example slider, with a few images, alt text and captions:

```
- selector: example_slider
  captions: true
  images:
    - src: /img/1.jpg
      alt: image one
    - src: /img/2.jpg
      alt: image two
    - src: /img/3.jpg
      alt: image three
  settings:
    height: "'auto'"
    effect: "'fade'"
```

### 2. Add `image_sliders` front matter variable

Using the `image_sliders` variable to add sliders to the front matter of a page or layout. This tells Jekyll to load the correct slider scripts and styles on that page or layout:

```
image_sliders:
  - example_slider
```

### 3. Include `slider.html`

Include `slider.html` where you want the slider to appear within the page or layout. Pass the slider selector into the include. This tells Jekyll to search `_data/sliders.yml` for slider data where the selector equals `example_slider` and use that data to create an image slider:

```
{% include slider.html selector="example_slider" %}
```

## Support

[Open an issue](https://github.com/jekylltools/jekyll-ideal-image-slider-include/issues) if you have any problems, questions or suggestions for improvement.
