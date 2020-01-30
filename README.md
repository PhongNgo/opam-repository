This opam 1.2 repository contains packages released by the REMS project
(currently lem, linksem and sail). You can use it by adding it as an
opam repository:

```
opam repository add rems https://github.com/rems-project/opam-repository.git
```

Note that opam 2 has a new repository format so these packages will not be accepted in the main opam repository until we upgrade them. 
For the moment we are sticking with opam 1.2 format so that we remain compatible with old and new opams.

## How to release opam packages

This is a method I found works for releasing to this repository:

0) Install an old version of `opam-publish` that does opam 1.2 format: `opam pin opam-publish=0.3.5`
1) Increment the `version:` filed in the opam file in the repository root. `git` add, commit and push that change.
1) `git tag -a <version>` the repository with the same version
1) `git push origin <version>` to push the tag to github
1) Run `opam-publish prepare` in the root of the repository
1) Move the resulting `package-name.version` directory into a checkout of this repo at `opam-repository/packages/package-name/` then `git` add, commit and push it.


## License

All the metadata contained in this repository are licensed under the
[CC0 1.0 Universal](http://creativecommons.org/publicdomain/zero/1.0/)
license.

Moreover, as the collection of the metadata in this repository is
technically a "Database" -- which is subject to a "sui generis" right
in Europe -- we would like to stress that even the *collection* of
the metadata contained in opam-repository is licensed under CC0 and
thus the simple act of cloning opam-repository is perfectly legal.
