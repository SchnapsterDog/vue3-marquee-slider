[![Contributors][contributors-shield]][contributors-url]
[![Downloads][downloads-shield]][downloads-url]
[![Issues][issues-shield]][issues-url]
[![MIT License][license-shield]][license-url]
[![LinkedIn][linkedin-shield]][linkedin-url]

<!-- PROJECT LOGO -->
<br />
<div align="center">
  <a href="https://vue-marquee.com" target="_blank">
    <img src="images/logo.png" alt="Logo" width="233" height="93">
  </a>

  <h3 align="center">Vue3 Marquee Slider</h3>

  <p align="center">
    Simple and easy-to-use component for Vue that allows you to create customizable marquees with just a few lines of code
    <br />
    <br />
    <a href="https://vue-marquee.com/" target="_blank"><strong>View Demo</strong></a>
    <br />
    <br />
    <a href="https://vue-marquee.com/guide" target="_blank"><strong>Explore the docs »</strong></a>
    ·
    <a href="https://github.com/schnapsterdog/vue3-marquee-slider/issues target="_blank"">Report Bug</a>
    ·
    <a href="https://github.com/schnapsterdog/vue3-marquee-slider/issues target="_blank"">Request Feature</a>
    ·
    <a href="https://github.com/SchnapsterDog/vue-marquee-slider target="_blank"">Vue2 Version</a>
  </p>
</div>

<!-- ABOUT THE PROJECT -->
## About The Vue3 Marquee Slider

[![Product Name Screen Shot][product-screenshot]](https://vue-marquee.com/)

vue3-marquee-slider is a simple and easy-to-use component for Vue that allows you to create customizable marquees with just a few lines of code. It is a great option if you are looking for a lightweight and easy-to-use marquee component that works out of the box with Vue 3.

The component allows you to create a responsive, customizable, mobile-friendly carousel/slider to display images, text, and custom HTML content. It supports various features such as usage with images, text and cards, setting the width and auto width of the images, setting the speed and space between items, and setting the direction of the sliding items to be reversed.

## Why to use Vue3 Marquee Slider

- 👉 It is easy to use and set up within all vue.js projects.
- 👉 It is responsive and adapts to different screen sizes.
- 👉 It allows for custom styling and customization options.
- 👉 It has a smooth and fluid animation.
- 👉 It can handle large amounts of data and images.
- 👉 It is lightweight and performs well.
- 👉 It is open source and free to use.

<!-- GETTING STARTED -->
## Getting Started

With vue3-marquee-slider, you can easily create scrolling text or images that automatically move across the screen.
You can control the speed, direction, and even pause or resume the marquee with simple props.

### Installation

To use vue3-marquee-slider in your Vue3 project, simply install it with npm or yarn:
* npm
  ```sh
  npm i vue3-marquee-slider@latest
  ```

* yarn
  ```sh
  yarn add vue3-marquee-slider@latest
  ```

### Component Usage Vue3

Sometimes you will want to import the component separately in each individual component.

This allows you to have more control over the component and tailor it specifically for each individual component's needs. Importing the component separately also allows for better organization and separation of concerns in your codebase.

```html
<vue-marquee-slider
  id="marquee-slider"
  :speed="1000"
  :width="50"
>
  <img src="https://app.imgforce.com/images/user/zrC_1622176244_logo-black-120.png" />
  <img src="https://app.imgforce.com/images/user/O1j_1670884991_js-logo.png" />
  <img src="https://app.imgforce.com/images/user/Igx_1670885749_vue-logo.png" />
  <img src="https://app.imgforce.com/images/user/TPs_1670885858_react-logo.png" />
  <img src="https://app.imgforce.com/images/user/jY4_1670885309_angular-logo.png" />
</vue-marquee-slider>
```

```js
import { VueMarqueeSlider } from 'vue3-marquee-slider';
import '@/node_modules/vue3-marquee-slider/dist/style.css'

export default {
  components: {
    VueMarqueeSlider
  }
}
```

or inside script tag with setup

```js
import { VueMarqueeSlider } from 'vue3-marquee-slider';
import '@/node_modules/vue3-marquee-slider/dist/style.css'
```

With loop:

```html
<vue-marquee-slider
  id="marquee-slider-loop"
  :speed="1000"
  :width="50"
>
  <img
    v-for="(image, index) in images"
    :key="index"
    :src="image.url"
  />
</vue-marquee-slider>
```

```js
export default {
  data() {
    return {
      images: [
        { url: 'https://app.imgforce.com/images/user/zrC_1622176244_logo-black-120.png' },
        { url: 'https://app.imgforce.com/images/user/O1j_1670884991_js-logo.png' },
        { url: 'https://app.imgforce.com/images/user/Igx_1670885749_vue-logo.png' },
        { url: 'https://app.imgforce.com/images/user/TPs_1670885858_react-logo.png' },
        { url: 'https://app.imgforce.com/images/user/jY4_1670885309_angular-logo.png' }
      ]
    }
  }
}
```

### Available props

| Name | Type | Default | Description |
|--|--|--|--|
|**autoWidth**|`Boolean`|`false`|The prop autoWidth of the vue3-marquee-slider component allows the width of each item in the slider to be automatically calculated based on the content of the item. This can be useful in cases where the items in the slider have varying lengths of text or other content, and you want to ensure that each item is displayed properly without being truncated or overlapping with other items. By setting this prop to true, the vue3-marquee-slider component will automatically adjust the width of each item to fit its content, ensuring that the items are displayed properly and are easy to read.
|**id**|`String`|`id`|The prop id is required in the vue3-marquee-slider component in order to uniquely identify the element on the page. This is necessary for proper functioning of the component, as it allows for proper event handling and state management.
|**paused**|`Boolean`|`false`|The paused prop is a boolean value that determines whether or not the marquee slider is paused. If paused is set to true, the marquee will not animate and will remain stationary. If paused is set to false, the marquee will animate according to the specified settings.
|**repeat**|`Number`|`10`|The repeat prop is used to specify the number of times the marquee items should repeat before stopping. This prop can take an integer value.
|**reverse**|`Boolean`|`false`|The reverse prop in vue3-marquee-slider is used to determine whether the marquee should move in a reverse direction. This can be useful for creating a backwards scrolling effect or for reversing the direction of the marquee when the user navigates to a different section of the website. This prop can be set to either true or false depending on the desired behavior of the marquee.
|**space**|`Number`|`200`|To add space between items in a vue3-marquee-slider, you can use the space prop. The space prop allows you to specify the amount of space in pixels between each item in the slider.
|**speed**|`Number`|`1500`|The speed prop in vue3-marquee-slider allows users to set the speed at which the content in the slider will move. This can be set in miliseconds, allowing for precise control over the speed. The default value is 1500 ms, but this can be increased or decreased as needed.
|**width**|`Number`|`100`|The width prop of each item in the vue3-marquee-slider determines the width of the individual items within the slider. This prop can be useful for creating a consistent look and feel for the items in the slider, and for ensuring that they all fit within the designated space of the slider.


## Examples

Visit the following <a href="https://vue-marquee.com/examples">link</a>. There you will find various examples of how to use the vue3-marquee-slider component in different ways, including different options for customizing the appearance and behavior of the slider.

These examples can help you understand the different features and options available with the vue3-marquee-slider component, and how you can use them to create your own custom marquee sliders.

### 👉 Basic sample with images

```html
<vue-marquee-slider
  id="marquee-slider"
  :speed="15000"
>
  <img src="https://app.imgforce.com/images/user/zrC_1622176244_logo-black-120.png" />
  <img src="https://app.imgforce.com/images/user/O1j_1670884991_js-logo.png" />
  <img src="https://app.imgforce.com/images/user/Igx_1670885749_vue-logo.png" />
  <img src="https://app.imgforce.com/images/user/TPs_1670885858_react-logo.png" />
  <img src="https://app.imgforce.com/images/user/jY4_1670885309_angular-logo.png" />
</vue-marquee-slider>
```

### 👉 With static width of the images

```html
<vue-marquee-slider
  id="marquee-slider-width"
  :speed="10000"
  :width="50"
>
  <img src="https://app.imgforce.com/images/user/zrC_1622176244_logo-black-120.png" />
  <img src="https://app.imgforce.com/images/user/O1j_1670884991_js-logo.png" />
  <img src="https://app.imgforce.com/images/user/Igx_1670885749_vue-logo.png" />
  <img src="https://app.imgforce.com/images/user/TPs_1670885858_react-logo.png" />
  <img src="https://app.imgforce.com/images/user/jY4_1670885309_angular-logo.png" />
</vue-marquee-slider>
```

### 👉 Speed & Space between items

```html
<vue-marquee-slider
  id="marquee-slider-space"
  :space="50"
  :speed="10000"
  :width="150"
>
  <img src="https://app.imgforce.com/images/user/zrC_1622176244_logo-black-120.png" />
  <img src="https://app.imgforce.com/images/user/O1j_1670884991_js-logo.png" />
  <img src="https://app.imgforce.com/images/user/Igx_1670885749_vue-logo.png" />
  <img src="https://app.imgforce.com/images/user/TPs_1670885858_react-logo.png" />
  <img src="https://app.imgforce.com/images/user/jY4_1670885309_angular-logo.png" />
</vue-marquee-slider>
```

### 👉 Basic usage with text

```html
<vue-marquee-slider
  id="marquee-slider-text"
  :space="150"
  :speed="10000"
  :width="200"
>
  <span>Schnapsterdog</span>
  <span>Vue.js</span>
  <span>Nuxt.js</span>
  <span>vue3-marquee-slider</span>
</vue-marquee-slider>
```

### 👉 Cards inside vue3-marquee-slider

```html
<vue-marquee-slider
  id="marquee-slider-cards"
  :space="50"
  :speed="12000"
  :width="420"
>
  <div>Some Cards</div>
  <div>Some Cards</div>
  <div>Some Cards</div>
</vue-marquee-slider>
```

### 👉 Reversed direction

```html
<vue-marquee-slider
  id="marquee-slider-reverse"
  :space="50"
  :speed="10000"
  :width="150"
  reverse
>
  <img src="https://app.imgforce.com/images/user/zrC_1622176244_logo-black-120.png" />
  <img src="https://app.imgforce.com/images/user/O1j_1670884991_js-logo.png" />
  <img src="https://app.imgforce.com/images/user/Igx_1670885749_vue-logo.png" />
  <img src="https://app.imgforce.com/images/user/TPs_1670885858_react-logo.png" />
  <img src="https://app.imgforce.com/images/user/jY4_1670885309_angular-logo.png" />
</vue-marquee-slider>
```

## Vue2 Version

Version for Vue 2: [https://github.com/schnapsterdog/vue-marquee-slider](https://github.com/schnapsterdog/vue-marquee-slider)


<!-- CONTRIBUTING -->
## Contributing

Contributions are what make the open source community such an amazing place to learn, inspire, and create. Any contributions you make are **greatly appreciated**.

If you have a suggestion that would make this better, please fork the repo and create a pull request. You can also simply open an issue with the tag "enhancement".
Don't forget to give the project a star! Thanks again!

1. Fork the Project
2. Create your Feature Branch (`git checkout -b feature/AmazingFeature`)
3. Commit your Changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the Branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request


<!-- LICENSE -->
## License

Distributed under the MIT License. See `LICENSE.txt` for more information.

<!-- CONTACT -->
## Contact

Oliver Trajceski - [LinkedIn](https://mk.linkedin.com/in/oliver-trajceski-8a28b070) - oliver@akrinum.com

Project Link: [https://github.com/schnapsterdog/vue3-marquee-slider](https://github.com/schnapsterdog/vue3-marquee-slider)


<!-- ACKNOWLEDGMENTS -->
## Acknowledgments

Use this space to list resources you find helpful and would like to give credit to. I've included a few of my favorites to kick things off!

* [Choose an Open Source License](https://choosealicense.com)
* [Img Shields](https://shields.io)
* [GitHub Pages](https://pages.github.com)

<!-- MARKDOWN LINKS & IMAGES -->
<!-- https://www.markdownguide.org/basic-syntax/#reference-style-links -->
[contributors-shield]: https://img.shields.io/github/contributors/schnapsterdog/vue3-marquee-slider.svg?style=for-the-badge
[contributors-url]: https://github.com/schnapsterdog/vue3-marquee-slider/graphs/contributors
[downloads-shield]: https://img.shields.io/npm/dw/vue3-marquee-slider.svg?style=for-the-badge
[downloads-url]: https://www.npmjs.com/package/vue3-marquee-slider
[stars-shield]: https://img.shields.io/github/stars/vue3-marquee-slider.svg?style=for-the-badge
[stars-url]: https://github.com/schnapsterdog/vue3-marquee-slider/stargazers
[issues-shield]: https://img.shields.io/github/issues/schnapsterdog/vue3-marquee-slider.svg?style=for-the-badge
[issues-url]: https://github.com/schnapsterdog/vue3-marquee-slider/issues
[license-shield]: https://img.shields.io/github/license/schnapsterdog/vue3-marquee-slider.svg?style=for-the-badge
[license-url]: https://github.com/schnapsterdog/vue3-marquee-slider/blob/master/LICENSE.txt
[linkedin-shield]: https://img.shields.io/badge/-LinkedIn-black.svg?style=for-the-badge&logo=linkedin&colorB=555
[linkedin-url]: https://mk.linkedin.com/in/oliver-trajceski-8a28b070
[product-screenshot]: https://app.imgforce.com/images/user/RdQ_1670897377_vue-marquee-seo.png
[Vue.js]: https://img.shields.io/badge/Vue.js-35495E?style=for-the-badge&logo=vuedotjs&logoColor=4FC08D
[Vue-url]: https://vuejs.org/