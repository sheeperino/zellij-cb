# zellij-cb

Custom compact bar plugin for [Zellij](https://zellij.dev/) based on
[Zellij's default plugin](https://github.com/zellij-org/zellij/tree/main/default-plugins/compact-bar).

<div align="center">
  <div>
    <img src="https://github.com/ndavd/zellij-cb/assets/74260683/94c76afa-223c-4fcd-974e-275cb8b1690f" />
  </div>
  <code>{session directory}-{session name} {mode in 1 letter} {...tabs}</code>
</div>

## Features

- Displays session directory name
- Is super compact and minimal
- Configurable

## Installation

To build it just run `make` and you'll find the binary in
`target/wasm32-wasip1/release/zellij-cb.wasm`. To load it into Zellij please
refer to their
[plugin loading documentation](https://zellij.dev/documentation/plugin-loading).

## Example usage

Check out my
[dotfiles](https://github.com/ndavd/dotfiles/tree/main/.config/zellij).

## Available configuration

- `color` type: This plugin takes its colors from the user's theme, they can
  then be overwritten with the following syntax:
  - 8-bit color (single digit), e.g. `"16"`
  - RGB color (comma separated digits), e.g. `"255,255,255"`

| Key                                          |   Type    | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
| -------------------------------------------- | :-------: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| **DisplaySessionDirectory**                  | `boolean` | If this is `false` then it only displays the session name. It will display the session name in the same style as before only if there's only one `-` (or none) like the default session names for zellij. If there are more then only the last two pieces of text delimited by it will be displayed with that style and the remaining will be displayed in the session directory style. This is particularly useful for those who wish to include the session directory in the session name. Default: `true` |
| **DefaultTabName**                           | `string`  | Default: `tab`                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |
| **FgColor**                                  |  `color`  | Default: `theme.text_selected.base`                                                                                                                                                                                                                                                                                                                                                                                                                                                                          |
| **BgColor**                                  |  `color`  | Default: `theme.text_unselected.background`                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
| **SessionDirectoryColor**                    |  `color`  | Default: `theme.text_selected.base`                                                                                                                                                                                                                                                                                                                                                                                                                                                                          |
| **SessionNameColor**                         |  `color`  | Default: `theme.text_selected.background`                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
| **TabColor**                                 |  `color`  | Default: `theme.text_selected.background`                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
| **ActiveTabColor**                           |  `color`  | Default: `theme.text_selected.emphasis_2`                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
| **NormalModeColor**                          |  `color`  | Default: `theme.exit_code_error.emphasis_1`                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
| **OtherModesColor**                          |  `color`  | Default: `theme.text_selected.emphasis_0`                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
| **OthersColor**                              |  `color`  | Default: `theme.text_selected.emphasis_0`                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
| **{mode}ModeLabel** (e.g. `NormalModeLabel`) | `string`  | Default: First letter of the mode and empty string if mode is `Locked`                                                                                                                                                                                                                                                                                                                                                                                                                                       |
