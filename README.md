# LSTree
Command line folder listing with indented tree-style display.

## Version
- v1.1 - May 31, 2020
- macOS, Linux, Windows
- [MIT License](LICENSE)
- By Abe Pralle

## Installation
1. Install the [Rogue](https://github.com/AbePralle/Rogue) language.
2. Run `rogo` in this folder to compile **LSTree**.
    - On macOS and Linux a launcher will be created here: `/usr/local/bin/lst`.
    - On Windows the build process will print the necessary folder to add to the system PATH environment variable.

## Examples

### Typical Use

    ~/Projects/Tools/LSTree> lst
    /Users/abe/Projects/Tools/LSTree
    - Build/
      - lst.exe        [276K]
      - LSTree-Linux   [282K]
      - LSTree-macOS   [319K]
      - LSTree.cpp     [354K]
      - lstree.exe     [194K]
      - LSTree.h      [83.8K]
      (1.5M)
    - Build.rogue  [11.5K]
    - LICENSE       [1.0K]
    - README.md     [4.1K]
    - Source/
      - LSTree.rogue   [5.6K]
      (5.6K)
    (1.5M)

### lst --no-sizes

    ~/Projects/Tools/LSTree> lst --no-sizes
    /Users/abe/Projects/Tools/LSTree
    - Build/
      - lst.exe
      - LSTree-Linux
      - LSTree-macOS
      - LSTree.cpp
      - lstree.exe
      - LSTree.h
    - Build.rogue
    - LICENSE
    - README.md
    - Source/
      - LSTree.rogue

## Usage

### Syntax

    lst [options] [folder-path]

### Options

Option             | Description
-------------------|-------------------------------------
`--depth=<N>`      | Limit the depth recursion to 1 or more levels (0 is unlimited).
`--exclude`<br>`--exclude=pattern` | Without an argument, any wildcard filepaths that follow are automatically used as exclusion patterns. With an argument, only the specified pattern is excluded. Example: `lst --hidden --exclude=.git`. See also WILDCARD PATTERNS, below.
`--help`                           | Show this help text.
`--hidden`<br>`-a`                 | Show hidden files.
`--no-sizes`<br>`--nosz`           | Do not show file sizes.

### Wildcard Patterns

    Put patterns in quotes to ensure that LSTree's non-standard wildcard patterns are correctly processed. By example:
    "*.rogue"     # matches files in the current folder ending with ".rogue"
    "**/*.rogue"  # matches files in subfolders but not in the current folder
    "***/*.rogue" # matches files in subfolders or in the current folder.

Finally, `?` can be used to match any single character.

