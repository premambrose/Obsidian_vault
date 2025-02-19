**Single-line comments:**

- Use `//` to start a single-line comment.
- Single-line comments can be placed on the same line as code or on a separate line.

Example:

```c
int x = 10;  // This is a single-line comment on the same line as code.

// This is a single-line comment on a separate line.
```

**Multi-line comments:**

- Use `/* */` to start and end a multi-line comment.
- Multi-line comments can span multiple lines and can include multiple paragraphs.

Example:

```c
/*
This is a multi-line comment.
It can span multiple lines and include multiple paragraphs.

Here is another paragraph.
*/
```

**Function comments:**

- Use comments to describe the purpose of a function, its inputs, and its outputs.
- Use comments to describe any assumptions or limitations of the function.
- Use a consistent format for function comments, such as Doxygen or Javadoc style.

Example:

```c
/**
 * Calculates the sum of two integers.
 *
 * @param a The first integer.
 * @param b The second integer.
 * @return The sum of a and b.
 */
int sum(int a, int b) {
    return a + b;
}
```

**File comments:**

- Use comments at the beginning of a file to describe its purpose and contents.
- Include information such as the author, date, and version number of the file.
- Use a consistent format for file comments, such as Doxygen or Javadoc style.

Example:

```c
/**
 * @file main.c
 *
 * This file contains the main function for the project.
 *
 * @author John Smith
 * @date 2021-10-01
 * @version 1.0
 */
```


**TODO comments:**

- Use `TODO` comments to mark areas of code that need to be completed or improved.
- Include a description of the task that needs to be done and any relevant information.

Example:

```c
// TODO: Implement error handling for this function.
int my_function() {
    // Function code here.
}
```

**FIXME comments:**

- Use `FIXME` comments to mark areas of code that contain bugs or errors.
- Include a description of the problem and any relevant information.

Example:

```c
// FIXME: This function crashes when the input is negative.
int my_function(int x) {
    // Function code here.
}
```

**NOTE comments:**

- Use `NOTE` comments to provide additional information about the code.
- Include a brief description of the note and any relevant information.

Example:

```c
// NOTE: This function assumes that the input is positive.
int my_function(int x) {
    // Function code here.
}
```

**DEBUG comments:**

- Use `DEBUG` comments to mark areas of code that are only used for debugging purposes.
- Include a description of the debugging code and any relevant information.

Example:

```c
// DEBUG: Print the value of x for debugging purposes.
printf("x = %d\n", x);
```


**HACK comments:**

- Use `HACK` comments to mark areas of code that contain temporary or hacky solutions to problems.
- Include a description of the problem and the temporary solution.

Example:

```c
// HACK: This code is a temporary solution to a bug in the library.
// It needs to be replaced with a more robust solution in the future.
int my_function() {
    // Function code here.
}
```

**INFO comments:**

- Use `INFO` comments to provide additional information about the code or its usage.
- Include a brief description of the information and any relevant details.

Example:

```c
// INFO: This function is only used in the testing module and should not be called directly.
int my_function() {
    // Function code here.
}
```

**WARN comments:**

- Use `WARN` comments to mark areas of code that could cause problems or unexpected behavior.
- Include a description of the potential problem and any relevant details.

Example:

```c
// WARN: This function modifies global state and should be used with caution.
int my_function() {
    // Function code here.
}
```

**IDE comments:**

- Use IDE-specific comments to provide information or instructions to the IDE.
- Include the name of the IDE and any relevant information.

Example:

```c
// Visual Studio: This code requires the "my_library" project to be added to the solution.
#include "my_library.h"
```
