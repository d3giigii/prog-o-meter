# Style Guide

## What is this?
This is a set of guidelines on how to *style* the code you plan on contributing to the prog-o-meter repository. Please do not let the guidelines discourage you from contributing. If you need further explanation of anything, please ask. If you are not sure your contribution follows the guidelines, **DO NOT FRET**, please submit a pull-request regardless, and we will help you make any necessary changes, before we merge.

No one is perfect! I am 100% sure you will find things in the current code, that do not follow the guidelines below. If you do, please either open a pull request with a fix so we can improve, or let us know by opening an issue, so someone else can fix it.

## Why is this useful? 
When everybody is on the same page, everyone writes better code. The purpose of the prog-o-meter project is too get newcomers out of their shell and excited to start learning, and feel confident contributing to the open source community. The faster everyone starts getting comfortable the better the project will be.

## 1. Quick Start
These are some quick guidelines and principles that this project follows. 

In general...
* **Structure** should follow the [PEP 8](https://www.python.org/dev/peps/pep-0008/#introduction) format.
* **Docstrings** should follow the [Google Python](http://google.github.io/styleguide/pyguide.html?showone=Comments#Comments) format. (Sec. 3)
* Code and comments should be kept **beginner friendly**. Purpose and word choice should be easy to understand. See section 3 for examples. 
* When in doubt look around; you should ***STAY CONSISTENT*** with the rest of the project. 

In order to keep things easy to read, and beginner friendly... 
* All classes, methods, and functions should include a docstring. (Sec. 4)
* Loop and control structures should have inline comments at each line. (Sec. 3)

## 2. Names

### Best Naming Practices
We use **descriptive**, and **concise** names (as they should be for all projects both public and private).
*  **Descriptive**: Names should accurately describe the entity they represent. 
*  **Concise**: Names should be as short as possible without extraneous abbreviation, or loss of meaning. 

"Function" in this section refers to a functions, methods, and generators as a group.

### Names of Structures and Data
Names should follow [Google Python](http://google.github.io/styleguide/pyguide.html?showone=Naming#Naming) convention. This means...
* **Classes** should be upper camel case, e.x. ```class MySuperCoolClass():```
* **Functions**: should be lowercase underscored, e.x. ```def my_function():``` 
* **Variables**: should be lowercase underscored, e.x. ```my_integer```

## 3. Comments
Some of our guidelines are contradictory to [PEP 8](https://www.python.org/dev/peps/pep-0008/#introduction) and [Google Python](http://google.github.io/styleguide/pyguide.html?showone=Comments#Comments) standards.
We deviate from these formats in an effort to remain **beginner friendly**.

### Inline Comments
We document all loop and control structures with inline comments. 
These comments should be indented at least 8 spaces after the end of the line. 
Indentation of the comment should match indentation of the line it describes. 
There should be a space after each '#', and the first letter of the comment should be captialized. 
Ex. 
```python
for i in range(self.days):        # Color a rectangle pr. completed day blue (from left to right).
    self.canvas.itemconfig(self.rectangle_list[i], fill = "blue")
    
new = randint(0, 9)        # Get a random integer between 0-9.
while new == self.current_greeting:        # Get a new random integer if new is the same as current_greeting.
    new = randint(0, 9)        # Get a new random integer between 0-9.
    ...
    
if self.user_type == 1:        # Display appropriate greeting for returning users.
    self.canvas.create_text(self.CANVAS_WIDTH/2, 20, text = "Good to see you again! Please enter your name")
elif self.user_type == 2:        # Display appropriate greeting for new users.
    self.canvas.create_text(self.CANVAS_WIDTH/2, 20, text = "Lets get you started! Please enter your name")
```

### Block Comments 
Block comments should be used to describe logical groupings of statements, if appropriate, but not loop or control structures.
They should be placed above the code block they describe, with a new line above itself and below the code block it describes. 
Ex. 
```python
# Attributes
self.root = Tk.Tk()
self.root.title("Welcome!")
self.choice = Tk.IntVar()

# Tkinter instantiation
self.canvas_layout()
self.input_buttons()
self.root.protocol("WM_DELETE_WINDOW", lambda: quit())
self.root.mainloop()

...
```

## 4. Docstrings
Docstrings should follow the [Google Python](http://google.github.io/styleguide/pyguide.html?showone=Comments#Comments) format.

### Docstring Format
Docstrings **must** immediately follow a class or function definition. 
There should be a new line immediately after the single line summary, and immediately before the first section (if there is additional info).

```
DOCSTRING FORMAT
KEY = [STUFF] = required data
<STUFF> = Data required if available
|STUFF| = optiondal data
[/] = new line
```
```python
def MyClass(object):
    """[Single line summary of class.]
    [/]
    |Additional info if relevant and useful.|
    |/|
    <Args:
        arg1: Description of parameter.
        ...>
    [/]
    <Attributes:
        attr1: Description of attribute. 
        ...>
    [/]
    <Returns:
        return_value: Data type and description of return_value.
        ...>
    [/]
    <Yields:
        yield_value: Description of yield_value. 
        ...>    
    """
```


### Single Line Summaries
Docstrings always begin with a single line summary. If you are having trouble writing a single line summary in a single line; the reason usually boils down to **"This X is too complicated."** 

Try these solutions...
1. **Describe *what* X represents or does, not what X *can* do or *how*.** 
2. **Refactor X into X and Y.** A good rule in programming is to have each *thing* do one, and only one thing. Classes should represent one object, and functions should accomplish one task. 

If you can't find a good way to do either; consider opening an issue about it, or commenting on it with your PR.
