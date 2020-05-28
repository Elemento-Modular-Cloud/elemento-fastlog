# Elemento Fastlog
## Light weight C++ and Python logging library

The aim of Elemento Fastlog is to provide the users with a `printf` "extension", capable of representing colored log levels.
In addition the calls related to a log level lower than the one selected are removed by the compiler at compilation time, reducing code footprint in large projects.

### How to use in C++
Start by importing the single header `fastlog.h`.

To change the log level set the `fatlog::logLevel` value to one of the available values, defined in `fastlog::Level` enumerator.

The supported log levels are:
- `SILENT`: no output, everything disabled
- `ERROR`: only errors are shown
- `INFO`: informations and errors are shown
- `DEBUG`: debug messages, informations and errors are displayed

To use it follow the same way you are used to use `printf`, but add as first argument the log level using one of the keywords defined by the `fastlog::Level` enumerator.

```
  // The usual:
  printf("Error message %s", string.data());

 // Becomes:
  fastlog(ERROR,"Error message %s", string.data());)
```

An example of the log levels behavior is contained in `main.cpp`.

The tool is compatible with CMake and the whole folder cna be added as subdirectory to any CMake project.

### How to use in Python
Start importing `fastlog` from the `fastlog.py` module.

In addition to the standard levels, additional output levels are available in python.

The supported log levels are:
- `SILENT`
- `ERROR`
- `WARNING`
- `INFO`
- `DEBUG`
- `UI`

Excluding the log level argument, the method signature is the same as for the standard python `print` function.

```
  # The usual:
  print("Error message {}".format(string))

  # Becomes:
  fastlog(ERROR,"Error message {}".format(string))
```
