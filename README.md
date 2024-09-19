# ByteMe Lexer

## Project Overview
This project is a lexer designed for a custom language (F24). The lexer reads the source code, processes keywords, operators, punctuation, and identifiers, and returns corresponding tokens. It uses `flex` to define lexical rules and process input.

## Repository URL
You can find the project repository at: [ByteMe GitHub](https://github.com/cojoda/ByteMe.git).

## How to Build and Run

### Prerequisites
- `flex` should be installed on your system.
- A C++ compiler (such as `g++` or `clang`) is required to compile the generated lexer code.

### Building the Lexer
To build the lexer, simply use the provided Makefile. Run the following command in the root directory of the project:

```bash
make
```

This will:
- Compile the `byte.cpp` file along with the other dependencies.
- Generate an executable that will process `.f24` source files.

Ah, I see! Let me adjust it:

---

### Running the Lexer
Once built, you can run the lexer on example files located in the `./example/` directory. For example, to process the `brain.f24` file and display the output, use the following command:

```bash
./bin/byte < ./example/brain.f24
```

If you'd like to save the output to a file, you can redirect it like this:

```bash
./bin/byte < ./example/brain.f24 > output.txt
```

You can replace `brain.f24` with `small.f24` or `mg.f24` to run other examples.

Replace `brain.f24` with `small.f24` or `mg.f24` to run other examples.

### Example Files
The project includes three example `.f24` files:
- `brain.f24`
- `small.f24`
- `mg.f24`

These are located in the `./example/` directory and are independent of other groups.

## Testing Environments
This project was tested using:
- **LLVM/Clang and Flex** from the macOS Xcode command line tools.
- **GCC and Flex** from the Pop!_OS

Both environments successfully built and executed the lexer.

## Flex and Yacc Information
The `flex` lexical analyzer is used in this project. If you need more information or want to download `flex`, you can find it at:  
- URL: https://github.com/cojoda/ByteMe.git

## Makefile
The provided `Makefile` automates the build process. It handles the compilation and linking steps for generating the lexer. You can find the Makefile in the project root directory.

### **Makefile Options**

1. **Default Build**: 
   By default, running `make` will build the lexer executable into the `bin/` directory. This is set with the following default target:
   ```bash
   make
   ```
   This will:
   - Compile the `byte.cpp` and `lexer.cpp` source files.
   - Create an executable named `byte` in the `bin/` directory.

2. **Clean**:
   To clean up the build directories and remove any generated files, you can use the following command:
   ```bash
   make clean
   ```
   This will remove the `bin/` and `obj/` directories, as well as the `lexer.cpp` file generated by `flex`.

3. **Test**:
   You can run a predefined test that processes the `mg.f24` file and outputs the result into a test directory (`./test/output.txt`):
   ```bash
   make test
   ```
   This will:
   - Ensure the lexer is built.
   - Create a `test/` directory.
   - Run the `byte` lexer on the `mg.f24` file and save the output to `test/output.txt`.

### Additional Notes:
- **Generated Files**: The lexer `.cpp` file is generated from `lexer.l` using the `flex` command.
- **Object Files**: Object files are compiled into the `obj/` directory.
- **Source Files**: Source files are located in the `src/` directory, and the binary is output to `bin/`.
