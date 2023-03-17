# chayang

Gradually dim the screen.

Can be used to implement a grace period before locking the session.

Forked version of chayang, upstream here: https://git.sr.ht/~emersion/chayang

Changes from upstream:

- option to ignore mouse movements
- option to provide lock command as an argument to improve integration with lock program


## Usage

    chayang && swaylock

or use to use command option and ignore mouse movement:

    chayang -M -c 'swaylock -f'

Note: swaylock must use the `-f` option in order to run the screenlock program
in the background.

## Building

    meson setup build/
    ninja -C build/

## Contributing

Send patches on the [mailing list]. Discuss in [#emersion on Libera Chat].

## License

MIT

[mailing list]: https://lists.sr.ht/~emersion/public-inbox
[#emersion on Libera Chat]: ircs://irc.libera.chat/#emersion
