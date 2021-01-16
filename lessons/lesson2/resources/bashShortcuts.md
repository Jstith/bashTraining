__Bash Shortcuts__
==================

### References

- [The Linux Command Line](https://nostarch.com/tlcl2) by No Starch Press
- [Keyboard Shortcuts for Bash](https://www.howtogeek.com/howto/ubuntu/keyboard-shortcuts-for-bash-command-shell-for-ubuntu-debian-suse-redhat-linux-etc/) by How-To Geek

### Cursor Movement

| Key | Action |
| :------------- | :------------- |
| ctl-A | Move cursor to the beginning of the line. |
| ctl-E | Move cursor to the end of the line. |
| ctl-F | Move cursor forward one character; same as the right arrow key. |
| ctl-B | Move cursor backward one character; same as the right arrow key. |
| alt-F | Move cursor forward one word. |
| alt-B | Move cursor backward one word. |
| ctl-L | Clear the screen and move the cursor to the top left corner; same as the `clear` command. |

### Text Editing

| Key | Action |
| :------------- | :------------- |
| ctl-D | Delete the character as the cursor location |
| ctl-T | Transpose (exchange) the character at the cursor location with the one preceding it |
| alt-T | Transpose (exchange) the word at the cursor location with the one preceding it |
| alt-L | Convert the characters from the cursor location to the end of the word to uppercase |
| alt-U | Convert the characters from the cursor location to the end of the word to lowercase |
| alt-C | Convert the character currently highlighted by the cursor to uppercase |

### Killing and Yanking

| Key | Action |
| :------------- | :------------- |
| ctl-K | Kill (cut) text from the cursor location to the end of the line. |
| ctl-U | Kill text from the cursor location to the beginning of the line. |
| alt-D | Kill text from the cursor location to the end of the word. |
| alt-Backspace | Kill text from the cursor location to the beginning of the current word. If the cursor is at the beginning of a word, kill the previous word. |
| ctl-Y | Yank text from the kill-ring and insert it at the cursor location (paste) |
