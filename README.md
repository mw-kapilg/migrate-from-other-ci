# signal-utils

Small MATLAB utilities for unit conversion and signal smoothing.

- `src/` — library functions
- `tests/` — unit tests (MATLAB unit testing framework)

Run the tests locally from the repository root:

```matlab
addpath("src")
results = runtests("tests")
```

CI runs on our Jenkins server (agents labelled `linux-matlab`, MATLAB
R2026a) — see `Jenkinsfile`.
