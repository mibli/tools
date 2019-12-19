# Asorted list of tools I use

For usage help run

    TOOL -h

## Mailcheck

A script to compare the count of mail in maildir before (cached, or running a command)
and after, send notifications about mail that just arrived and print the count
of new mail.

The purpose of this script is to use it on one of the small window managers
taskbars, such as polybar or i3blocks, with combination of offlineimap.

The script caches the new message list in `$XDG_CONFIG_HOME/mailcheck`
