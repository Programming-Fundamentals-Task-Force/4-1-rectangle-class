# Assignment 4-1: Rectangle Class

## Creating a new project from VS Code

1. Start VS Code in the project directory.
2. Press Ctrl + Shift + P (Mac: Cmd + Shift + P) to open Command Palette.
3. Select "Java: Create Java Project..." (You can find the command by typing part of the command in the search box.)
4. Select "Maven" for the project type.
5. Select "maven-archetype-quickstart" for the archetype.
6. Select "1.5" for the version of maven-archetype-quickstart.
7. When asked for _group Id_, enter "com.lab". This will be the package name of your project.
8. When asked for _artifact Id_ (this is the project name), enter a name following these examples:
	- For Lab Assignment 3-2, the artifact Id should be "lab32".
	- For Lab Assignment 10-1, the artifact Id should be "lab101".
	- For Homework 4-3, the artifact Id should be "hw43".
9. File browser will pop up for folder selection. Accept the default by pressing Enter.
10. Terminal will show the prompt "Define value for property 'version'", asking for the initial version of the project. Default is "1.0-SNAPSHOT". You may press Enter to accept the default, or type in a version you want, e.g., "0.1-ALPHA" or just "1.0".
11. Maven will show the current configuration and ask for confirmation. Review and enter "y" (or just press Enter) to accept it, or "n" to change some properties. You may want to change "javaCompilerVersion" to "21".
12. The project folder should be successfully created. You can now press Enter at the terminal to close it.

### Notes

- Maven archetypes are configurable starting templates that provide the project directory structure, starting code, and `pom.xml` which contains the project configuration.
- If "maven-archetype-quickstart" version "1.5" is not available, start over (press ESC then Ctrl + Shift + P again) and select "Maven: Update Maven Archetype Catalog".
- All the property settings can be changed later in the file `pom.xml` inside the project directory.
- Source code will be in `src/main/java/com/lab/`.

If you don't want to use VS Code to generate Maven projects, you can use the command line:

```
mvn archetype:generate -DarchetypeGroupId=org.apache.maven.archetypes -DarchetypeArtifactId=maven-archetype-quickstart -DarchetypeVersion=1.5
```

For PowerShell, some command line parameters need to be quoted, like this:

```
mvn archetype:generate "-DarchetypeGroupId=org.apache.maven.archetypes" "-DarchetypeArtifactId=maven-archetype-quickstart" "-DarchetypeVersion=1.5"
```

## Compiling with Maven

Compiled class files will be in `target/classes` directory by default.

### From VS Code

- Open Command Palette.
- Select "Maven: Execute Commands..."
- Select "compile" as the goal to execute.

### From command line

- Change to the project directory (e.g., lab41).
- Enter:
```
mvn compile
```

## Building a distributable package

- Use "Maven: Execute Commands..." -> "package" in VS Code or enter `mvn package` at the command line prompt.
- A JAR file will be created in the `target` directory.

## Running the program

- In The starting class is `App` by default. We can invoke it using the class name with its package name: `com.lab.App`
- We can run the program both from a compiled class file, or from a JAR package file.
- We need to provide the class path, which is either `target/classes` or the path to the JAR file.

Example:

```
java -cp target/classes com.lab.App
```

Or (if the package name is `lab41-1.0-SNAPSHOT.jar`):

```
java -cp target/lab41-1.0-SNAPSHOT.jar com.lab.App
```

## Instructions

Create a `Rectangle` class which will be used to represent rectangle dimensions. For now, we will not handle their positions yet, as the purpose of this assignment is to learn how to use Maven.

## The `Rectangle` class should include the following methods:

- `public Rectangle(double width, double height)`
  A constructor that takes the width and height as parameters.

- `public Rectangle(double width)`
  A constructor that takes the width as the parameter and creates a square object.

- `public Rectangle()`
  A constructor that takes no parameters and creates a unit square object (square with dimensions of 1).

- `public double area()`
  Returns the area of the rectangle.

- `public bool isSquare()`
  Returns `true` if the rectangle is a square.

## Output requirements

You can write a `main()` method in the `App` class to test the `Rectangle` class. However, this assignment is graded on the correctness of the `Rectangle` class, so you can implement the `main()` method however you want it.

However, you MUST strictly follow the instruction on how to use Maven, especially on the package name (`com.lab`). Otherwise, the code will not be graded correcly.