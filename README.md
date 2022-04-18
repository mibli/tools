# Asorted list of tools I use

## Index

* [abuild (Auto Build)](#auto-build-abuild)
* [compath (Compress Path)](#compress-path-compath)
* [datestamp](#worthy-mentions)
* [findlibs](#findlibs)
* [idlex (Idle Executor)](#idle-executor-idlex)
* [mailcheck](#mailcheck)
* [mlvdsel (Mullvad Selector)](#mullvad-selector-mlvdsel)
* [prtscn](#print-screen-prtscn)
* [recscn](#record-screen-recscn)
* [swap](#worthy-mentions)
* [thumbnailer](#thumbnailer)
* [timestamp](#worthy-mentions)

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

* removal of existence requirement for shortening (would need to implement a few tweaks)
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

### Mullvad Selector (mlvdsel)

Helps with selecting enabling and disabling WireGuard Mullvad configurations. Requires sudo to work,
so read the source to be sure.

Example usage:

    mlvdsel             # interactive
    mlvdsel -r          # select random country and server
    mlvdsel -c ro -s 4  # select server 4 in Romania

### Print Screen (prtscn)

Wrapper around several methods of taking screenshots. Mostly for tiled window manager use.

Example usage:

    prtscn -r  # take root screenshot
    prtscn -w  # take window screenshot
    prtscn -c  # take selection screenshot

### Record Screen (recscn)

Similar interface as `prtscn` for recording using ffmpeg. Nowadays I prefer obs. Also it's hard to
kill if You don't run it in terminal window.

Example usage:

    recscn -r  # record root
    recscn -w  # record window - careful! It doesn't follow window
    recscn -c  # record selection

### Thumbnailer

Generates thumbnails and returns paths to the thumbnails. Matches extensions for videos and
populates thumbnails under specified directory. Currently only customizable by editing the file.
Thumbnails are only created if they haven't been generated yet.

Doesn't have help flag!

Example usage:

    $ thumbnailer "/src/images/weird catalogue/1352345lk3j132.jpg" "/other/video.mp4"
    /home/user/.cache/thumbs/src/images/weird catalogue/1352345lk3j132.jpg
    /home/user/.cache/thumbs/other/video.mp4

### Worthy mentions

* datestamp - Produces a simple date stamp in predefined format.
* swap - swap two files with use of mktemp
* timestamp - Produces a simple time stamp in predefined format.
