---
title: "Error Handling Functions"
read_time: "1 min"
updated: "mar 31, 2015"
group: "articles"
permalink: "/tutorials/error-handling.html"
---
These are functions dealing with error handling and logging. They allow you to define your own error handling rules, as well as modify the way the errors can be logged. This allows you to change and enhance error reporting to suit your needs.

Using these logging functions, you can send messages directly to other machines, to an email, to system logs, etc., so you can selectively log and monitor the most important parts of your applications and websites.

##Installation:

The error and logging functions are part of the PHP core. There is no installation needed to use these functions.

##Runtime Configuration:

The behaviour of these functions is affected by settings in php.ini. These settings are defined below.

| Name                   | Default | Changeable  | Changelog                                                  |
|------------------------|---------|-------------|------------------------------------------------------------|
| error_reporting        | NULL    | PHP_INI_ALL |                                                            |
| display_errors         | 1       | PHP_INI_ALL |                                                            |
| display_startup_errors | 0       | PHP_INI_ALL | Available since PHP 4.0.3.                                 |
| log_errors             | 0       | PHP_INI_ALL |                                                            |
| log_errors_max_len     | 1024    | PHP_INI_ALL | Available since PHP 4.3.0.                                 |
| ignore_repeated_errors | 0       | PHP_INI_ALL | Available since PHP 4.3.0.                                 |
| ignore_repeated_source | 0       | PHP_INI_ALL | Available since PHP 4.3.0.                                 |
| report_memleaks        | 1       | PHP_INI_ALL | Available since PHP 4.3.0.                                 |
| track_errors           | 0       | PHP_INI_ALL |                                                            |
| html_errors            | 1       | PHP_INI_ALL | PHP_INI_SYSTEM in PHP <= 4.2.3. Available since PHP 4.0.2. |
| docref_root            |         | PHP_INI_ALL | Available since PHP 4.3.0.                                 |
| docref_ext             |         | PHP_INI_ALL | Available since PHP 4.3.2.                                 |
| error_prepend_string   | NULL    | PHP_INI_ALL |                                                            |
| error_append_string    | NULL    | PHP_INI_ALL |                                                            |
| error_log              | NULL    | PHP_INI_ALL |                                                            |
| warn_plus_overloading  | NULL    |             | This option is no longer available as of PHP 4.0.0         |


##PHP Error and Logging Constants:

**PHP**: indicates the earliest version of PHP that supports the constant.

You can use any of the constant while configuring your php.ini file.

| Value | Constant            | Description                                                                                                               | PHP |
|-------|---------------------|---------------------------------------------------------------------------------------------------------------------------|-----|
| 1     | E_ERROR             | Fatal run-time errors. Errors that cannot be recovered from. Execution of the script is halted                            |     |
| 2     | E_WARNING           | Non-fatal run-time errors. Execution of the script is not halted                                                          |     |
| 4     | E_PARSE             | Compile-time parse errors. Parse errors should only be generated by the parser                                            |     |
| 8     | E_NOTICE            | Run-time notices. The script found something that might be an error, but could also happen when running a script normally |     |
| 16    | E_CORE_ERROR        | Fatal errors at PHP startup. This is like an E_ERROR in the PHP core                                                      | 4   |
| 32    | E_CORE_WARNING      | Non-fatal errors at PHP startup. This is like an E_WARNING in the PHP core                                                | 4   |
| 64    | E_COMPILE_ERROR     | Fatal compile-time errors. This is like an E_ERROR generated by the Zend Scripting Engine                                 | 4   |
| 128   | E_COMPILE_WARNING   | Non-fatal compile-time errors. This is like an E_WARNING generated by the Zend Scripting Engine                           | 4   |
| 256   | E_USER_ERROR        | Fatal user-generated error. This is like an E_ERROR set by the programmer using the PHP function trigger_error()          | 4   |
| 512   | E_USER_WARNING      | Non-fatal user-generated warning. This is like an E_WARNING set by the programmer using the PHP function trigger_error()  | 4   |
| 1024  | E_USER_NOTICE       | User-generated notice. This is like an E_NOTICE set by the programmer using the PHP function trigger_error()              | 4   |
| 2048  | E_STRICT            | Run-time notices. PHP suggest changes to your code to help interoperability and compatibility of the code                 | 5   |
| 4096  | E_RECOVERABLE_ERROR | Catchable fatal error. This is like an E_ERROR but can be caught by a user defined handle (see also set_error_handler())  | 5   |
| 8191  | E_ALL               | All errors and warnings, except of level E_STRICT                                                                         | 5   |

##List of Functions

**PHP**: indicates the earliest version of PHP that supports the function.

| Function                    | Description                                                                  | PHP |
|-----------------------------|------------------------------------------------------------------------------|-----|
| debug_backtrace()           | Generates a backtrace                                                        | 4   |
| debug_print_backtrace()     | Prints a backtrace                                                           | 5   |
| error_get_last()            | Gets the last error occurred                                                 | 5   |
| error_log()                 | Sends an error to the server error-log, to a file or to a remote destination | 4   |
| error_reporting()           | Specifies which errors are reported                                          | 4   |
| restore_error_handler()     | Restores the previous error handler                                          | 4   |
| restore_exception_handler() | Restores the previous exception handler                                      | 5   |
| set_error_handler()         | Sets a user-defined function to handle errors                                | 4   |
| set_exception_handler()     | Sets a user-defined function to handle exceptions                            | 5   |
| trigger_error()             | Creates a user-defined error message                                         | 4   |
| user_error()                | Alias of trigger_error()                                                     | 4   |