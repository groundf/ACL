# ΛCL Programming Language

ΛCL is a concatenative programming language.

ACL is currently a command line application with plans for a GTK version to provide a GUI.

## Development

I am seeking experienced C programmers to join the project. Immediate needs are testing ACL in other environments and possibly joining as a developer. You can develop in any compatible environment.
If you are an expert C programmer, you can probably suggest improvements to my implementation. I welcome such suggestions. The file docs/coding.txt gives examples of coding in ACL. The file test/test.acl is a trivial example of how to create an ACL program. ACL programs are executed by `main(filename)`. The development language is C (99).

## Compilation

```shell
cmake -B build
```

```shell
cmalke --build build --config debug
```

```shell
cmake --build build --config release
```

## Credits

* Author: Don Groves
