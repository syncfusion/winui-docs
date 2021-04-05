---
layout: post
title: Grid Lines | TreeGrid | WinUI | Syncfusion
description: Learn about customization of grid lines for GridCells and HeaderCells in Syncfusion WinUI TreeGrid (SfTreeGrid) control and more details.
platform: winui
control: TreeGrid
documentation: ug
---

# Grid Lines customization in WinUI TreeGrid (SfTreeGrid)

SfTreeGrid allows you to customize the grid lines visibility to vertical, horizontal, both or none. To achieve this, use the following properties.

`SfTreeGrid.GridLinesVisibility`: To set the border lines for the cells other than header and stacked header cells.
`SfTreeGrid.HeaderLinesVisibility`: To set the border lines only for header and stacked header cells.

The following are the list of options available to customize grid lines visibility,

* Both
* Vertical
* Horizontal
* None

## Record rows

### Both

The GridLinesVisibility.Both displays the TreeGrid with both horizontal and vertical grid lines. By default GridLinesVisibility value set as Both.

{% tabs %}
{% highlight xaml %}
xmlns:treeGrid="using:Syncfusion.UI.Xaml.TreeGrid"

<treeGrid:SfTreeGrid  x:Name="sfTreeGrid"
                      AutoExpandMode="RootNodesExpanded"
                      AutoGenerateColumns="False"
                      GridLinesVisibility="Both"
                      ChildPropertyName="Children"
                      ColumnWidthMode="AutoWithLastColumnFill"
                      ExpanderColumn="FirstName"
                      ItemsSource="{Binding Persons}"/>


{% endhighlight %}
{% highlight c# %}
this.sfTreeGrid.GridLinesVisibility = GridLinesVisibility.Both;
{% endhighlight %}
{% endtabs %}

![GridLinesVisibility in WinUI TreeGrid](GridLines_images/GridLines_image1.png)

### Horizontal

The GridLinesVisibility.Horizontal displays the TreeGrid with horizontal grid lines only.

{% tabs %}
{% highlight xaml %}
xmlns:treeGrid="using:Syncfusion.UI.Xaml.TreeGrid"

<treeGrid:SfTreeGrid  x:Name="sfTreeGrid"
                      AutoExpandMode="RootNodesExpanded"
                      AutoGenerateColumns="True"
                      GridLinesVisibility="Horizontal"
                      ChildPropertyName="Children"
                      ColumnWidthMode="AutoWithLastColumnFill"
                      ExpanderColumn="FirstName"
                      ItemsSource="{Binding Persons}"/>

{% endhighlight %}
{% highlight c# %}
this.sfTreeGrid.GridLinesVisibility = GridLinesVisibility.Horizontal;
{% endhighlight %}
{% endtabs %}

![Horizontal GridLinesVisibility in WinUI TreeGrid](GridLines_images/GridLines_image2.png)

### Vertical

The GridLinesVisibility.Vertical displays the TreeGrid with vertical grid lines only.

{% tabs %}
{% highlight xaml %}
xmlns:treeGrid="using:Syncfusion.UI.Xaml.TreeGrid"

<treeGrid:SfTreeGrid  x:Name="sfTreeGrid"
                      AutoExpandMode="RootNodesExpanded"
                      AutoGenerateColumns="True"
                      GridLinesVisibility="Vertical"
                      ChildPropertyName="Children"
                      ColumnWidthMode="AutoWithLastColumnFill"
                      ExpanderColumn="FirstName"
                      ItemsSource="{Binding Persons}"/>

{% endhighlight %}
{% highlight c# %}
this.sfTreeGrid.GridLinesVisibility = GridLinesVisibility.Vertical;
{% endhighlight %}
{% endtabs %}

![Vertical GridLinesVisibility in WinUI TreeGrid](GridLines_images/GridLines_image3.png)

### None
GridLinesVisibility.None displays the TreeGrid without grid lines.

{% tabs %}
{% highlight xaml %}
xmlns:treeGrid="using:Syncfusion.UI.Xaml.TreeGrid"

<treeGrid:SfTreeGrid  x:Name="sfTreeGrid"
                      Height="514"
                      Width="800"
                      Margin="5"
                      VerticalAlignment="Top"
                      AutoExpandMode="RootNodesExpanded"
                      AutoGenerateColumns="False"
                      GridLinesVisibility="None"
                      ChildPropertyName="Children"
                      ColumnWidthMode="AutoWithLastColumnFill"
                      ExpanderColumn="FirstName"
                      ItemsSource="{Binding Persons}"/>

{% endhighlight %}
{% highlight c# %}
this.sfTreeGrid.GridLinesVisibility = GridLinesVisibility.None;
{% endhighlight %}
{% endtabs %}

![None GridLinesVisibility in WinUI TreeGrid](GridLines_images/GridLines_image4.png)

## Header rows

You can customize the TreeGrid header lines visibility by using the SfTreeGrid.HeaderLinesVisibility property. You can also customize the header lines visibility to horizontal, vertical, none or both. By default HeaderLinesVisibility value set as Both.

{% tabs %}
{% highlight xaml %}
xmlns:treeGrid="using:Syncfusion.UI.Xaml.TreeGrid"

<treeGrid:SfTreeGrid  x:Name="sfTreeGrid"
                      AutoExpandMode="RootNodesExpanded"
                      AutoGenerateColumns="True"
                      HeaderLinesVisibility="Horizontal"
                      ChildPropertyName="Children"
                      ColumnWidthMode="AutoWithLastColumnFill"
                      ExpanderColumn="FirstName"
                      ItemsSource="{Binding Persons}"/>

{% endhighlight %}
{% highlight c# %}
this.sfTreeGrid.HeaderLinesVisibility = GridLinesVisibility.Horizontal;
{% endhighlight %}
{% endtabs %}

![Horizontal HeaderLinesVisibility in WinUI TreeGrid](GridLines_images/GridLines_image5.png)

## Limitations

* Grid lines customization are not supported for RowHeader.