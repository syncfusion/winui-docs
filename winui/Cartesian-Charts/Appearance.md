---
layout: post
title: Appearance in WinUI Chart control | Syncfusion
description: This section explains about how to apply palettes and gradient in the Syncfusion WinUI Chart(SfCartesianChart) control.
platform: WinUI
control: SfCartesianChart
documentation: ug
---

# Appearance in WinUI Chart (SfCartesianChart)

The appearance of [SfCartesianChart](https://help.syncfusion.com/cr/winui/Syncfusion.UI.Xaml.Charts.SfCartesianChart.html) can be customized by using the predefined palettes, custom palettes and gradient, which allows to enrich the application.

## Palettes

[SfCartesianChart](https://help.syncfusion.com/cr/winui/Syncfusion.UI.Xaml.Charts.SfCartesianChart.html) provides options for applying various kinds of palettes. Some predefined palettes, such as.

* Metro
* AutumnBrights
* FloraHues
* Pineapple
* TomatoSpectrum
* RedChrome
* PurpleChrome
* BlueChrome
* GreenChrome
* Elite
* LightCandy
* SandyBeach

N> Elite, SandyBeach and LightCandy palettes are not supported in the bitmap series types.

### Applying Palette

Each palette applies a set of predefined brushes to the series in a predefined order. [Metro](https://help.syncfusion.com/cr/winui/Syncfusion.UI.Xaml.Charts.ChartColorPalette.html#Syncfusion_UI_Xaml_Charts_ChartColorPalette_Metro) palette is the default palette.

{% tabs %}

{% highlight xaml %}

<chart:SfCartesianChart x:Name="chart" Palette="Metro">

</chart:SfCartesianChart>

{% endhighlight %}

{% highlight c# %}

SfCartesianChart chart = new SfCartesianChart();
chart.Palette = ChartColorPalette.Metro;
. . .
this.Content = chart;

{% endhighlight %}

{% endtabs %}

![Predefined palette in WinUI Chart](Appearance_images/WinUI_chart_predefined_palette.png)

The following code example defined [Palette](https://help.syncfusion.com/cr/winui/Syncfusion.UI.Xaml.Charts.ChartBase.html#Syncfusion_UI_Xaml_Charts_ChartBase_Palette) as [BlueChrome](https://help.syncfusion.com/cr/winui/Syncfusion.UI.Xaml.Charts.ChartColorPalette.html#Syncfusion_UI_Xaml_Charts_ChartColorPalette_BlueChrome).

{% tabs %}

{% highlight xaml %}

<chart:SfCartesianChart x:Name="chart" Palette="BlueChrome"/>

{% endhighlight %}

{% highlight c# %}

SfCartesianChart chart = new SfCartesianChart();
chart.Palette = ChartColorPalette.BlueChrome;
. . .
this.Content = chart;

{% endhighlight %}

{% endtabs %}

![Palette support in WinUI Chart](Appearance_images/WinUI_chart_bluechrome_palette.png)

### Applying Palette to Segment

Cartesian chart provides support to set the palette to series for applying predefined brushes to the segment. The following code example shows you how to set the [GreenChrome](https://help.syncfusion.com/cr/winui/Syncfusion.UI.Xaml.Charts.ChartColorPalette.html#Syncfusion_UI_Xaml_Charts_ChartColorPalette_GreenChrome) palette for the series.

{% tabs %}

{% highlight xaml %}

<chart:ColumnSeries ItemsSource="{Binding Data}"  
                    XBindingPath="Demand" 
                    YBindingPath="Year2010" 
                    Palette="GreenChrome"/>

{% endhighlight %}

{% highlight c# %}

ColumnSeries series1 = new ColumnSeries()
{
    ItemsSource = new ViewModel().Data,
    XBindingPath = "Demand",
    YBindingPath = "Year2010",
    Palette = ChartColorPalette.GreenChrome
};

{% endhighlight %}

{% endtabs %}

![Series palette support in WinUI Chart](Appearance_images/WinUI_chart_greenchrome_palette.png)

## Custom Palette

[SfCartesianChart](https://help.syncfusion.com/cr/winui/Syncfusion.UI.Xaml.Charts.SfCartesianChart.html) provides support to define own brushes for the chart with preferred order by using the [CustomBrushes](https://help.syncfusion.com/cr/winui/Syncfusion.UI.Xaml.Charts.ChartColorModel.html#Syncfusion_UI_Xaml_Charts_ChartColorModel_CustomBrushes) property of [ChartColorModel](https://help.syncfusion.com/cr/winui/Syncfusion.UI.Xaml.Charts.ChartColorModel.html) and [Palette](https://help.syncfusion.com/cr/winui/Syncfusion.UI.Xaml.Charts.ChartBase.html#Syncfusion_UI_Xaml_Charts_ChartBase_Palette) value as `Custom`, as shown in the following code example.

{% tabs %}

{% highlight xaml %}

<chart:SfCartesianChart.Series>
    <chart:ColumnSeries ItemsSource="{Binding Data}"  
                        XBindingPath="Demand" 
                        YBindingPath="Year2010" 
                        Palette="Custom">
        <chart:ColumnSeries.ColorModel>
            <chart:ChartColorModel>
                <chart:ChartColorModel.CustomBrushes>
                    <SolidColorBrush Color="#26c6da"/>
                    <SolidColorBrush Color="#00bcd4"/>
                    <SolidColorBrush Color="#00acc1"/>
                    <SolidColorBrush Color="#0097a7"/>
                    <SolidColorBrush Color="#00838f"/>
                </chart:ChartColorModel.CustomBrushes>
            </chart:ChartColorModel>
        </chart:ColumnSeries.ColorModel>
    </chart:ColumnSeries>
</chart:SfCartesianChart.Series>

{% endhighlight %}

{% highlight c# %}

SfCartesianChart chart = new SfCartesianChart();
. . .
ChartColorModel colorModel = new ChartColorModel();
colorModel.CustomBrushes.Add(new SolidColorBrush(Color.FromArgb(255, 38, 198, 218)));
colorModel.CustomBrushes.Add(new SolidColorBrush(Color.FromArgb(255, 0, 188, 212)));
colorModel.CustomBrushes.Add(new SolidColorBrush(Color.FromArgb(255, 0, 172, 193)));
colorModel.CustomBrushes.Add(new SolidColorBrush(Color.FromArgb(255, 0, 151, 167)));
colorModel.CustomBrushes.Add(new SolidColorBrush(Color.FromArgb(255, 0, 131, 143)));

ColumnSeries series = new ColumnSeries()
{
    ItemsSource = new ViewModel().Data,
    XBindingPath = "Demand",
    YBindingPath = "Year2010",
    Palette = ChartColorPalette.Custom,
    ColorModel = colorModel
};
. . .
chart.Series.Add(series);
this.Content = chart;

{% endhighlight %}

{% endtabs %}

![Custom palette in WinUI Chart](Appearance_images/WinUI_chart_custom_palette.png)

## Applying Gradient

Gradient for the chart can be set by using the [ColorModel](https://help.syncfusion.com/cr/winui/Syncfusion.UI.Xaml.Charts.ChartBase.html#Syncfusion_UI_Xaml_Charts_ChartBase_ColorModel) property with the help of `LinearGradientBrush` or `RadialGradientBrush`.

The following code sample and screenshot illustrates how to apply the gradient brushes for the series using the [ColorModel](https://help.syncfusion.com/cr/winui/Syncfusion.UI.Xaml.Charts.ChartBase.html#Syncfusion_UI_Xaml_Charts_ChartBase_ColorModel) property.

{% tabs %}

{% highlight xaml %}

 <chart:ColumnSeries ItemsSource="{Binding Data}"  
                                      XBindingPath="Demand" 
                                      YBindingPath="Year2010" 
                                      Palette="Custom">
    <chart:ColumnSeries.ColorModel>
        <chart:ChartColorModel>
            <chart:ChartColorModel.CustomBrushes>
                <LinearGradientBrush>
                    <GradientStop Offset="1" Color="#FFE7C7" />
                    <GradientStop Offset="0" Color="#FCB69F" />
                </LinearGradientBrush>
                <LinearGradientBrush>
                    <GradientStop Offset="1" Color="#fadd7d" />
                    <GradientStop Offset="0" Color="#fccc2d" />
                </LinearGradientBrush>
                <LinearGradientBrush>
                    <GradientStop Offset="1" Color="#DCFA97" />
                    <GradientStop Offset="0" Color="#96E6A1" />
                </LinearGradientBrush>
                <LinearGradientBrush>
                    <GradientStop Offset="1" Color="#DDD6F3" />
                    <GradientStop Offset="0" Color="#FAACA8" />
                </LinearGradientBrush>
                <LinearGradientBrush>
                    <GradientStop Offset="1" Color="#A8EAEE" />
                    <GradientStop Offset="0" Color="#7BB0F9" />
                </LinearGradientBrush>
            </chart:ChartColorModel.CustomBrushes>
        </chart:ChartColorModel>
    </chart:ColumnSeries.ColorModel>
</chart:ColumnSeries>

{% endhighlight %}

{% highlight c# %}

SfCartesianChart chart = new SfCartesianChart();
...
ChartColorModel colorModel = new ChartColorModel();
LinearGradientBrush gradientColor1 = new LinearGradientBrush();
GradientStop stop1 = new GradientStop() { Offset = 1, Color = Color.FromRgb(255, 231, 199) };
GradientStop stop2 = new GradientStop() { Offset = 0, Color = Color.FromRgb(252, 182, 159) };
gradientColor1.GradientStops.Add(stop1);
gradientColor1.GradientStops.Add(stop2);
LinearGradientBrush gradientColor2 = new LinearGradientBrush();
stop1 = new GradientStop() { Offset = 1, Color = Color.FromRgb(250, 221, 125) };
stop2 = new GradientStop() { Offset = 0, Color = Color.FromRgb(252, 204, 45) };
gradientColor2.GradientStops.Add(stop1);
gradientColor2.GradientStops.Add(stop2);
...
colorModel.CustomBrushes.Add(gradientColor1);
colorModel.CustomBrushes.Add(gradientColor2);
...
ColumnSeries series = new ColumnSeries()
{
    ItemsSource = new ViewModel().Data,
    XBindingPath = "Demand",
    YBindingPath = "Year2010",
    Palette = ChartColorPalette.Custom,
    ColorModel = colorModel
};
chart.Series.Add(series);
. . .            
this.Content = chart;

{% endhighlight %}

{% endtabs %}

![Gradient support in WinUI Chart](Appearance_images/WinUI_chart_gradient_color.png)

The following code sample and screenshot illustrates how to apply the gradient color using the [Interior](https://help.syncfusion.com/cr/winui/Syncfusion.UI.Xaml.Charts.ChartSeriesBase.html#Syncfusion_UI_Xaml_Charts_ChartSeriesBase_Interior) property of series with `LinearGradientBrush`.

{% tabs %}

{% highlight xaml %}

 <chart:SfCartesianChart.Series>
    <chart:ColumnSeries ItemsSource="{Binding Data}" 
                        XBindingPath="Demand" 
                        YBindingPath="Year2010">
        <chart:ColumnSeries.Interior>
            <LinearGradientBrush>
                <GradientStop Offset="1" Color="#A8EAEE" />
                <GradientStop Offset="0" Color="#7BB0F9" />
            </LinearGradientBrush>
        </chart:ColumnSeries.Interior>
    </chart:ColumnSeries>
</chart:SfCartesianChart.Series>

{% endhighlight %}

{% highlight c# %}

SfCartesianChart chart = new SfCartesianChart();
...
LinearGradientBrush gradientColor = new LinearGradientBrush();
GradientStop stop1 = new GradientStop() { Offset = 1, Color = Color.FromRgb(168, 234, 238) };
GradientStop stop2 = new GradientStop() { Offset = 0, Color = Color.FromRgb(123, 176, 249) };
gradientColor.GradientStops.Add(stop1);
gradientColor.GradientStops.Add(stop2);
...
ColumnSeries series = new ColumnSeries()
{
    ItemsSource = new ViewModel().Data,
    XBindingPath = "Demand",
    YBindingPath = "Year2010",
    Interior = gradientColor,
};
. . .            
this.Content = chart;

{% endhighlight %}

{% endtabs %}

![Interior support in WinUI Chart](Appearance_images/WinUI_chart_interior_gradient_color.png)

## Segment Color Binding

The color of the each segment can be set by binding their corresponding model property from the `ItemsSource` collection to its [SegmentColorPath](https://help.syncfusion.com/cr/winui/Syncfusion.UI.Xaml.Charts.ChartSeriesBase.html#Syncfusion_UI_Xaml_Charts_ChartSeriesBase_SegmentColorPath) property of series as follows.

{% tabs %}

{% highlight xaml %}

<chart:ColumnSeries x:Name="chart" 
                ItemsSource="{Binding Data}" 
                XBindingPath="Demand"
                YBindingPath="Year2010"
                SegmentColorPath="SegmentColor">
</chart:ColumnSeries>

{% endhighlight %}

{% highlight c# %}

public class ViewModel
{
    public ObservableCollection<Model> Data { get; set; }

    public ViewModel()
    {
        Data = new ObservableCollection<Model>()
        {
            new Model(){ Demand = "Jewelry", Year2010 = 500 , SegmentColor = new SolidColorBrush(Color.FromArgb(255, 152, 251, 152))},
            new Model(){ Demand = "Electronics", Year2010 = 1300, SegmentColor = new SolidColorBrush(Color.FromArgb(255, 255, 105, 180))},
            new Model(){ Demand = "Research", Year2010 = 1100 , SegmentColor = new SolidColorBrush(Color.FromArgb(255, 255, 165, 0))},
            new Model(){ Demand = "Investment", Year2010 = 1600 , SegmentColor = new SolidColorBrush(Color.FromArgb(255, 238, 130, 238))},
            new Model(){ Demand = "Purchases", Year2010 = 1000 , SegmentColor = new SolidColorBrush(Color.FromArgb(255, 0, 255, 255))},

        };
    }
}

SfCartesianChart chart = new SfCartesianChart();
. . .
ColumnSeries series = new ColumnSeries()
{
    ItemsSource = viewModel.Data,
    XBindingPath = "Demand",
    YBindingPath = "Year2010",
    SegmentColorPath = "SegmentColor"
};
. . .            
this.Content = chart;

{% endhighlight %}

{% endtabs %}

![Segment color binding support in WinUI Chart](Appearance_images/WinUI_chart_colorvaluepath.png)

