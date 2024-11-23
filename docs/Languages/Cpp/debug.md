# Debugging

When using `lldb` to debug you will need to run the compiler, g++ for me, with the `-g` flag to include debugging information in the binary.

When you then run `lldb` you can use the `run` command to execute the binary.

After a crash you can use the `bt` command to get a backtrace of the call stack.

If you need to run with arguments you can use the `run` command with arguments.

`frame select [int]` (puts focus on a frame in the stack trace)
`frame variable --show-types` (shows the vars in a frame)

`bt` - prints the backtrace
`breakpoint set --file [filename] --line [lineNumber]`
`breakpoint set --name [functionNameWithClass]`
`breakpoint list`
`step` / `s` - step into function
`next` / `n` - next line
`finish` / `f` - step out of func
`continue` / `c` - go till next breakpoint
