# Java Menu-Driven GUI

A Java Swing desktop application developed for a Programming II coursework assignment at Colorado State University Global. The project demonstrates menu-driven graphical user interfaces, event handling, file input/output, and dynamic interface customization.

## Project Overview

This application provides a graphical user interface with a menu containing four interactive options. Users can display the current date and time, save text to a local file, change the application's background color, and exit the program.

The project builds upon introductory Java GUI development by introducing menu components, file-writing operations, and dynamically generated colors.

## Features

- Graphical user interface built using Java Swing
- Menu bar with four interactive options
- Display the current date and time
- Save text area contents to a local log file
- Generate random dark-green background colors
- Display the RGB values of the selected background color
- Scrollable text area for application output
- Exit the application through the menu

## Technologies Used

- **Java** — Application logic and event handling
- **Java Swing** — Graphical user interface components
- **Java AWT** — Layout management and color customization
- **Java Time API** — Current date and time retrieval
- **Java File I/O** — Writing application output to a text file

## Application Functionality

### 1. Show Date/Time

Selecting **Options → Show Date/Time** retrieves the current system date and time using Java's `LocalDateTime` class.

The result is appended to the application's text area.

Example output:

```text
Date/Time: 2026-05-01T14:30:45.123
```

The displayed value depends on the system's current date and time.

### 2. Save to File

Selecting **Options → Save to File** writes the current contents of the text area to a file named `log.txt`.

The application uses Java's `FileWriter` class with append mode enabled.

This means:

- The file is created if it does not already exist.
- Existing file contents are preserved.
- New output is appended rather than replacing previous content.
- The application displays a confirmation message after saving.

The log file is generated in the application's working directory.

Because the program saves the entire text area each time, previously displayed text may appear more than once in the log after multiple saves.

### 3. Change Background Color

Selecting **Options → Change Background Color** generates a random dark-green color using RGB values.

The application uses Java's `Math.random()` method to generate color components within predefined ranges:

- **Red:** 0–39
- **Green:** 80–139
- **Blue:** 0–29

The generated color is applied to the text area's background, and its foreground text color is set to white for readability.

The selected RGB values are also displayed in the text area.

Example output:

```text
Background changed to RGB(15, 112, 8)
```

### 4. Exit

Selecting **Options → Exit** closes the application.

## Programming Concepts Demonstrated

### Graphical User Interfaces

The application uses Java Swing components to create an interactive desktop interface.

Components include:

- `JFrame` — Main application window
- `JMenuBar` — Menu bar
- `JMenu` — Options menu
- `JMenuItem` — Individual menu commands
- `JTextArea` — Displays application output
- `JScrollPane` — Provides scrolling functionality

### Event-Driven Programming

Each menu item uses an action listener to execute code when selected.

This demonstrates how Java applications respond to user interactions rather than following a strictly sequential console-based execution flow.

### File Input/Output

The application demonstrates basic file-writing operations using `FileWriter`.

A `try/catch` block handles errors that may occur during the save operation.

### Random Number Generation

The application uses `Math.random()` to generate RGB color values.

These values are used to construct a `Color` object and dynamically update the graphical interface.

### Date and Time

The application uses `LocalDateTime.now()` to retrieve the current system date and time.

## Project Structure

```text
java-menu-driven-gui/
├── src/
│   └── UserInterfaceApp.java
├── .gitignore
├── LICENSE
└── README.md
```

The `log.txt` file is generated when the application saves output and is excluded from version control.

## How to Run

### Requirements

- Java Development Kit (JDK)
- Desktop environment capable of displaying Java Swing windows
- Terminal or command prompt

### Instructions

1. Clone or download the repository.

2. Open a terminal in the repository's root directory.

3. Compile the Java source file:

   ```bash
   javac src/UserInterfaceApp.java
   ```

4. Run the application:

   ```bash
   java -cp src UserInterfaceApp
   ```

5. The application window will open.

### Using the Application

1. Open the **Options** menu at the top of the window.
2. Select **Show Date/Time** to display the current date and time.
3. Select **Change Background Color** to generate a new dark-green background.
4. Select **Save to File** to save the text area's contents to `log.txt`.
5. Select **Exit** to close the application.

## Example Output

After selecting the date/time and background color options, the text area might display:

```text
Date/Time: 2026-05-01T14:30:45.123
Background changed to RGB(15, 112, 8)
Content saved to log.txt
```

The actual date, time, and RGB values will vary.

## Current Limitations

This project represents an introductory implementation of a menu-driven Java desktop application.

The current version has several limitations:

- The application uses a fixed initial window size.
- File output is saved to a predefined filename rather than a user-selected location.
- Repeated save operations may duplicate previously saved text.
- File-writing errors display a general message rather than detailed diagnostic information.
- The application does not provide options to open or load previously saved log files.
- The interface uses a basic layout without advanced styling or customization controls.

These limitations reflect the educational scope of the original assignment rather than a production-ready desktop application.

## Educational Context

This application was developed for a Programming II assignment at Colorado State University Global.

The project demonstrates progression from basic Java graphical interfaces to menu-driven applications incorporating event handling, file operations, and dynamic visual changes.

Key learning objectives include:

- Creating menu bars and menu items using Java Swing
- Implementing event listeners for menu selections
- Working with text areas and scroll panes
- Retrieving the current system date and time
- Writing application output to a local text file
- Generating random RGB color values
- Updating graphical interface components dynamically
- Organizing application behavior within a Java class

The original coursework structure and pseudocode have been preserved to demonstrate programming progression throughout the degree program.

## License

This project is licensed under the MIT License. See [LICENSE](LICENSE) for details.
