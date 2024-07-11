---
id: wji3bt37h681uou8fn7sp2j
title: 012 - Flowcharts for Debugging
desc: ''
updated: 1720709905751
created: 1720709053162
---

Flowcharts **can help** `visualize` **the** `process` **and** `identify` `areas` `for improvement`. Below are two flowcharts that address debugging:

```plaintext
    Start
      |
      v
Run Code to Identify Errors
      |
      v
Check for Syntax Errors
      |
      v
Syntax Error? ---> Yes ---> Fix Syntax Errors
      |                             |
     No                             v
      |                        Re-run Code
      v
Check for Runtime Errors
      |
      v
Runtime Error? ---> Yes ---> Use Debugger to Trace Error
      |                                 |
     No                                 v
      |                         Fix Runtime Errors
      |                                 |
      v                                 v
Check for Logical Errors           Re-run Code
      |
      v
Logical Error? ---> Yes ---> Use Console Logs/Breakpoints
      |                                 |
     No                                 v
      |                         Fix Logical Errors
      v                                 |
    Code Runs without Errors <----------+
      |
      v
     End
```

1. **Run Code to Identify Errors**: Start by running your code to see where errors occur.
2. **Check for Syntax Errors**: Syntax errors are the easiest to spot and should be `fix`ed `first`.
3. **Check for Runtime Errors**: `Use` tools like a `debugger` to find runtime errors.
4. **Check for Logical Errors**: These are errors in the logic of your code that require `careful` `tracing and understanding of` the `code flow`.