# Highcharts Trendline Example

This project illustrates how you can easily add a trendline to your [Highchart](http://www.highcharts.com) charts.

_Note:_ If you are looking for a more complete implementation, checkout the [highcharts-regression][highcharts-regression] [plugin][plugin].

## Usage

Include the `regression.js` script into your HTML page.

Given your source data array, supply a function which calls `fitData(<source>).data` to produce the regression data for the trendline.

E.g.

```javascript
// E.g. source data
var sourceData = [
    [106.4, 271.8], [129.2, 213.4],
    [295.6, 432.3], [154.4, 398.1],
    [129.9, 133.2], [271.5, 432.1],
    [144.0, 134.7], [176.0, 399.2],
    [216.4, 319.2], [194.1, 542.1],
    [435.6, 665.3], [348.5, 435.9]
];

var chart_linear = new Highcharts.Chart({
    chart: {
      renderTo: 'linear'
    },
    plotOptions: {
      series: {
        enableMouseTracking: false
      }
    },
    series: [{
      type: 'scatter',
      data: sourceData
    },
    {
      type: 'line',
      marker: { enabled: false },
      /* function returns data for trend-line */
      data: (function() {
        return fitData(sourceData).data;
      })()
    }]
});
```

## Examples

Checkout the demo HTML files for examples of how to plot various trendlines.

* [Linear Regression][demo1]

  ![Example Chart](demo.jpg)

* [Linear Regression - One dimensional data][demo3]

  ![Example Chart](demo3.jpg)

* [Line Regression (X axis set to category)][demo4]

  ![Example Chart](demo4.jpg)

* [Linear Regression - With Projection][demo5]

  ![Example Chart](demo5.jpg)

# Credits

The code for the `regression.js` script was extracted from [jqplot.trendline.js](http://www.jqplot.com/docs/files/plugins/jqplot-trendline-js.html), by Chris Leonello.

[demo1]: https://github.com/virtualstaticvoid/highcharts_trendline/blob/master/demo.html
[demo2]: https://github.com/virtualstaticvoid/highcharts_trendline/blob/master/demo2.html
[demo3]: https://github.com/virtualstaticvoid/highcharts_trendline/blob/master/demo3.html
[demo4]: https://github.com/virtualstaticvoid/highcharts_trendline/blob/master/demo4.html
[demo5]: https://github.com/virtualstaticvoid/highcharts_trendline/blob/master/demo5.html
[highcharts-regression]: https://github.com/streamlinesocial/highcharts-regression
[plugin]: http://www.highcharts.com/plugin-registry/single/22/Highcharts%20regression
