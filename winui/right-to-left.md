---
layout: post
title: Right-to-left in WinUI Controls | Syncfusion
description: Learn here about Right-to-left FlowDirection support in Syncfusion WinUI Project Reunion controls and more details. 
platform: WinUI
control: RightToLeft
documentation: ug
---

# Right to Left(RTL) in WinUI Controls 

Right to left (RTL) support allows to change the direction of text and other UI elements flow within the controls layout. 
 
Syncfusion WinUI controls support to change the flow direction and are suitable for all applications that are localized in right-to-left languages. The layout of control direction can be changed by setting the [FlowDirection](https://docs.microsoft.com/en-us/uwp/api/windows.ui.xaml.frameworkelement.flowdirection?view=winrt-19041) to `RightToLeft`. 

The example below shows a treeview control with RTL direction.

{% tabs %}
{% highlight xaml %}

<treeView:SfTreeView x:Name="treeView" FlowDirection="RightToLeft"/>

{% endhighlight %}
{% highlight c# %}

treeView.FlowDirection = FlowDirection.RightToLeft;

{% endhighlight %}
{% endtabs %}

![WinUI TreeView with right-to-left flow direction](Common-images/winui-control-right-to-left-direction.png)