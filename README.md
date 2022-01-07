# bash-helpers
A repository for generic bash helpers to be sourced into other scripts

## Usage
In order to use any of these helpers in a bash script, simply add
```
source <(curl -s https://raw.githubusercontent.com/LeapYear/bash-helpers/main/path/to/helper.sh)
```
to the beginning of your script.

## Contents
### Logger

#### Description

This script provides logging functionality for bash scripts. It keys off of an environment variable named `LOG_LEVEL` with available values being
1. FATAL
2. SUCCESS
3. ERROR
4. WARN
5. INFO
6. DEBUG
7. TRACE

With the logging level increasing in the order shown above. By default, if the variable is not set, then the logger will assume a log level of `INFO`.

In addition, calling a log level of `FATAL` will automatically exit with status code 1 after displaying the message.

#### Usage

To write logs from inside your script, add the following line wherever you want logs printed out
```
_log "<desired log level for the message>" "Message to print"
```

For example, using
```
_log "INFO" "This is an example message"
```

would output
```shell
[INFO] :: This is an example message
```

NOTE: The logger outputs log level labels with specific colors, however the GitHub README is unable to display them. The following is the list of colors as they correspond to log level:

| Level     | Color  |
| --------- | ------ |
| `FATAL`   | red    |
| `SUCCESS` | green  |
| `ERROR`   | red    |
| `WARN`    | yellow |
| `INFO`    | green  |
| `DEBUG`   | cyan   |
| `TRACE`   | blue   |
