
##Custom Terminal on Windows (Using the new Windows Terminal)

I'm pretty sure I starter reading this `https://www.hanselman.com/blog/ANewConsoleForWindowsItsTheOpenSourceWindowsTerminal.aspx`

[At some point I was reading this `https://gist.github.com/shanselman/221ef38d035fcf2836d664009f144eac?WT.mc_id=-blog-scottha` and I know I ~copied~ based my config on a profile/scheme _"UbuntuLegit"_]

On Windows, install chocolate `https://chocolatey.org/` (package manager)
Then install FiraCode `https://github.com/tonsky/FiraCode/wiki` 
    => This is to install it for Windows Terminals, for WSL:
    `sudo apt update & upgrade`
    `sudo apt install fonts-firacode`

Install PIP for 
    `sudo apt install python-pip`

###Install Powerline-Shell
* Following instructions given @ `https://github.com/b-ryan/powerline-shell?WT.mc_id=-blog-scottha#setup`

    `pip install powerline-shell`
* Add the following to the `.bashrc` profile (@ ~/): 

```Bash
Add the following to your .bashrc file:

function _update_ps1() {
    PS1=$(powerline-shell $?)
}

if [[ $TERM != linux && ! $PROMPT_COMMAND =~ _update_ps1 ]]; then
    PROMPT_COMMAND="_update_ps1; $PROMPT_COMMAND"
fi
```

### VSCode Settings
settings.json on vscode

```json
{
    "workbench.colorTheme": "Cobalt2",
    "editor.wordWrap": "on",
    "editor.formatOnPaste": true,
    "[html]": {
        "editor.defaultFormatter": "vscode.html-language-features"
    },
    "editor.fontFamily": "'Fira Code Medium', Consolas, 'Courier New', monospace",
    "editor.fontLigatures": true
}
```

The file `config.json` is to be copied to `~/.config/poweline-shell/config.json` as part of poweline-shell's configuration.

###ToDo:

Make Win32 PATH accessible from WSL (Seems to be a way here `https://devblogs.microsoft.com/commandline/share-environment-vars-between-wsl-and-windows/`)