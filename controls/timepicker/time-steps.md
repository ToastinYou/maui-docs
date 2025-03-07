---
title: Time Steps
page_title: .NET MAUI TimePicker Documentation - Time Steps
description: Learn more about the time steps functionality that the Telerik UI for .NET MAUI TimePicker control provides.
position: 2
previous_url: /controls/timepicker/timepicker-time-steps
slug: timepicker-time-steps
---

# .NET MAUI TimePicker Time Steps

By default, the TimePicker increments each part of its time values by one step.

You can change the default setup using the following properties:

* `HourStep`(`int`)&mdash;Controls the incremental step of the hour value. The default value is `1`.
* `MinuteStep`(`int`)&mdash;Controls the incremental step of the minute value. The default value is `1`.
* `SecondStep`(`int`)&mdash;Controls the incremental step of the second value. The default value is `1`.

The following example shows how to set the time steps.

1. Define the TimePicker.

 ```XAML
<telerik:RadTimePicker HourStep="2"
                         MinuteStep="10"
                         SecondStep="30"/>
 ```

1. Add the namespace.

 ```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
 ```

## See Also

- [Templates]({%slug timepicker-templates%})
- [Time Format Strings]({%slug timepicker-formatting%})
- [Styling]({%slug timepicker-styling%})
- [Selection]({%slug timepicker-selection%})
- [Commands]({%slug timepicker-commands%})
