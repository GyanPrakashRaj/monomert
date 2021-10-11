# To create a mononert or a monorepo.
                           'https://github.com/GyanPrakashRaj/shelllbaba.git'
- Make a file containing the git URLs of the repos you want to
  combine. These can be paths to bare repos (ideally created with `git
  clone --mir`) or `git@github.com:` URLs. This file should be
  named `something.repos` where `something` is the name of the new
  monorepo you want to create.

- Run `./build something.repos`. It will create a directory named
  `something` and incorporate all the repos listed in the `.repos`
  file.

- After the monorepo is built, look for `empty-repo.txt` and
  `no-branch.txt` files in the subdirectories. These are created if
  the repo incorporated had either no changes (`empty-repo.txt`) or no
  `master` branch. In the latter case the `no-branch.txt` file will
  contain a list of the refs from the repo. If there's an appropriate
  branch (say the repo used `prod` instead of `master`) you can fix
  things up with the `pushdown` script. In the monorepo remove the
  `no-branch.txt` and then run `./pushdown foo/prod` to put the
  contents of the `foo/prod` branch into the `foo` subdirectory and
  merge them to `master`.


# Pushing to GitHub

After you've built your monorepo, you'll probably want to push it to
GitHub. In the normal case you can probably just create a repo on
GitHub and then do the normal:

```
git remote add origin git@github.com:<whatever>
```

Then to push everything:

```
git push --all origin
git push --tags origin
```
# Copyright
- Kindly ASK before copy or any other changes.
- All right reserved 'https://github.com/GyanPrakashRaj/shelllbaba.git'.

