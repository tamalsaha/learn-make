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
```
var := $(shell find . -name "*.c")
```
- weird: https://www.gnu.org/software/make/manual/html_node/Appending.html#Appending

### What is the difference between the GNU Makefile variable assignments =, ?=, := and +=?

- https://stackoverflow.com/a/448939
- https://stackoverflow.com/q/2826029

### Lazy Set

    VARIABLE = value

Normal setting of a variable, but any other variables mentioned with the `value` field are recursively expanded with their value at the point at which the variable is used, not the one it had when it was declared

### Immediate Set

    VARIABLE := value

Setting of a variable with simple expansion of the values inside - values within it are expanded at declaration time.

### Lazy Set If Absent

    VARIABLE ?= value

Setting of a variable only if it doesn't have a value. `value` is always evaluated when `VARIABLE` is accessed. It is equivalent to

    ifeq ($(origin FOO), undefined)
      FOO = bar
    endif

See the [documentation](https://www.gnu.org/software/make/manual/html_node/Flavors.html#Flavors) for more details.


### Append
    VARIABLE += value

Appending the supplied value to the existing value (or setting to that value if the variable didn't exist)

## Functions
`Functions allow you to do text processing in the makefile to compute the files to operate on or the commands to use in recipes.`

- https://www.gnu.org/software/make/manual/html_node/Functions.html#Functions
- `shell` : https://www.gnu.org/software/make/manual/html_node/Shell-Function.html#Shell-Function

## Recursive calls of Make
- https://www.gnu.org/software/make/manual/html_node/MAKE-Variable.html#MAKE-Variable

