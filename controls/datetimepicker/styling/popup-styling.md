---
title: Popup Styling
page_title: .NET MAUI DateTimePicker Documentation - Popup Styling
description: Apply the styling options of the Telerik UI for .NET MAUI DateTimePicker Popup.
position: 1
slug: datetimepicker-popup-styling
---

# .NET MAUI DateTimePicker Popup Styling

By using the `PopupSettings` property (of type `Telerik.Maui.Controls.PickerPopupSettings`) of the DateTimePicker, you can modify the appearance of the dialog (popup). The `PickerPopupSettings` class exposes the following `Style` properties:

* `PopupViewStyle`(of type `Style` with target type `telerik:PickerPopupContentView`)&mdash;Defines the popup view style.
* `HeaderStyle`(of type `Style` with target type `telerik:PickerPopupHeaderView`)&mdash;Defines the popup header style.
* `HeaderLabelStyle`(of type `Style` with target type `Label`)&mdash;Defines the popup header label style.
* `FooterStyle`(of type `Style` with target type `telerik:PickerPopupFooterView`)&mdash;Defines the popup footer style.
* `AcceptButtonStyle`(of type `Style` with target type `Button`)&mdash;Defines the **Accept** button style.
* `CancelButtonStyle`(of type `Style` with target type `Button`)&mdash;Defines the **Cancel** button style.


The `PickerPopupSettings` also provides the following properties for popup customization:


* `PopupOutsideBackgroundColor`&mdash;Defines the color outside of the popup.
* `IsPopupModal`(`bool`)&mdash;Defines a Boolean value indicating if the popup will be closed when tapped outside of the popup. By default, the value of the `IsPopupModal` is `false`.

	When `IsPopupModal="True"`, the UI behind the popup gets inactive and cannot be used until the popup is closed.

	When `IsPopupModal="False"`, the popup can be closed when clicking outside the popup. 	

* `HeaderLabelText` (`string`)&mdash;Specifies the text visualized in the popup header.
* `IsHeaderVisible` (`bool`)&mdash;Specifies whether the Popup header is currently visible. By default, the value is `True`
* `IsFooterVisible` (`bool`)&mdash;Specifies whether the Popup footer is currently visible. By default, the value is `True`.
* `AcceptButtonText` (`string`)&mdash;Defines the text visualized for the `Accept` button. By default, the text is **OK**.
* `CancelButtonText` (`string`)&mdash;Defines the text visualized for the `Cancel` button. By default, the text is **Cancel**.

> __PopupSettings__ provides styling options for the popup, its header and footer, outside background color and other. If you need to customize the look&feel of the spinner controls that show the available date values, please refer to `SpinnerStyle`, `SpinnerHeaderStyle` and `SelectionHighlightStyle` properties of the DateTimePicker. For more detailed information on them go to [DateTimePicker Styling]({%slug datetimepicker-styling%}) topic.

## Namespaces

When you use `PopupViewStyle`, `HeaderStyle`, `FooterStyle`, you will need to add the following namespace:

 ```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
 ```

## Styling Examples

The following examples demonstrate how to define use the styling properties of the DateTimePicker.

**Define the `RadDateTimePicker`**

<snippet id='datetimepicker-popup-style' />

**Define the Spinner Style**

<snippet id='datetimepicker-style-spinner-style' />

**Define the SpinnerHeader Style**

<snippet id='datetimepicker-style-spinner-header-style' />

**Define the PopupView Style**

<snippet id='datetimepicker-style-popupview-style' />

**Define the Header Style**

<snippet id='datetimepicker-style-header-style' />

**Define the HeaderLabel Style**

<snippet id='datetimepicker-style-header-label-style' />

**Define the Footer Style**

<snippet id='datetimepicker-style-footer-style' />

**Define the AcceptButton Style**

<snippet id='datetimepicker-style-accept-button-style' />

**Define the CancelButton Style**

<snippet id='datetimepicker-style-cancel-button-style' />


In addition, add the following namespaces:

 ```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
 ```

The following image shows what the DateTimePicker control looks like when the styles described above are applied:

![DateTimePicker Popup Style](../images/datetimepicker_popupstyle.png)

## See Also

- [DateTimePicker Styling]({%slug datetimepicker-styling%})
- [Formatting]({%slug datetimepicker-formatting%})
- [Visual Structure]({%slug datetimepicker-visual-structure%})
