---
title: Getting Started
page_title: .NET MAUI ListPicker Documentation - Getting Started
description: Get started with the Telerik UI for .NET MAUI ListPicker control and add the control to your .NET MAUI project.
position: 1
previous_url: /controls/listpicker/listpicker-getting-started
slug: listpicker-getting-started
---

# Getting Started with the .NET MAUI ListPicker

This guide provides the information you need to start using the Telerik UI for .NET MAUI ListPicker by adding the control to your project.

At the end, you will achieve the following result.

![ListPicker Getting Started](images/listpicker_getting_started.png)

## Prerequisites

Before adding the ListPicker, you need to:

1. [Set up your .NET MAUI application]({%slug maui-getting-started %}#step-1-set-up-your-net-maui-application).

1. [Download Telerik UI for .NET MAUI]({% slug maui-getting-started %}#step-2-download-telerik-ui-for-net-maui).

1. [Install Telerik UI for .NET MAUI]({%slug maui-getting-started %}#step-3-install-telerik-ui-for-net-maui).

## Define the Control

1. When the your .NET MAUI application is set up, you are ready to add a ListPicker control to your page.

 ```XAML
<telerik:RadListPicker Placeholder="Pick a name!"
							ItemsSource="{Binding Items}"
							DisplayMemberPath="FullName">
	<telerik:RadListPicker.BindingContext>
		<local:PeopleViewModel/>
	</telerik:RadListPicker.BindingContext>
	<telerik:RadListPicker.ItemTemplate>
		<DataTemplate>
			<Label Text="{Binding Name}"
				   HorizontalTextAlignment="Center"
				   VerticalTextAlignment="Center"/>
		</DataTemplate>
	</telerik:RadListPicker.ItemTemplate>
</telerik:RadListPicker>
 ```

1. Add a sample `ViewModel` class:

 ```C#
public class PeopleViewModel
{
	public PeopleViewModel()
	{
		this.Items = new ObservableCollection<Person>()
		{
			new Person("Freda","Curtis"),
			new Person("Jeffery","Francis"),
			new Person("Ema","Lawson"),
			new Person("Niki","Samaniego"),
			new Person("Jenny","Santos"),
			new Person("Eric","Wheeler"),
			new Person("Emmett","Fuller"),
			new Person("Brian","Johnas"),
		};
	}

	public ObservableCollection<Person> Items { get; set; }
}
 ```

1. Create the Business model:

 ```C#
public class Person
{
	public Person(string name, string lastName)
	{
		this.Name = name;
		this.LastName = lastName;
	}

	public string Name { get; set; }

	public string LastName { get; set; }

	public string FullName
	{
		get
		{
			return $"{this.Name} {this.LastName}";
		}
	}
}
 ```

1. Add the following namespace:

 ```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
 ```

1. Register the Telerik controls through the `Telerik.Maui.Controls.Compatibility.UseTelerik` extension method called inside the `CreateMauiApp` method of the `MauiProgram.cs` file of your project:

```C#
 using Telerik.Maui.Controls.Compatibility;

 public static class MauiProgram
 {
	public static MauiApp CreateMauiApp()
	{
		var builder = MauiApp.CreateBuilder();
		builder
			.UseTelerik()
			.UseMauiApp<App>()
			.ConfigureFonts(fonts =>
			{
				fonts.AddFont("OpenSans-Regular.ttf", "OpenSansRegular");
			});

		return builder.Build();
	}
 }           
```

## Additional Resources

- [.NET MAUI ListPicker Product Page](https://www.telerik.com/maui-ui/listpicker)
- [.NET MAUI ListPicker Forum Page](https://www.telerik.com/forums/maui?tagId=1855)
- [Telerik .NET MAUI Blogs](https://www.telerik.com/blogs/mobile-net-maui)
- [Telerik .NET MAUI Roadmap](https://www.telerik.com/support/whats-new/maui-ui/roadmap)

## See Also

- [Looping]({%slug listpicker-looping%})
- [Templates]({%slug listpicker-templates%})
- [Styling]({%slug listpicker-styling%})
- [Visual Structure]({%slug listpicker-visual-structure%})
