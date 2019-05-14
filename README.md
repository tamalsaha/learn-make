# learn-make

- https://opensource.com/article/18/8/what-how-makefile
- https://www.gnu.org/software/make/manual/html_node/Phony-Targets.html
- https://www.gnu.org/software/make/manual/html_node/Reading.html#Reading

## Receipe syntax
- https://www.gnu.org/software/make/manual/html_node/Recipe-Syntax.html#Recipe-Syntax
> Each line in the recipe must start with a tab (or the first character in the value of the .RECIPEPREFIX variable; see Special Variables), except that the first recipe line may be attached to the target-and-prerequisites line with a semicolon in between. Any line in the makefile that begins with a tab and appears in a “rule context” (that is, after a rule has been started until another rule or variable definition) will be considered part of a recipe for that rule. Blank lines and lines of just comments may appear among the recipe lines; they are ignored.

> A blank line that begins with a tab is not blank: it’s an empty recipe (see Empty Recipes).

> A comment in a recipe is not a make comment; it will be passed to the shell as-is. Whether the shell treats it as a comment or not depends on your shell.

## How make Reads a Makefile
- https://www.gnu.org/software/make/manual/html_node/Reading-Makefiles.html#Reading-Makefiles

## Sub shell for each receipe:
- https://www.gnu.org/software/make/manual/html_node/Execution.html#Execution

> this implies that setting shell variables and invoking shell commands such as cd that set a context local to each process will not affect the following lines in the recipe.2 If you want to use cd to affect the next statement, put both statements in a single recipe line. Then make will invoke one shell to run the entire line, and the shell will execute the statements in sequence.

## Debugging
- https://www.gnu.org/software/make/manual/html_node/Echoing.html#Echoing

```
make -n
```

## Variables
- https://www.gnu.org/software/make/manual/html_node/Flavors.html#Flavors
- https://www.gnu.org/software/make/manual/html_node/Environment.html#Environment

## Functions
`Functions allow you to do text processing in the makefile to compute the files to operate on or the commands to use in recipes.`

- https://www.gnu.org/software/make/manual/html_node/Functions.html#Functions
- `shell` : https://www.gnu.org/software/make/manual/html_node/Shell-Function.html#Shell-Function


