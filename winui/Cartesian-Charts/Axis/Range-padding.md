---
layout: post
title: Range padding in WinUI Chart control | Syncfusion
description: Learn here all about axis range padding and its types features of Syncfusion WinUI Chart (SfCartesianChart) control.
platform: WinUI
control: SfCartesianChart
documentation: ug
---

# Range Padding in WinUI Chart (SfCartesianChart)

Range padding is used to apply the minimum and maximum extremes of chart axis range by using the `RangePadding` property. The [NumericalAxis](https://help.syncfusion.com/cr/winui/Syncfusion.UI.Xaml.Charts.NumericalAxis.html) and [DateTimeAxis](https://help.syncfusion.com/cr/winui/Syncfusion.UI.Xaml.Charts.DateTimeAxis.html) have a [RangePadding](https://help.syncfusion.com/cr/winui/Syncfusion.UI.Xaml.Charts.DateTimeAxis.html#Syncfusion_UI_Xaml_Charts_DateTimeAxis_RangePadding) property that can be used to add padding to the range of the chart axis.

## Numerical Range Padding

The [RangePadding](https://help.syncfusion.com/cr/winui/Syncfusion.UI.Xaml.Charts.NumericalAxis.html#Syncfusion_UI_Xaml_Charts_NumericalAxis_RangePadding) is used to set the numeric range for axis.

The following types are available for [NumericalAxis](https://help.syncfusion.com/cr/winui/Syncfusion.UI.Xaml.Charts.NumericalAxis.html) range padding:

* [Additional](https://help.syncfusion.com/cr/winui/Syncfusion.UI.Xaml.Charts.NumericalPadding.html#Syncfusion_UI_Xaml_Charts_NumericalPadding_Additional) - The visible start and end range will be added with an additional interval. 
* [None](https://help.syncfusion.com/cr/winui/Syncfusion.UI.Xaml.Charts.NumericalPadding.html#Syncfusion_UI_Xaml_Charts_NumericalPadding_None) - The visible range sets to exact minimum and maximum value of the items source.
* [Normal](https://help.syncfusion.com/cr/winui/Syncfusion.UI.Xaml.Charts.NumericalPadding.html#Syncfusion_UI_Xaml_Charts_NumericalPadding_Normal) - The visible range will be the actual range calculated from given items source and series types.
* [Auto](https://help.syncfusion.com/cr/winui/Syncfusion.UI.Xaml.Charts.NumericalPadding.html#Syncfusion_UI_Xaml_Charts_NumericalPadding_Auto) - Automatically chosen based on the orientation of the axis.
* [Round](https://help.syncfusion.com/cr/winui/Syncfusion.UI.Xaml.Charts.NumericalPadding.html#Syncfusion_UI_Xaml_Charts_NumericalPadding_Round) - The visible start and end range round to nearest interval value.
* [RoundStart](https://help.syncfusion.com/cr/winui/Syncfusion.UI.Xaml.Charts.NumericalPadding.html#Syncfusion_UI_Xaml_Charts_NumericalPadding_RoundStart) - The visible start range round to nearest interval value.
* [RoundEnd](https://help.syncfusion.com/cr/winui/Syncfusion.UI.Xaml.Charts.NumericalPadding.html#Syncfusion_UI_Xaml_Charts_NumericalPadding_RoundEnd) -  The visible end range round to nearest interval value. 
* [PrependInterval](https://help.syncfusion.com/cr/winui/Syncfusion.UI.Xaml.Charts.NumericalPadding.html#Syncfusion_UI_Xaml_Charts_NumericalPadding_PrependInterval) - The visible start range will be prepended with an additional interval.
* [AppendInterval](https://help.syncfusion.com/cr/winui/Syncfusion.UI.Xaml.Charts.NumericalPadding.html#Syncfusion_UI_Xaml_Charts_NumericalPadding_AppendInterval) - The visible end range will be appended with an additional interval.

By default, the [RangePadding](https://help.syncfusion.com/cr/winui/Syncfusion.UI.Xaml.Charts.NumericalAxis.html#Syncfusion_UI_Xaml_Charts_NumericalAxis_RangePadding) value for [PrimaryAxis](https://help.syncfusion.com/cr/winui/Syncfusion.UI.Xaml.Charts.SfCartesianChart.html#Syncfusion_UI_Xaml_Charts_SfCartesianChart_PrimaryAxis) is [Auto](https://help.syncfusion.com/cr/winui/Syncfusion.UI.Xaml.Charts.NumericalPadding.html#Syncfusion_UI_Xaml_Charts_NumericalPadding_Auto) and for [SecondaryAxis](https://help.syncfusion.com/cr/winui/Syncfusion.UI.Xaml.Charts.SfCartesianChart.html#Syncfusion_UI_Xaml_Charts_SfCartesianChart_SecondaryAxis) is [Round](https://help.syncfusion.com/cr/winui/Syncfusion.UI.Xaml.Charts.NumericalPadding.html#Syncfusion_UI_Xaml_Charts_NumericalPadding_Round).

**Additional**

{% tabs %}

{% highlight xaml %}

<chart:SfCartesianChart Palette="BlueChrome">
. . .
    <chart:SfCartesianChart.PrimaryAxis>
        <chart:NumericalAxis  RangePadding="Additional"/>
    </chart:SfCartesianChart.PrimaryAxis>

    <chart:SfCartesianChart.SecondaryAxis>
        <chart:NumericalAxis />
    </chart:SfCartesianChart.SecondaryAxis>
. . .
</chart:SfCartesianChart>

{% endhighlight %}

{% highlight c# %}

SfCartesianChart chart = new SfCartesianChart();
chart.Palette = ChartColorPalette.BlueChrome;

chart.PrimaryAxis = new NumericalAxis()
{
    RangePadding = NumericalPadding.Additional,
};

chart.SecondaryAxis = new NumericalAxis();
. . .
this.Content = chart;

{% endhighlight %}

{% endtabs %}

![NumericalAxis range padding support in WinUI Chart](Axis_Images/winui_chart_axis_numerical-range-padding_additional.png)

**None**

{% tabs %}

{% highlight xaml %}

<chart:SfCartesianChart Palette="BlueChrome">
. . .
    <chart:SfCartesianChart.PrimaryAxis>
        <chart:NumericalAxis RangePadding="None"/>
    </chart:SfCartesianChart.PrimaryAxis>

    <chart:SfCartesianChart.SecondaryAxis>
        <chart:NumericalAxis />
    </chart:SfCartesianChart.SecondaryAxis>
. . .
</chart:SfCartesianChart>

{% endhighlight %}

{% highlight c# %}

SfCartesianChart chart = new SfCartesianChart();
chart.Palette = ChartColorPalette.BlueChrome;

chart.PrimaryAxis = new NumericalAxis()
{
    RangePadding = NumericalPadding.None,
};

chart.SecondaryAxis = new NumericalAxis();
. . .
this.Content = chart;

{% endhighlight %}

{% endtabs %}

![NumericalAxis range padding none in WinUI Chart](Axis_Images/winui_chart_axis_numerical-range-padding_none.png)

**Round**

{% tabs %}

{% highlight xaml %}

<chart:SfCartesianChart Palette="BlueChrome">
. . .
    <chart:SfCartesianChart.PrimaryAxis>
        <chart:NumericalAxis  RangePadding="Round"/>
    </chart:SfCartesianChart.PrimaryAxis>

    <chart:SfCartesianChart.SecondaryAxis>
        <chart:NumericalAxis />
    </chart:SfCartesianChart.SecondaryAxis>
. . .
</chart:SfCartesianChart>

{% endhighlight %}

{% highlight c# %}

SfCartesianChart chart = new SfCartesianChart();
chart.Palette = ChartColorPalette.BlueChrome;

chart.PrimaryAxis = new NumericalAxis()
{
    RangePadding = NumericalPadding.Round,
};

chart.SecondaryAxis = new NumericalAxis();
. . .
this.Content = chart;

{% endhighlight %}

{% endtabs %}

![NumericalAxis range padding round in WinUI Chart](Axis_Images/winui_chart_axis_numerical-range-padding_round.png)

## DateTime Range Padding

The [RangePadding](https://help.syncfusion.com/cr/winui/Syncfusion.UI.Xaml.Charts.NumericalAxis.html) types available in the [DateTimeAxis](https://help.syncfusion.com/cr/winui/Syncfusion.UI.Xaml.Charts.DateTimeAxis.html) are: 

* [Auto](https://help.syncfusion.com/cr/winui/Syncfusion.UI.Xaml.Charts.DateTimeRangePadding.html#Syncfusion_UI_Xaml_Charts_DateTimeRangePadding_Auto) - Automatically chosen based on the orientation of the axis.
* [Additional](https://help.syncfusion.com/cr/winui/Syncfusion.UI.Xaml.Charts.DateTimeRangePadding.html#Syncfusion_UI_Xaml_Charts_DateTimeRangePadding_Additional) - The visible start and end range will be added with an additional interval.
* [None](https://help.syncfusion.com/cr/winui/Syncfusion.UI.Xaml.Charts.DateTimeRangePadding.html#Syncfusion_UI_Xaml_Charts_DateTimeRangePadding_None) - The visible range sets to exact minimum and maximum value of the items source.
* [Round](https://help.syncfusion.com/cr/winui/Syncfusion.UI.Xaml.Charts.DateTimeRangePadding.html#Syncfusion_UI_Xaml_Charts_DateTimeRangePadding_Round) - The visible start and end range round to nearest interval value.
* [RoundStart](https://help.syncfusion.com/cr/winui/Syncfusion.UI.Xaml.Charts.DateTimeRangePadding.html#Syncfusion_UI_Xaml_Charts_DateTimeRangePadding_RoundStart) - The visible start range round to nearest interval value.
* [RoundEnd](https://help.syncfusion.com/cr/winui/Syncfusion.UI.Xaml.Charts.DateTimeRangePadding.html#Syncfusion_UI_Xaml_Charts_DateTimeRangePadding_RoundEnd) - The visible end range round to nearest interval value.
* [PrependInterval](https://help.syncfusion.com/cr/winui/Syncfusion.UI.Xaml.Charts.DateTimeRangePadding.html#Syncfusion_UI_Xaml_Charts_DateTimeRangePadding_PrependInterval) - The visible start range will be prepended with an additional interval.
* [AppendInterval](https://help.syncfusion.com/cr/winui/Syncfusion.UI.Xaml.Charts.DateTimeRangePadding.html#Syncfusion_UI_Xaml_Charts_DateTimeRangePadding_AppendInterval) - The visible start range will be appended with an additional interval.

**Additional**

{% tabs %}

{% highlight xaml %}

<chart:SfCartesianChart Palette="BlueChrome">
. . .
    <chart:SfCartesianChart.PrimaryAxis>
        <chart:DateTimeAxis RangePadding="Additional" LabelFormat="MMM-yy"/>
    </chart:SfCartesianChart.PrimaryAxis>

    <chart:SfCartesianChart.SecondaryAxis>
        <chart:NumericalAxis />
    </chart:SfCartesianChart.SecondaryAxis>
. . .
</chart:SfCartesianChart>

{% endhighlight %}

{% highlight c# %}

SfCartesianChart chart = new SfCartesianChart();
chart.Palette = ChartColorPalette.BlueChrome;

chart.PrimaryAxis = new DateTimeAxis()
{
    RangePadding = DateTimeRangePadding.Additional,
    LabelFormat = "MMM-yy"
};

chart.SecondaryAxis = new NumericalAxis();
. . .
this.Content = chart;

{% endhighlight %}

{% endtabs %}

![DateTimeAxis range padding support in WinUI Chart](Axis_Images/winui_chart_axis_datetime-range-padding_additional.png)

**None**

{% tabs %}

{% highlight xaml %}

<chart:SfCartesianChart Palette="BlueChrome">
. . .
    <chart:SfCartesianChart.PrimaryAxis>
        <chart:DateTimeAxis RangePadding="None" LabelFormat="MMM-yy"/>
    </chart:SfCartesianChart.PrimaryAxis>

    <chart:SfCartesianChart.SecondaryAxis>
        <chart:NumericalAxis />
    </chart:SfCartesianChart.SecondaryAxis>
. . .
</chart:SfCartesianChart>

{% endhighlight %}

{% highlight c# %}

SfCartesianChart chart = new SfCartesianChart();
chart.Palette = ChartColorPalette.BlueChrome;

chart.PrimaryAxis = new DateTimeAxis()
{
    RangePadding = DateTimeRangePadding.None,
    LabelFormat = "MMM-yy"
};

chart.SecondaryAxis = new NumericalAxis();
. . .
this.Content = chart;

{% endhighlight %}

{% endtabs %}

![DateTimeAxis range padding none in WinUI Chart](Axis_Images/winui_chart_axis_datetime-range-padding_none.png)

**Round**

{% tabs %}

{% highlight xaml %}

<chart:SfCartesianChart Palette="BlueChrome">
. . .
    <chart:SfCartesianChart.PrimaryAxis>
        <chart:DateTimeAxis RangePadding="Round" LabelFormat="MMM-yy"/>
    </chart:SfCartesianChart.PrimaryAxis>

    <chart:SfCartesianChart.SecondaryAxis>
        <chart:NumericalAxis />
    </chart:SfCartesianChart.SecondaryAxis>
. . .
</chart:SfCartesianChart>

{% endhighlight %}

{% highlight c# %}

SfCartesianChart chart = new SfCartesianChart();
chart.Palette = ChartColorPalette.BlueChrome;

chart.PrimaryAxis = new DateTimeAxis()
{
    RangePadding = DateTimeRangePadding.Round,
    LabelFormat = "MMM-yy"
};

chart.SecondaryAxis = new NumericalAxis();
. . .
this.Content = chart;

{% endhighlight %}

{% endtabs %}

![DateTimeAxis range padding round in WinUI Chart](Axis_Images/winui_chart_axis_datetime-range-padding_round.png)
