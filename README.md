## Project: Logger

## Overview
---
Logger is a tool for easily measuring the number of times functions or class methods are called and their execution time when writing Python code.

## Description
---
The Logger class can be used simply by importing it. It can also be turned OFF during operation to minimize impact on performance.

This project consists of three main parts:

- Logger.py: Provides the Logger class.  
    The 'log_calls' method counts the number of function calls and the 'timer' method measures the execution time of the function.

- analyze.py: Provides the 'analyze_logs' function to analyze log data.

- demo.py: Demonstrates usage examples of the above class and function.

## USAGE
---
### Log Embedding  
To add log functionality to functions or methods, use Logger's methods as decorators.

```py
@Logger.timer
@Logger.log_calls
def slow_function():
    time.sleep(1)
```

### During Development
By setting Logger's enabled to True and the mode to 'memory', log information is saved in memory. If needed, you can also output log information to a text file.

```py
Logger.enabled = True
Logger.mode = 'memory'  # ログをテキストに出力
slow_function()
Logger.write_logs()
```

### Log Analysis  
Log file analysis is done using the 'analyze_logs' function in the analyze module.  

```py
import analyze
analyze.analyze_logs(filename)
```

### During Operation  
In the operating environment, Logger is set to OFF to minimize the impact on performance. From then on, Logger's methods will not output anything.  

```py
Logger.enabled = False
# これ以降はログは作成されない
```

### Latest Version
v1.0 (2023-06-18)

New data analysis features have been added, logging functions have been improved, and new demonstration examples have been added. For more details, please check the [release notes](link to the release notes).

## Requirement
---
To run this project, you need Python 3.11.2 and the following Python libraries:

- matplotlib 3.7.1

## Licence
---
This project is available under the[MIT](LICENSE) license.

## Author
---
[kumab2221](https://github.com/kumab2221)

## Acknowledgements
---
This project expresses gratitude to the open source community, especially to the Python language and its wonderful ecosystem.