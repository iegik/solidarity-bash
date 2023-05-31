# solidarity-bash

_Inspired by [solidarity](https://github.com/infinitered/solidarity) npm [package](https://www.npmjs.com/package/solidarity)_

## Goal

Create lightweight Bash script version of solidarity

- [ ] Grouping
- [ ] Custom messages (template support)
- [ ] Versioning support
- [ ] Custom RegExp support

**TODO: Get configuration**

```
cat .solidarity | jq -r '.["$schema"]'
cat .solidarity | jq -r '.requirements'
```

**TODO: Comparing semver**

```
$(($a < $b)) # math expressions
```

- https://stackoverflow.com/questions/4023830/how-to-compare-two-strings-in-dot-separated-version-format-in-bash
- https://gist.github.com/Ariel-Rodriguez/9e3c2163f4644d7a389759b224bfe7f3
- https://gist.github.com/jonlabelle/6691d740f404b9736116c22195a8d706
- https://unix.stackexchange.com/questions/285924/how-to-compare-a-programs-version-in-a-shell-script
