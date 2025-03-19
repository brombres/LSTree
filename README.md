# LSTree
Command line folder listing with indented tree-style display.

Summary   | Current Release
----------|-----------------------
Version   | 2.2
Date      | March 19, 2025
Platforms | macOS, Linux (Ubuntu+), Windows
License   | [MIT License](LICENSE)
Author    | Brom Bresenham

## New Installation

1. Install [morlock.sh](https://morlock.sh)
2. `morlock install brombres/lstree`

## Updating Existing Installation
`morlock update lstree`

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

    ~/Projects/Tools/LSTree> lst -n
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

    USAGE
      lst [OPTIONS] [folder-path]

    OPTIONS
      -0, -1, -2, ...
        Aliases for `--depth=0` ...

      --depth=<N>, -d <N>
        --depth=0 # No depth limitation (default)
        --depth=1 # Limit the listing to a single level
        --depth=2 # Limit the listing to two levels, etc.

      --exclude, --exclude=pattern
        Without an argument, any wildcard filepaths that follow are automatically
        used as exclusion patterns. With an argument, only the specified pattern is
        excluded. Example: "lst --hidden --exclude=.git". See also WILDCARD
        PATTERNS, below.

      --folders, -f
        Show folders only, without files.

      --help, -h
        Show this help text.

      --hidden, -a
        Show hidden files.

      --no-sizes, -n
        Do not show file sizes.

    WILDCARD PATTERNS
      Put patterns in quotes to ensure that LSTree's non-standard wildcard patterns
      are correctly processed. By example:
        "*.rogue"      # matches files in the current folder ending with ".rogue"
        "**/*.rogue"   # matches files in subfolders or in the current folder.
        "*/**/*.rogue" # matches files in subfolders but not in the current folder
      Finally, '?' can be used to match any single character.
