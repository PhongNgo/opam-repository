This opam 2.0 repository contains packages released by the REMS project
(currently lem, linksem and sail) that are not yes on the main opam repository.
You can use it by adding it as an opam repository:

```
opam repository add rems https://github.com/rems-project/opam-repository.git
```

For most packages, this is a temporary solution, as they are soon going to be
available on the main [opam repository](https://opam.ocaml.org/).


## How to release opam packages here

It is assumed that your package lives on it's own GitHub repository.

 1) Ensure that your packages is properly packaged for opam by running
    `opam install .` in the repository root directory and verifying it's
    properly installed. If you don't know how to package, go to
    [opam packaging instructions](https://opam.ocaml.org/doc/Packaging.html)
 2) Release your package on git by tagging (`git tag -a <version>`)
    Release that on GitHub by pushing the tag (`git push origin <version>`)
 3) Install opam publish if you haven't already (`opam install opam-publish`)
 4) Run opam publish to create a PR to this repository (From your project root)

```
opam publish --repo=rems-project/opam-repository .
```
  5) Merge the PR

## License

All the metadata contained in this repository are licensed under the
[CC0 1.0 Universal](http://creativecommons.org/publicdomain/zero/1.0/)
license.

Moreover, as the collection of the metadata in this repository is
technically a "Database" -- which is subject to a "sui generis" right
in Europe -- we would like to stress that even the *collection* of
the metadata contained in opam-repository is licensed under CC0 and
thus the simple act of cloning opam-repository is perfectly legal.
