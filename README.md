When there are two `main` modules in the source roots, `pants package` succeeds but running the pex fails.

```
# both have ambiguous `main.py` module as implicit dependency in entry_point
pants run foo:fails
pants run bar:fails
```

```
# using file name to another module works fine though
pants run bar:works
```
