# Nix Python package template

Minimal flake template showing how to package a Python application from PyPI
with `python3Packages.buildPythonApplication`. The checked-in example builds
`pip-hello-world` version `0.1`.

## Try the example

```bash
git clone https://github.com/RevolunixOS/pkg-python3Packages.template.git
cd pkg-python3Packages.template
nix build
nix run
```

## Create a package from the template

1. Update `pname` and `version` in `package.nix`.
2. Choose `fetchPypi` or the commented `fetchFromGitHub` source.
3. Replace the source hash. A first build with a fake hash will print the
   expected value.
4. Add build and runtime dependencies to `nativeBuildInputs`, `buildInputs`, or
   `propagatedBuildInputs` as appropriate.
5. Enable and configure tests instead of retaining `doCheck = false`.
6. Correct the description, homepage, license metadata, and main program.
7. Run `nix build`, `nix run`, and `nix fmt`.

## Files

```text
flake.nix    x86_64-linux package output and formatter
package.nix  Python package derivation
default.nix  non-flake callPackage entry point
```

This is a learning template, not a generic generator. Python projects using
Poetry, Hatch, compiled extensions, custom test fixtures, or non-PyPI sources
will require additional Nix expressions.

## License

See [`LICENSE`](LICENSE).
