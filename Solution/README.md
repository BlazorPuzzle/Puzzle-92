# Puzzle #92 - A LITTLE Interactivity Please?
Jeff and Carl want to know the best way to make interactive components without global interactivity.

YouTube Video: https://youtu.be/xRIGV8iJo7E

Blazor Puzzle Home Page: https://blazorpuzzle.com

## The Challenge

This application is a Blazor Static Server Rendered app.

In this puzzle, we've got a custom button component that you can click and it writes a log message. 

By default, this button will not do anything when clicked, because we have not activated the Blazor interactivity on this page. The `@rendermode` directive is commented out at the top of this file. If you uncomment it, then the button will work.

What if we want to place the button in the layout so that it is always available?

## The Solution

There are two solutions to this puzzle. 

The first solution is to just add the `@rendermode` attribute on the `MyButton` declaration in *MainLayout.razor* like so:

```xml
<MyButton @rendermode=InteractiveServer LogMessage="You clicked the button in the layout"></MyButton>
```

You can specify a `rendermode` on an individual component! This is ultimately flexible because you may also have instances that are NOT interactive.

The second solution is to implement the `@rendermode` attribute inside the button itself:

```xml
@rendermode InteractiveServer
<button @onclick="OnClick">
	Click Me!
</button>
@code {

	[Parameter]
	public string LogMessage { get; set; } = "Click Me!";

	private void OnClick()
	{
		Console.WriteLine(LogMessage);
	}
}
```

With this approach, ALL instances of `MyButton` will be interactive. 

Boom!
