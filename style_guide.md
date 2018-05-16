# Style Guide

## What is this?
This is a set of guidelines on how to *style* code you plan on contributing to the prog-o-meter repository. You don't have to follow each, or any of them, but it may take your PR longer to get merged if someone else has to rewrite and document your code.

## Why is this useful? 
When everybody is on the same page, everyone writes better code. The purpose of the prog-o-meter project is too get newcomers out of their shell and excited to start learning, and feel confident contributing to the open source community. The faster everyone starts getting comfortable the better the project will be.

## 1. Quick Start
These are some quick guidelines and principles that this project follows. 

In general...
* **Structure** should follow the [PEP 8](https://www.python.org/dev/peps/pep-0008/#introduction) format.
* **Docstrings** should follow the [Google Python](http://google.github.io/styleguide/pyguide.html?showone=Comments#Comments) format. (Sec. 3)
* Code and comments should be kept **beginner friendly**. Purpose and diction should be easy to understand. (Sec. 4)
* When in doubt look around; you should ***STAY CONSISTENT*** with the rest of the project. 

In order to keep things beginner friendly... 
* All classes, methods, and functions should include a docstring. (Sec. 3)
* Loop and control structures should be documented at each line. (Sec. 4)

## 2. Names

### Best Naming Practices
Names should be **descriptive**, and **concise**.
*  **Descriptive**: Names should accurately describe the entity they represent. 
*  **Concise**: Names should be as short as possible without extraneous abbreviation, or loss of meaning. 

"Function" in this section refers to a functions, methods, and generators as group.

### Names of Structures and Data
Names should follow [Google Python](http://google.github.io/styleguide/pyguide.html?showone=Naming#Naming) convention. Simply put...
* **Classes** should be upper camel case, e.x. ```class MySuperCoolClass():```
* **Functions**: should be lowercase underscored, e.x. ```def my_function():``` 
* **Variables**: should be lowercase underscored, e.x. ```my_integer```

## 3. Comments
Some of our guidelines are contradictory to [PEP 8](https://www.python.org/dev/peps/pep-0008/#introduction) and [Google Python](http://google.github.io/styleguide/pyguide.html?showone=Comments#Comments) standards.
We deviate from these formats in an effort to remain **beginner friendly**.

### Inline Comments
You should document all loop and control structures with inline comments. 
These comments should be indented at least 8 spaces after the end of the line, and the indentation for each check and statement should match. 
Indentation should match with tier i.e. in for-while loop; the for comment should be 4 spaces leftward of while comment. 
There should be a space after each '#', and the first letter of the comment should be captialized. 
Ex. 
```python
while self.isAlive is True:                # While person is alive
    if self.age < 6 or self.isRetired:         # If too old or young
        stay_home()                                # Stay home
    elif self.age < 18:                        # Else if school age
        goto_school()                              # Goto school
    else:                                      # Otherwise
        goto_work()                                # Goto work
```

### Block Comments 
Block comments should be used to describe logical groupings of statements, if appropriate, but not loop or control structures. 
They should be placed above the code block they describe, with a new line above itself and below the code block it describes. 
Ex. 
```python
# Do the work
work_it_harder()
make_it_better()
do_it_faster()
makes_us_stronger()

# Ramble on afterwards
more_than_ever()
hour_after()
our_work_is()
never_over()

end_song()
```
## 4. Docstrings
Docstrings should follow the [Google Python](http://google.github.io/styleguide/pyguide.html?showone=Comments#Comments) format.

### Single Line Summaries
If you are having trouble writing a single line summary in a single line; the reason usually boils down to **"This X is too complicated."** 

Try these solutions...
1. **Describe *what* X represents or does, not what X *can* do or *how*.** 
2. **Refactor X into X and Y.** A good rule in programming is to have each *thing* do one, and only one thing. Classes should represent one object, and functions should accomplish one task. 

If you can't find a good way to do either; consider opening an issue about it, or commenting on it with your PR.

### Docstring Format
Docstrings **must** immediately follow a class or function definition. 
There should be a new line immediately after the single line summary, and immediately before the first section (if there is additional info).

```
DOCSTRING FORMAT
KEY = [STUFF] = required data, <STUFF> = Data required if available, |STUFF| = optiondal data, [/] = new line
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
