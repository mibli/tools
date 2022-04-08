# Asorted list of tools I use

## General usage

For usage help run

    toolname -h

## Scripts

### Auto Build (abuild)

This is just a wrapper command, that will detect files present in the current directory and try to
build the project in `.build` folder. Considering it's limited functionality I use it more often
than it deserves credit for.

Example usage:

    abuild  # run when in a project folder

### FindLibs

The purpose of this script is to automate finding dependencies of libraries, that are incorrectly
linked and thus You can't be sure which symbols they include. It will scan ELF symbols and look for
the symbol in each library under given paths. Honestly though... Just link the libraries properly.

Example usage:

    findlibs badlib.so badlibs/ /usr/lib/ /usr/lib/Qt5/

### Mailcheck

A script to compare the count of mail in maildir before (cached, or running a command)
and after, send notifications about mail that just arrived and print the count
of new mail.

The purpose of this script is to use it on one of the small window managers
taskbars, such as polybar or i3blocks, with combination of offlineimap.

The script caches the new message list in `$XDG_CONFIG_HOME/mailcheck`
