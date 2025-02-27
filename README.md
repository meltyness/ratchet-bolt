# ratchet-bolt
A command authorization client for Linux

> [!CAUTION]
> This is just a bit of exposition
> about how you could authorize Bash commands
> across a Linux fleet.

So ratchet provides a TACACS+ server,

TACACS+ defines a protocol facility for authorizing specific
sets of commands given a username.

Bash (a common command shell) has the following facilities:
- `trap`
```bash
trap '<command, program, etc>' DEBUG
```
- `extdebug`
[via the gnu bash docs](https://www.gnu.org/savannah-checkouts/gnu/bash/manual/bash.html#The-Shopt-Builtin)
> If set after invocation, behavior intended for use by debuggers is enabled:
> ...
> If the command run by the DEBUG trap returns a non-zero value,
> the next command is skipped and not executed.
> ...

So then with a simple client running on a Linux machine, commands could be forwarded
using TACACS+ to a server for inspection, logging, or authorization based on 
arbitrary policies.
