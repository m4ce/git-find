# Git find

A minimal GNU-style find implementation for Git. This utility allows for pattern searching in the Git history and optionally take actions over it.

Some examples:

# Delete all files greater than 1M from the history
```
git find --size +1M --delete
```

# Delete all files that match '*.gz' from the history
```
git find --name '*.gz' --delete
```

# Delete all files that match '*.txt' and are located within a 'reports' directory from the history
```
git find --name '*.gz' --path '*/reports/*' --delete
```

# You can also specify an arbitrary command to execute. The following variables will be interpolated: %{mode}, %{type}, %{sha}, %{size}, %{path}
```
git find --name '*.gz' --path '*/reports/*' --exec 'git cat-files %{type} %{sha}'
```

# Formatted output is implemented as follows
```
git find --printf '%{sha} %{path} %{size}'
```

and so forth.

## Installation

The script needs to be made available on your <u>PATH</u> in order for git to have <i>find</i> as an additional command-line action.

## Todo

1. Implement -type option
2. Implement find-alike expressions and operators (e.g. -name x -o -name y)

## Contact

Matteo Cerutti - matteo.cerutti@hotmail.co.uk
