# NIH Test Tool

`ntt` the NIH Test Tool is a simple driver aimed to help testing programs
by comparing the outputs (standard, error and status) of an execution with
expected results.

A simple execution is

    ntt prog
    
which will execute `prog` with its standard input coming from `prog.in` in
the current directory (or `/dev/null` if it doesn't exist) and compare its
result with `prog.out` and `prog.err` (either may not exist, in which case
they are assumed to be empty). If an non null status is expected, the last
line of `prog.err` must be something like

    status 1

`ntt` accepts some arguments:

- `-d <dir>` will look for `prog.in`, `prog.out` and `prog.err` in `<dir>`.
- `-n name` will use `name.in`, `name.out` and `name.err` for files.
