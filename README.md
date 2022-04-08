# Asorted list of tools I use

For usage help run

    toolname -h

## Mailcheck

A script to compare the count of mail in maildir before (cached, or running a command)
and after, send notifications about mail that just arrived and print the count
of new mail.

The purpose of this script is to use it on one of the small window managers
taskbars, such as polybar or i3blocks, with combination of offlineimap.

The script caches the new message list in `$XDG_CONFIG_HOME/mailcheck`

## FindLibs

The purpose of this script is to automate finding dependencies of libraries, that are incorrectly
linked and thus You can't be sure which symbols they include. It will scan ELF symbols and look for
the symbol in each library under given paths. Honestly though... Just link the libraries properly.

Example usage:

    findlibs badlib.so badlibs/ /usr/lib/ /usr/lib/Qt5/
