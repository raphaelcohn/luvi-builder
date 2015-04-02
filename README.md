# [luvi-builder]

[luvi-builder] is a simple MIT-licensed [shellfire] script to make it easy to build [luvi] applications directly from Git. It's intended to be used as a git submodule. See [luvi-builder-samples] to see how it's used. You can fork [luvi-builder-samples] to bootstrap your own [luvi-builder] based project.

[luvi-builder] will attempt to download and cache a version of [luvi] from GitHub releases for the current OS and machine architecture. It does this by reading the link in `lib/luvi/current`, which should resolve to a version (including the leading 'v'). Downloading normally uses `curl`, but will fallback to a BusyBox friendly `wget`.

[luvi-builder] exists as an alternative to [lit] based applications. Its intention is to provide a GitHub-friendly model of development and dependency managerment (aka 'Check out and Go') and to support 'rsync' style deployment. Indeed, you should be able to just rsync a [luvi-builder] based project directly to a host once pulled from git (and submodules init'd). Or, you can build your project and then rsync the output (for even fewer dependencies).

## Footnote
[luvi-builder] is also partly an emotional response to the Windows noise in a lot of [luvi] - semicolons as path separators, using zip as a package format (heck, even Java 9 has finally recognised that they goofed when they chose that) and the package manager, [lit]. [lit] by itself is fine, it's just, well, I detest language-specific package managers for software dependencies. They assume a certain way of working that's often not apt (get it). It all started with maven, and went downhill from there. Indeed, you don't _really_ need even [luvi-builder]; 'built' [luvi] applications are just luvi + a zip concatenated on the end. There not even appropriate for some use cases (eg readonly file systems on low-power devices).

[shellfire]: "https://github.com/shellfire-dev/shellfire" "shellfire homepage"
[luvi-builder-samples]: "https://github.com/raphaelcohn/luvi-builder-samples" "luvi-builder homepage"
[luvi-builder]: "https://github.com/raphaelcohn/luvi-builder" "luvi-builder homepage"
[luvi]: "https://github.com/luvit/luvi" "luvi homepage"
[lit]: "https://github.com/luvit/lit" "lit homepage"
