# logging_temp
init
```python
import structlog

def setup_logging():
    """Sets up global logging configuration for the application."""
    structlog.configure(
        # ... your global configuration ...
    )

# Call this function at the start of your application.
setup_logging()

def get_logger(name):
    """Get a pre-configured logger."""
    return structlog.get_logger(name)
```

module
```python
from app_init import get_logger

# Get a logger and bind a custom field
logger = get_logger(__name__).bind(custom_field="custom_value")

def my_function():
    logger.info("Function called", event="my_function_invocation")
    # Your function logic here

# Example usage
if __name__ == "__main__":
    my_function()

```
