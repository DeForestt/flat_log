# flat_log

`flat_log` is a lightweight and configurable logging library for AFlat, designed to streamline logging and debugging processes in your applications. It supports multiple log levels, outputs formatted logs, and integrates with environment variables to dynamically adjust the logging behavior.

---

## Features

- **Log Levels:** Supports `Debug`, `Info`, `Warn`, and `Error` levels to categorize logs.
- **Singleton Logger:** Ensures a single instance of the logger, preventing redundant memory usage.
- **Formatted Logs:** Logs are timestamped for better traceability.
- **Environment Configuration:** Reads the default log level from the `LOG_LEVEL` environment variable.
- **Convenient API:** Provides simple helper functions for each log level.

---

## Installation

Install using the aflat compiler:

```bash
aflat install http://github.com/DeForestt/flat_log
```

### Example Import

```aflat
import { getLogger, info, debug, warning, error } from "./src/flat_log" under log;
```

---

## Usage

### Setting Up the Logger

The logger is automatically initialized as a singleton. By default, it reads the `LOG_LEVEL` environment variable to set the logging level. If the variable is not set, it defaults to `INFO`.

Example:

```bash
export LOG_LEVEL="DEBUG"
```

### Logging Messages

Log messages at various levels using the helper functions. Always use your custom namespace (e.g., `log`) for clarity and consistency.

#### Info
Logs informational messages:
```aflat
log.info("Application started successfully.");
```

#### Debug
Logs detailed debugging information:
```aflat
log.debug(`Debugging value: {value}`);
```

#### Warning
Logs warnings about potential issues:
```aflat
log.warning("Disk space running low.");
```

#### Error
Logs critical errors:
```aflat
log.error("Unable to connect to the database.");
```

### Example

```aflat
import { info, debug, warning, error } from "./src/flat_log" under log;

log.info("Service initialized.");
log.debug("Processing request...");
log.warning("API rate limit approaching.");
log.error("Fatal error: Unable to authenticate.");
```

Output example:
```
[2024-11-22 10:15:30] [INFO] Service initialized.
[2024-11-22 10:15:31] [DEBUG] Processing request...
[2024-11-22 10:15:32] [WARNING] API rate limit approaching.
[2024-11-22 10:15:33] [ERROR] Fatal error: Unable to authenticate.
```

---

## API Reference

### Exports

#### `Logger getLogger()`
- Retrieves the singleton logger instance.

#### `bool info(string message)`
- Logs an informational message.

#### `bool debug(string message)`
- Logs a debugging message.

#### `bool warning(string message)`
- Logs a warning message.

#### `bool error(string message)`
- Logs an error message.

---

## Log Levels

The library defines the following log levels:

| Level   | Description                           |
|---------|---------------------------------------|
| `DEBUG` | Detailed debugging information.       |
| `INFO`  | General information about operations. |
| `WARN`  | Warnings about potential issues.      |
| `ERROR` | Critical errors that need attention.  |

---

## Configuration

The logger reads the `LOG_LEVEL` from the system environment variables. Possible values include:
- `DEBUG`
- `INFO`
- `WARNING`
- `ERROR`

If `LOG_LEVEL` is not set, the default level is `INFO`.

---

## Contributing

Feel free to contribute to this library by improving its functionality or adding new features. Pull requests and issues are welcome.

---

## License

This library is open-sourced and licensed under the MIT License.