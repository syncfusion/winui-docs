---
layout: post
title: Localization and Formatting in Calendar DateRange Picker | Syncfusion
description: This section describes how to localize and changed formats in dropdown calendar of Calendar DateRange Picker (SfCalendarDateRangePicker) control.
platform: WinUI
control: SfCalendarDateRangePicker
documentation: ug
---

# Localization and Formatting in WinUI Calendar DateRange Picker

## Types of Calendar

The `Calendar DateRange Picker` control supports different type of calendars such as Gregorian, Julian, Hebrew, etc. You can change the calendar type by using [`CalendarIdentifier`](https://help.syncfusion.com/cr/winui/Syncfusion.UI.Xaml.Calendar.SfCalendarDateRangePicker.html#Syncfusion_UI_Xaml_Calendar_SfCalendarDateRangePicker_CalendarIdentifier) property. The default value of `CalendarIdentifier` property is **GregorianCalendar**.

You can select the required `CalendarIdentifier` value from below types.
 * JulianCalendar
 * GregorianCalendar
 * HebrewCalendar
 * HijriCalendar
 * KoreanCalendar
 * TaiwanCalendar
 * ThaiCalendar
 * UmAlQuraCalendar
 * PersianCalendar

N> Japanese and Lunar type calendars are not supported in `Calendar` control.

N> When `CalendarIdentifier` and `FlowDirection` properties are set, `FlowDirection` property is given higher precedence.

N> `Calendar DateRange Picker` control updates the flow direction visually based on the `CalendarIdentifier` property value.

{% tabs %}
{% highlight xaml %}

<calendar:SfCalendarDateRangePicker CalendarIdentifier="HebrewCalendar"
                               x:Name="sfCalendarDateRangePicker"/>

{% endhighlight %}
{% highlight C# %}

SfCalendarDateRangePicker sfCalendarDateRangePicker = new SfCalendarDateRangePicker();
sfCalendarDateRangePicker.CalendarIdentifier = "HebrewCalendar";

{% endhighlight %}
{% endtabs %}

![Calendar Types aka Calendar Identifier in WinUI Calendar DateRange Picker](Getting-Started_images/winui-calendar-daterange-picker-calendar-types.png)

N> Download demo from [Github](https://github.com/SyncfusionExamples/syncfusion-winui-tools-calendar-daterange-picker-examples/tree/main/Samples/Formatting)

## Change the language

If you want to localize the dropdown calendar, use the `Language` property. The default value of `Language` property is **en-US**.

{% tabs %}
{% highlight xaml %}

<calendar:SfCalendarDateRangePicker Language="ar-AR"
                               x:Name="sfCalendarDateRangePicker"/>

{% endhighlight %}
{% highlight C# %}

SfCalendarDateRangePicker sfCalendarDateRangePicker = new SfCalendarDateRangePicker();
sfCalendarDateRangePicker.Language = "ar-AR";

{% endhighlight %}
{% endtabs %}

![Arabic Culture in WinUI Calendar DateRange Picker](Getting-Started_images/winui-calendar-daterange-picker-arabic-culture.png)

N> Download demo from [Github](https://github.com/SyncfusionExamples/syncfusion-winui-tools-calendar-daterange-picker-examples/tree/main/Samples/Formatting)

## Change editor display format

You can modify and display the selected date range with various formatting like date, month and year formats by using the [`DisplayDateFormat`](https://help.syncfusion.com/cr/winui/Syncfusion.UI.Xaml.Calendar.SfCalendarDateRangePicker.html#Syncfusion_UI_Xaml_Calendar_SfCalendarDateRangePicker_DisplayDateFormat) property. The default value of `DisplayDateFormat` property is **{0:d}-{1:d}**.

{% tabs %}
{% highlight xaml %}

<calendar:SfCalendarDateRangePicker x:Name="sfCalendarDateRangePicker" DisplayDateFormat="{}{0:D} - {1:D}" />
   
{% endhighlight  %}
{% highlight C# %}

SfCalendarDateRangePicker sfCalendarDateRangePicker = new SfCalendarDateRangePicker();
sfCalendarDateRangePicker.DisplayDateFormat= "{0:D}-{1:D}";

{% endhighlight  %}
{% endtabs %}

![WinUI Calendar DateRange Picker String Formatting](Getting-Started_images/winui-calendar-daterange-picker-string-formatting.png)

N> Download demo from [Github](https://github.com/SyncfusionExamples/syncfusion-winui-tools-calendar-daterange-picker-examples/tree/main/Samples/Formatting)

## Change calendar display format

You can use different date formats such as abbreviated or full name for a day, month, week names or header name of month and year in dropdown calendar by using the [`DayFormat`](https://help.syncfusion.com/cr/winui/Syncfusion.UI.Xaml.Calendar.SfCalendarDateRangePicker.html#Syncfusion_UI_Xaml_Calendar_SfCalendarDateRangePicker_DayFormat), [`MonthFormat`](https://help.syncfusion.com/cr/winui/Syncfusion.UI.Xaml.Calendar.SfCalendarDateRangePicker.html#Syncfusion_UI_Xaml_Calendar_SfCalendarDateRangePicker_MonthFormat), [`DayOfWeekFormat`](https://help.syncfusion.com/cr/winui/Syncfusion.UI.Xaml.Calendar.SfCalendarDateRangePicker.html#Syncfusion_UI_Xaml_Calendar_SfCalendarDateRangePicker_DayOfWeekFormat) and [`MonthHeaderFormat`](https://help.syncfusion.com/cr/winui/Syncfusion.UI.Xaml.Calendar.SfCalendarDateRangePicker.html#Syncfusion_UI_Xaml_Calendar_SfCalendarDateRangePicker_MonthHeaderFormat) properties.

N> Refer [DateTimeFormatter](https://docs.microsoft.com/en-us/uwp/api/windows.globalization.datetimeformatting.datetimeformatter?view=winrt-19041) page to get more date formats.

{% tabs %}
{% highlight xaml %}

<calendar:SfCalendarDateRangePicker DayFormat="{}{day.integer(2)}"
                                    MonthFormat="{}{month.full}"
                                    DayOfWeekFormat="{}{dayofweek.abbreviated(3)}"
                                    MonthHeaderFormat="{}{month.abbreviated} {year.abbreviated}‎"
                                    x:Name="sfCalendarDateRangePicker"/>

{% endhighlight %}
{% highlight C# %}

SfCalendarDateRangePicker sfCalendarDateRangePicker = new SfCalendarDateRangePicker();
sfCalendarDateRangePicker.DayFormat = "{day.integer(2)}";
sfCalendarDateRangePicker.MonthFormat = "{month.full}";
sfCalendarDateRangePicker.DayOfWeekFormat = "{dayofweek.abbreviated(3)}";
sfCalendarDateRangePicker.MonthHeaderFormat = "{month.abbreviated} {year.abbreviated}‎";

{% endhighlight %}
{% endtabs %}

![WinUI Calendar DateRange Picker Date Formatting](Getting-Started_images/winui-calendar-daterange-picker-date-formatting.gif)

N> Download demo from [Github](https://github.com/SyncfusionExamples/syncfusion-winui-tools-calendar-daterange-picker-examples/tree/main/Samples/Formatting)

## First day of week

By default, **Sunday** is shown as the first day of the week in a dropdown calendar of `Calendar DateRange Picker` control. You can change the first day of week, by changing the [`FirstDayOfWeek`](https://help.syncfusion.com/cr/winui/Syncfusion.UI.Xaml.Calendar.SfCalendarDateRangePicker.html#Syncfusion_UI_Xaml_Calendar_SfCalendarDateRangePicker_FirstDayOfWeek) property value. 

{% tabs %}
{% highlight xaml %}

<calendar:SfCalendarDateRangePicker x:Name="sfCalendarDateRangePicker" 
                               FirstDayOfWeek="Monday"/>

{% endhighlight %}
{% highlight C# %}

SfCalendarDateRangePicker sfCalendarDateRangePicker = new SfCalendarDateRangePicker();
sfCalendarDateRangePicker.FirstDayOfWeek = DayOfWeek.Monday;

{% endhighlight %}
{% endtabs %}

![First Day of Week in WinUI Calendar DateRange Picker](Dropdown-Calendar_images/winui-calendar-daterange-picker-first-day-of-week.png)

## Change flow direction

By default, flow direction is changed automatically based on selected `CalendarIdentifier` value in `Calendar DateRange Picker` control. However you can override it by explicitly specifying the `FlowDirection` property value. The default value of `FlowDirection` property is **LeftToRight**.

N> When `CalendarIdentifier` and `FlowDirection` properties are set, `FlowDirection` property is given higher precedence.

{% tabs %}
{% highlight XAML %}

<calendar:SfCalendarDateRangePicker FlowDirection="RightToLeft" 
                               x:Name="sfCalendarDateRangePicker"/>

{% endhighlight %}
{% highlight c# %}

SfCalendarDateRangePicker sfCalendarDateRangePicker = new SfCalendarDateRangePicker();
sfCalendarDateRangePicker.FlowDirection = FlowDirection.RightToLeft;

{% endhighlight %}
{% endtabs %}

![WinUI Calendar DateRange Picker Right-to-Left](Dropdown-Calendar_images/winui-calendar-daterange-picker-right-to-left.png)

N> Download demo from [Github](https://github.com/SyncfusionExamples/syncfusion-winui-tools-calendar-daterange-picker-examples/tree/main/Samples/Formatting)
