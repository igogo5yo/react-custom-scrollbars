react-customized-scrollbars
=========================


[![npm](https://img.shields.io/badge/npm-react--custom--scrollbars-brightgreen.svg?style=flat-square)]()
[![npm version](https://img.shields.io/npm/v/react-customized-scrollbars.svg?style=flat-square)](https://www.npmjs.com/package/react-customized-scrollbars)
[![npm downloads](https://img.shields.io/npm/dm/react-customized-scrollbars.svg?style=flat-square)](https://www.npmjs.com/package/react-customized-scrollbars)


#### Forked from: [malte-wessel/react-custom-scrollbars](https://github.com/malte-wessel/react-custom-scrollbars)
Forked to make better support of react-virtualized and fix issue with hidden scrollbar on macOS ([see `innerHeight` prop](https://github.com/igogo5yo/react-customized-scrollbars/tree/master/docs/API.md#innerHeight)).

* frictionless native browser scrolling
* native scrollbars for mobile devices
* [fully customizable](https://github.com/igogo5yo/react-customized-scrollbars/blob/master/docs/customization.md)
* [auto hide](https://github.com/igogo5yo/react-customized-scrollbars/blob/master/docs/usage.md#auto-hide)
* [auto height](https://github.com/igogo5yo/react-customized-scrollbars/blob/master/docs/usage.md#auto-height)
* [universal](https://github.com/igogo5yo/react-customized-scrollbars/blob/master/docs/usage.md#universal-rendering) (runs on client & server)
* `requestAnimationFrame` for 60fps
* no extra stylesheets
* well tested, 100% code coverage

**[Demos](http://malte-wessel.github.io/react-customized-scrollbars/) · [Documentation](https://github.com/igogo5yo/react-customized-scrollbars/tree/master/docs)**

## Installation
```bash
npm install react-customized-scrollbars --save
```

This assumes that you’re using [npm](http://npmjs.com/) package manager with a module bundler like [Webpack](http://webpack.github.io) or [Browserify](http://browserify.org/) to consume [CommonJS modules](http://webpack.github.io/docs/commonjs.html).

If you don’t yet use [npm](http://npmjs.com/) or a modern module bundler, and would rather prefer a single-file [UMD](https://github.com/umdjs/umd) build that makes `ReactCustomScrollbars` available as a global object, you can grab a pre-built version from [unpkg](https://unpkg.com/react-customized-scrollbars@3.0.1/dist/react-customized-scrollbars.js). We *don’t* recommend this approach for any serious application, as most of the libraries complementary to `react-customized-scrollbars` are only available on [npm](http://npmjs.com/).

## Usage

This is the minimal configuration. [Check out the Documentation for advanced usage](https://github.com/igogo5yo/react-customized-scrollbars/tree/master/docs).

```javascript
import { Scrollbars } from 'react-customized-scrollbars';

class App extends Component {
  render() {
    return (
      <Scrollbars style={{ width: 500, height: 300 }}>
        <p>Some great content...</p>
      </Scrollbars>
    );
  }
}
```

The `<Scrollbars>` component is completely customizable. Check out the following code:

```javascript
import { Scrollbars } from 'react-customized-scrollbars';

class CustomScrollbars extends Component {
  render() {
    return (
      <Scrollbars
        onScroll={this.handleScroll}
        onScrollFrame={this.handleScrollFrame}
        onScrollStart={this.handleScrollStart}
        onScrollStop={this.handleScrollStop}
        onUpdate={this.handleUpdate}
        renderView={this.renderView}
        renderTrackHorizontal={this.renderTrackHorizontal}
        renderTrackVertical={this.renderTrackVertical}
        renderThumbHorizontal={this.renderThumbHorizontal}
        renderThumbVertical={this.renderThumbVertical}
        autoHide
        autoHideTimeout={1000}
        autoHideDuration={200}
        autoHeight
        autoHeightMin={0}
        autoHeightMax={200}
        thumbMinSize={30}
        universal={true}
        {...this.props}>
    );
  }
}
```

All properties are documented in the [API docs](https://github.com/igogo5yo/react-customized-scrollbars/blob/master/docs/API.md)

## Examples

Run the simple example:
```bash
# Make sure that you've installed the dependencies
npm install
# Move to example directory
cd react-customized-scrollbars/examples/simple
npm install
npm start
```

## Tests
```bash
# Make sure that you've installed the dependencies
npm install
# Run tests
npm test
```

### Code Coverage
```bash
# Run code coverage. Results can be found in `./coverage`
npm run test:cov
```


## License

MIT
