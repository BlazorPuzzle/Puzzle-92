# Puzzle #92 - A LITTLE Interactivity Please?
Jeff and Carl want to know the best way to make interactive components without global interactivity.

YouTube Video: https://youtu.be/xRIGV8iJo7E

Blazor Puzzle Home Page: https://blazorpuzzle.com

## The Challenge

This application is a Blazor Static Server Rendered app.

In this puzzle, we've got a custom button component that you can click and it writes a log message. 

By default, this button will not do anything when clicked, because we have not activated the Blazor interactivity on this page. The `@rendermode` directive is commented out at the top of this file. If you uncomment it, then the button will work.

What if we want to place the button in the layout so that it is always available?
