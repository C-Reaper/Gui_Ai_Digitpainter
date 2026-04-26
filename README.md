# Project README

## Overview
The project, named "Ai Digitpainter," is a simple graphical application that allows users to draw digits on the screen. It uses various libraries for rendering and input handling.

## Features
- Drawing numbers using mouse input.
- Displaying the current digit being drawn at the bottom of the window.

## Project Structure
```
 Ai Digitpainter/
├── build/              # Build output directory
│   ├── Main            # Executable file (Linux)
│   └── Main.exe        # Executable file (Windows)
├── src/
│   ├── Main.c          # Entry point and main logic
│   └── *.h             # Header files for functions, structures, and constants
├── Makefile.linux      # Linux build configuration
├── Makefile.windows    # Windows build configuration
├── Makefile.wine       # Wine (Linux to Windows) build configuration
└── Makefile.web        # Emscripten (WebAssembly) build configuration
```

## Prerequisites
- C/C++ Compiler and Debugger (GCC, Clang)
- Make utility
- Standard development tools
- Libraries needed in specific projects:
  - Linux: X11 for GUI, PNG/JPEG for image processing.
  - Windows: User32, GDI32, Winmm for GUI and multimedia functions.
  - WebAssembly: emcc (Emscripten) for compiling to JavaScript.

## Build & Run
### Building on Linux
To build the project on a Linux system:
```sh
cd Ai Digitpainter/
make -f Makefile.linux all
```

Run the executable:
```sh
make -f Makefile.linux exe
```

### Building on Windows
To build the project on a Windows system, you need to use MinGW and set up an appropriate shell environment (like Cygwin or MSYS2).

```sh
cd Ai Digitpainter/
make -f Makefile.windows all
```

Run the executable:
```sh
make -f Makefile.windows exe
```

### Building for WebAssembly
To build the project for web browsers using Emscripten:

1. Install Emscripten.
2. Navigate to the project directory and run:
    ```sh
    emcc src/Main.c -o build/index.html -s INITIAL_MEMORY=169082880 -s USE_SDL=0
    ```

To view the web application, open `build/index.html` in a web browser.

### Clean Build
To clean up and rebuild from scratch:
```sh
make -f Makefile.linux clean && make -f Makefile.linux all
```

Or for Windows:
```sh
make -f Makefile.windows clean && make -f Makefile.windows all
```

This README provides a clear overview of the project, its features, and how to build and run it on different platforms.