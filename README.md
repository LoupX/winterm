# Custom Terminal on Windows (Using the new Windows Terminal)

I was about to start a [Wes Bos' course](https://learnnode.com) while using a computer with windows and I realized how uggly is powerShell (and cmd and whatsoever), even when I had already installed ubuntu as [WSL](https://docs.microsoft.com/en-us/windows/wsl/install-win10) and even after installed the [new windows terminal](https://devblogs.microsoft.com/commandline/introducing-windows-terminal/) (Currently on Beta) so, as a good procrastinator, I decided to have a, at least, decent terminal before start. It may not be needed but it will calm my tatas.

I'm pretty sure I starter reading [this](https:git//www.hanselman.com/blog/ANewConsoleForWindowsItsTheOpenSourceWindowsTerminal.aspx)

At some point I was reading [this](https://gist.github.com/shanselman/221ef38d035fcf2836d664009f144eac?WT.mc_id=-blog-scottha) and I know I ~copied~ based my config on a profile/scheme named _"UbuntuLegit"_ so:

- On Windows, install [chocolate](https://chocolatey.org) (package manager)

- Then [install FiraCode](https://github.com/tonsky/FiraCode/wiki)
    => This is to install it for Windows Terminals, for WSL:
    `sudo apt update & apt upgrade`
    `sudo apt install fonts-firacode`

Install PIP for python packages
    `sudo apt install python-pip`

## Install Powerline-Shell

-Following instructions given [@ b-ryan's powerline-shell](https://github.com/b-ryan/powerline-shell?WT.mc_id=-blog-scottha#setup)

    `pip install powerline-shell`

-Add the following to the `.bashrc` profile (@ ~/):

    ```Bash
    #Add the following to your .bashrc file:

    function _update_ps1() {
        PS1=$(powerline-shell $?)
    }

    if [[ $TERM != linux && ! $PROMPT_COMMAND =~ _update_ps1 ]]; 
    then
        PROMPT_COMMAND="_update_ps1; $PROMPT_COMMAND"
    fi
    ```

The file [config.json](config.json) is to be copied to `~/.config/poweline-shell/config.json` as part of poweline-shell's configuration.
The configuration file is explained at b-ryans' project (link above, DUH !)

## VSCode Settings

These are my current [settings](settings.json) on vscode

## To Do

## Updates

~Make Win32 PATH accessible from WSL (Seems to be a way [here](https://devblogs.microsoft.com/commandline/share-environment-vars-between-wsl-and-windows/) )~

No longer needed. Acording to [this article](https://docs.microsoft.com/en-us/windows/wsl/interop#share-environment-variables-between-windows-and-wsl) to run Win exes from WSL it is just needed to write:
`app.exe` for example `notepad.exe`, as long as the executable is on Windows' PATH it should work.

[Examples here](https://docs.microsoft.com/en-us/windows/wsl/interop#)
