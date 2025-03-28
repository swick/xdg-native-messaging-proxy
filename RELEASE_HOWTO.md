# Steps for doing a xdg-native-messaging-proxy release

### Prepare the release

- Make sure the version in `meson.build` is correct
- Create a branch
```sh
$ git checkout -b release-${version}
```
- Add your changelog to the `NEWS.md` file
```sh
$ git add NEWS.md
$ git commit -m ${version}
```
- Push your branch
```sh
$ git push -u ${fork} release-${version}
```
- Open a pull request

### Create a Signed Tag

**NOTE**: Only project maintainers can create a tag.

Make sure that:
 - You're on the `main` branch, or a stable branch;
 - The tip of the branch is a release commit (e.g. `1.19.4`)
 - The version in `meson.build` is correct

Then create the tag:

```sh
$ git evtag sign ${version}
$ git push -u origin ${version}
```

### Post-Release

- Update version number in `meson.build` to the next release version
- Start a new section in `NEWS.md`
```md
Changes in ${nextVersion}
=================
Released: Not yet
...
```
