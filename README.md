# learn-make

- https://opensource.com/article/18/8/what-how-makefile
- https://www.gnu.org/software/make/manual/html_node/Phony-Targets.html
- https://www.gnu.org/software/make/manual/html_node/Reading.html#Reading


Sub shell for each receipe:
- https://www.gnu.org/software/make/manual/html_node/Execution.html#Execution

> this implies that setting shell variables and invoking shell commands such as cd that set a context local to each process will not affect the following lines in the recipe.2 If you want to use cd to affect the next statement, put both statements in a single recipe line. Then make will invoke one shell to run the entire line, and the shell will execute the statements in sequence.

Debugging
- https://www.gnu.org/software/make/manual/html_node/Echoing.html#Echoing

```
make -n
```
