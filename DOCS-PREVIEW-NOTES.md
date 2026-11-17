# Documentation notes for DiRoots.ProSheets.Releases

Found while testing documentation PR previews on a replica of this repository (`DiRoots-Mauro/DiRoots.Sandbox.ProSheets.Releases`) and on the production site. None of these items is caused by the preview workflows; they are listed so they can be fixed separately.

## Visual Studio cache committed on `gh-pages`

The `gh-pages` branch contains a `.vs/` folder (Visual Studio local settings). Jekyll does not publish it, but it does not belong in the repository.
- Suggested fix: delete `.vs/` from `gh-pages` and keep it ignored in `.gitignore`.
