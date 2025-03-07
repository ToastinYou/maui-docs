---
title: Bind custom Clear Selection command to editable ComboBox.
description: Override the behavior of the Clear Selection Command in editable ComboBox by using the custom command.
type: how-to
page_title: Bind custom Clear Selection command to editable ComboBox
slug: combobox-clear-selection-command
position: 
tags: command, combobox, clear, button, editable 
ticketid: 1616145
res_type: kb
---

## Environment
<table>
    <tbody>
        <tr>
            <td>Product Version</td>
            <td>6.1.0</td>
        </tr>
        <tr>
            <td>Product</td>
            <td>ComboBox for MAUI</td>
        </tr>
    </tbody>
</table>


## Description

How can I override the behavior of the clear button in the editable ComboBox control?

I want to achieve the following: When the user starts typing into an editable ComboBox and clicks the clear button before they've selected another item, the clear button must revert their text to what was in there before they started typing and keep the previously selected item selected, instead of clearing the text and selected item.

## Solution

To override the default behavior of the clear button, use a custom `ClearSelectionCommand` command:

**1.** Define the ComboBox control in XAML:

```XAML
 <telerik:RadComboBox x:Name="comboBox"
                      IsEditable="True"
                      Text="{Binding MyText , Mode=TwoWay}"
                      ItemsSource="{Binding Items}"
                      DisplayMemberPath="Name"
                      ClearSelectionCommand="{Binding MyCustomCommand}"
                      SelectedItem="{Binding SelectedItem, Mode=TwoWay}"
                      SelectionMode="Single">
</telerik:RadComboBox>
```

**2.** Add the following namespace:

```XAML 
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
```

**3.** Define the business model:

```C#
public class City
{
    public string Name { get; set; }
}
```

**4.** Define the ViewModel and create the custom command:

```C#
public class ViewModel : NotifyPropertyChangedBase
{
    private City selectedItem;
    public ViewModel()
    {
        this.Items = new ObservableCollection<City>
        {
            new City { Name = "Tokyo"},
            new City { Name = "New York"},
            new City { Name = "London"},
            new City { Name = "Madrid"},
            new City { Name = "Los Angeles"},
            new City { Name = "Paris"},
            new City { Name = "Beijing"},
            new City { Name = "Singapore"},
            new City { Name = "New Delhi"},
            new City { Name = "Bangkok"},
            new City { Name = "Berlin"},
        };
         
        this.MyCustomCommand = new Command(()=> this.MyText = this.SelectedItem.Name);
    }

    public ObservableCollection<City> Items { get; set; }

    public City SelectedItem
    {
        get
        {
            return this.selectedItem;
        }
        set
        {
            if (this.selectedItem != value)
            {
                this.selectedItem = value;
                OnPropertyChanged();
            }
        }
    }

    private ICommand myCustomCommand;

    public ICommand MyCustomCommand
    {
        get
        {
            return this.myCustomCommand;
        }
        set
        {
            if (this.myCustomCommand != value)
            {
                this.myCustomCommand = value;
                OnPropertyChanged();
            }
        }
    }

    private string myText;

    public string MyText
    {
        get
        {
            return this.myText;
        }
        set
        {
            if (this.myText != value)
            {
                this.myText = value;
                OnPropertyChanged();
            }
        }
    }
}
```

The following `.gif` file represents the result from the code snippet:

![.NET MAUI ComboBox Clear Button with command](images/combobox-clear-selection.gif)
