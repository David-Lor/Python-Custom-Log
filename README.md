# Python-Custom-Log

My custom Python logging library, working with "transactions". It works with the native logging library. Can store logs in local files, SQLite DB and use custom functions.

This library is focused on logging functions and methods. When something goes wrong inside a function, the logger can save ALL the logs defined on the function to a file. When everything works OK, the logs can be avoided.

## Example

```python
from customlog import CustomLog

# TODO add customlog initialization

def divide(a, b):
    log = logger.Transaction()
    log.debug("We divide {}/{}".format(a,b))
    try:
        r = a / b
    except (TypeError, ZeroDivisionError):
        log.exception("Something went wrong")

print(divide(10,2)) # Nothing will be logged

print(divide(0/0)) # debug and exception will be logged

```
