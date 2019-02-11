<h1 align="center">wc 🌐 stories</h1>

<p align="center">
Instagram/Whatsapp stories like built on Web Components and Web Animations API.
</p>

> ⚡ **Disclaimer:** this component is not available on npm yet. I'm a little bussy. If you want to help with it, your'e welcome to make a PR. 😉

<br />

<p align="center">
  <img height="320" src="https://i.imgur.com/IOnigkm.gif">
</p>

## Browser support

| [<img src="https://raw.githubusercontent.com/alrra/browser-logos/master/src/edge/edge_48x48.png" alt="IE / Edge" width="24px" height="24px" />](http://godban.github.io/browsers-support-badges/)</br>IE / Edge | [<img src="https://raw.githubusercontent.com/alrra/browser-logos/master/src/firefox/firefox_48x48.png" alt="Firefox" width="24px" height="24px" />](http://godban.github.io/browsers-support-badges/)</br>Firefox | [<img src="https://raw.githubusercontent.com/alrra/browser-logos/master/src/chrome/chrome_48x48.png" alt="Chrome" width="24px" height="24px" />](http://godban.github.io/browsers-support-badges/)</br>Chrome | [<img src="https://raw.githubusercontent.com/alrra/browser-logos/master/src/safari/safari_48x48.png" alt="Safari" width="24px" height="24px" />](http://godban.github.io/browsers-support-badges/)</br>Safari | [<img src="https://raw.githubusercontent.com/alrra/browser-logos/master/src/opera/opera_48x48.png" alt="Opera" width="24px" height="24px" />](http://godban.github.io/browsers-support-badges/)</br>Opera |
| --------- | --------- | --------- | --------- | --------- |
| IE11, Edge| last 10 versions| last 10 versions| last 10 versions| last 10 versions

---

## 💡 What's the prupose of it?

Just fun 🙂. I love learn and code, so, this every time I have free time, pick some crazy idea or got inspiration from another projects and make it. 😋

## 🦄 Inspiration

When I saw the project of Mohit, [react-insta-stories](https://github.com/mohitk05/react-insta-stories), immediately wanted to know how complicated it would be to do the same thing using **Web Components**. So, I built this. Thanks, Mohit! 😃 

## ⚙️ How it works?

There are three components working together:

- `<wc-stories-story>`: this component shows a image. The maximun size of an image is the containers viewport.
- `<wc-stories-progress`>: this component shows the progress bar at top the the container. It uses **Web Animations API** to run it. If we change of image (clicking on left/right), the previous animation is cancelled.
- `<wc-stories>`: this is the main component. This one harbor the two components above. Here is the logic for control which image should be revealed, what happen if the user
clicks on left or right side, etc.

## 🚀 How to run?

After install depenencies, you just need to run `yarn start`. Once the server was started, go to [localhost:4444](http://127.0.0.1:4444) and see it in action.

## 🛠️ How to build?

Execute the `yarn build` command to compile the source code and get the ES5 equivalent. Compiled code will be available on `dist/` folder.

## 🙋 How to use it in my web/app?

First, we need to add the needed polyfills:

- `@webcomponents/webcomponentsjs/custom-elements-es5-adapter.js`
- `@webcomponents/webcomponentsjs/webcomponents-loader.js`.
- `web-animations-js/web-animations.min.js`

### Web Components/Vanilla JavaScript
If you're using Web Components or vanilla JavaScript, just put the `wc-stories` tag inside your HTML and pass it the array of images:

```html
<wc-stories
  width="320"
  height="480"
>
</wc-stories>

<script>
// On document/window loaded
const wcStories = document.querySelector('wc-stories')
wcStories.images = [
  '<path/to/image>',
  '<path/to/image>',
  '<path/to/image>',
  ...
]
</script>
```

Or you can pass the images array as inline:

**Note** that the string is bounded with single quotes (`'`).

```html
<wc-stories
  width="320"
  height="480"
  images='[
    "/img/01.jpg",
    "/img/02.jpg",
    "/img/03.jpg",
    "/img/04.jpg",
    "/img/05.jpg"
  ]'
>
</wc-stories>
```

### React

If you're using React, use the component as is. Instead of passing raw values you can use `state` to
store the component configuration:

```jsx
render() {
  return (
    <wc-stories
      width={this.state.height}
      height={this.state.width}
      images={this.state.images}
    >
    </wc-stories>
  )
}
```

### Angular

If you're using Angular, put the component inside your template. Like React, you can put the configuration inside the controller instead passing raw values:

```html
<wc-stories
  [width]="storiesWidth"
  [height]="storiesHeight"
  [images]="imageList"
>
</wc-stories>
```

###  Vue

If you're using Vue, put the component inside your template. Like React, you can put the configuration inside the controller instead passing raw values:

```html
<wc-stories
  :width="storiesWidth"
  :height="storiesHeigh}"
  :images="imageList"
>
</wc-stories>
```

## 🚧 Roadmap

- [x] Implement Typescript
- [x] Implement PostCSS.
- [x] Make builds with Webpack.
- [x] Compile down to ES5.
- [x] Control animation's flow
- [ ] Improve suite case.
- [ ] Add mobile swipe support.
- [ ] Add more transition effects.
- [ ] Add demo page.
- [ ] Publish the package to npm.

## 🙌 Contribute

If you found this project interesting, I'm glade to
receive updates, new features or fixes 🙂. Just
fork the project, create your branch, make your changes
and send your Pull Request! 😃

## 📖 API

- `images: []string`: array of images url.
- `startAt: number`: initial image index to show.
- `duration: number`: duración de las imágenes.
- `height: number`: height of the component.
- `width: number`: width of the component.
- `withShadow: boolean`: enable or disable drop shadow.
