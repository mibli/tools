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

### Compress Path (compath)

Compresses path mainly for prompt use, addressing the problem of ugly wrapping, or lengthy prompts.
I don't think it has much use outside of it, but feel free to let me know if You do. It should be
compatible with paths with spaces and unicodes.

Example usage:

    pwd | compath

Possible future features:

* full name of last element
* vowel removal
* preserving the trailing 's' (indicating multiple)
* tests

### FindLibs

The purpose of this script is to automate finding dependencies of libraries, that are incorrectly
linked and thus You can't be sure which symbols they include. It will scan ELF symbols and look for
the symbol in each library under given paths. Honestly though... Just link the libraries properly.

Example usage:

    findlibs badlib.so badlibs/ /usr/lib/ /usr/lib/Qt5/

### Idle Executor (idlex)

This is a bash script for running commands after some x input idle time. Personally I've used it
mostly for reporting worked time on a project.

Example usage:

    idlex -e "notify-send idle detected" -x "notify-send idle exited" -i 10s -t $((1 * 60 * 1000))

### Mailcheck

A script to compare the count of mail in maildir before (cached, or running a command)
and after, send notifications about mail that just arrived and print the count
of new mail.

The purpose of this script is to use it on one of the small window managers
taskbars, such as polybar or i3blocks, with combination of offlineimap.

The script caches the new message list in `$XDG_CONFIG_HOME/mailcheck`
