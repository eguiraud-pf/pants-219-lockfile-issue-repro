## Repro for pants 2.19 generate lockfile issue

To reproduce:

```
pants generate-lockfiles
```
results in

```
11:10:45.65 [INFO] Completed: Generate lockfile for python-default
11:10:45.65 [ERROR] 1 Exception encountered:

Engine traceback:
  in `generate-lockfiles` goal

ProcessExecutionFailure: Process 'Generate lockfile for python-default' failed with exit code 1.
stdout:

stderr:
Expected matching RIGHT_PARENTHESIS for LEFT_PARENTHESIS, after version specifier
    cadquery (==master) ; extra == 'prod'
             ~^ 
```

When using 2.18 instead of 2.19 in `pants.toml`, the command runs correctly.
2.20 also seems to suffer from the same regression.
