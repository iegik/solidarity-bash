# solidarity-bash

_Inspired by [solidarity](https://github.com/infinitered/solidarity) npm [package](https://www.npmjs.com/package/solidarity)_

A lightweight Bash script version of solidarity

## Usage

Create a `.solidarity` file in the root of your project as described below in [Example](#Example) section. And run following command:

```bash
npx solidarity-bash
```

- [x] Grouping (without spaces)
- [x] Custom messages (`{{installedVersion}}` and `{{wantedVersion}}` variables supported)
- [x] Versioning support (SemVer)
- [x] Custom RegExp support

**Example**

.solidarity

```json
{
  "$schema": "http://json.schemastore.org/solidaritySchema",
  "requirements": {
    "Android": [
      {
        "rule": "cli",
        "binary": "emulator"
      },
      {
        "rule": "env",
        "variable": "ANDROID_HOME",
        "error": "The ANDROID_HOME environment variable must be set to your local SDK.  Refer to getting started docs for help."
      }
    ],
    "iOS": [
      {
        "rule": "cli",
        "binary": "xcodebuild",
        "version": "-version",
        "semver": ">=13.0.0",
        "error": "You have xcodebuild@{{installedVersion}}. Fix with install xcode v{{wantedVersion}}",
        "platform": "darwin"
      },
      {
        "rule": "cli",
        "binary": "gem",
        "version": "list ffi",
        "semver": ">=1.15.5 <2.0.0",
        "error": "You have ffi@{{installedVersion}}. Fix with `gem install ffi --version {{wantedVersion}} --user-install`. More info https://github.com/ffi/ffi",
        "platform": "darwin"
      }
    ],
    "Git": [
      {
        "rule": "shell",
        "command": "git config user.email",
        "match": ".+@.+"
      }
    ]
  }
}
```