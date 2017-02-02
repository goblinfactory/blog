# How to show hidden files and folders on a mac

Warning: changing this setting can result in serious damage to your Mac as it will allow you to see and edit system files and folders you should not be fiddling with. Unfortunately sometimes some developer folders (like `.vscode` settings folder) are hidden.

## Showing system and hidden files

> `defaults write com.apple.finder AppleShowAllFiles YES`

## Resetting (hiding) system and hidden files

> `defaults write com.apple.finder AppleShowAllFiles NO`

After running either of the above commands, alt+right click on finder and select relaunch for the changes to take effect. Finder will restart and re-open at the same place it was before.