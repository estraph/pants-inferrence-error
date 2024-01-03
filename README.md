When there are two `main` modules in the source roots, `pants package` succeeds but running the pex fails.

```sh
# both have ambiguous `main.py` module as implicit dependency in entry_point
pants run foo:fails
pants run bar:fails
```

If the entry point is not ambiguous, pants successfully infers the dependency. If inference fails, pants silently creates an empty pex file.

```sh
# using file name to another module works fine though
pants run bar:works
```
