# tc-angular-chartjs

> AngularJS directives for [Chart.js](http://www.chartjs.org/)

[![Build Status](https://travis-ci.org/carlcraig/tc-angular-chartjs.svg)](https://travis-ci.org/carlcraig/tc-angular-chartjs)

## Installation

Ensure you have [installed Chart.js](http://www.chartjs.org/docs/#getting-started-installation)

#### npm

```bash
npm install tc-angular-chartjs --save
```

#### bower

Bower support has been dropped but you can still use tc-angular-chartjs with Bower using [bower-npm-resolver](https://www.npmjs.com/package/bower-npm-resolver).

#### download

You can download the source archive from the github [releases](https://github.com/carlcraig/tc-angular-chartjs/releases) page.

Just include `dist/tc-angular-chartjs.js` into your project.

## Basic Usage

Add `tc.chartjs` to your modules dependencies e.g.

```javascript
angular.module( 'app', ['tc.chartjs']);
```

You will then have access to the following directives:
- tc-chartjs
- tc-chartjs-line
- tc-chartjs-bar
- tc-chartjs-radar
- tc-chartjs-polararea
- tc-chartjs-pie
- tc-chartjs-doughnut

Just place one of these directives on a `canvas` element to create a Chart.js chart.

You will also want to give the chart some `data` and `options`. These can be provided via the `chart-options` and `chart-data` attributes.

You can also handle chart clicks via the `chart-click` attribute.

Example Pie Chart

```html
<canvas
  tc-chartjs-pie
  chart-data="myData"
  chart-options="myOptions"
  chart-click="onChartClick(event)"
  width="350"
  height="350"
></canvas>
```
```javascript
$scope.myData = {
  // Chart.js data structure goes here
  // e.g. Pie Chart Data Structure http://www.chartjs.org/docs/#doughnut-pie-chart-data-structure
};

$scope.myOptions =  {
  // Chart.js options go here
  // e.g. Pie Chart Options http://www.chartjs.org/docs/#doughnut-pie-chart-chart-options
};

$scope.onChartClick = function (event) {
  console.log(event);
};

```

## Using the `tc-chartjs` directive

When using the `tc-chartjs` directive you will need to add an additional attribute to
say which type of chart should be created.

Just attach a `chart-type=""` attribute to the canvas element.

```html
<canvas
  tc-chartjs
  chart-type="doughnut"
  chart-data="myData"
  chart-options="myOptions"
  width="350"
  height="350"
></canvas>
```

Available Types:

- line
- bar
- radar
- polararea
- pie
- doughnut

Passing another value to chart-type than the above will try to create a chart of
that type, which is useful if you have extended Chart.js with custom chart types,
e.g. through plugins.

## Developing

This library is built using `gulp` so ensure you have it installed.

To build the `dist` files run the following:

```bash
npm run build
```

To run the tests:

```bash
npm test
```

To watch files and rebuild `dist` when changes are made:

```bash
npm start
```

## Contributing

- [Open a Pull Request (PR)](https://github.com/carlcraig/tc-angular-chartjs/pull/new/master)
- Make sure your PR is on a new branch you created from the latest version of master branch
- Please do not open a PR from your master branch
- Open a PR even if your code is incomplete to start a discussion and to collect feedback
- Please make sure all unit tests pass, and add new tests for any added features.


## License

tc-angular-chartjs is dual licensed with the Apache-2.0 or MIT license.

See LICENSE-APACHE-2.0 and LICENSE-MIT for more details.

