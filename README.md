# DDcal

DDcal is a BDD calculator with a graphical interface, written by Fabio
Somenzi at the University of Colorado at Boulder. It is a Perl/Tk
front end (`DDcal.pl`) driving a small lex/yacc C program (`ddcal`)
that parses calculator statements, performs the BDD computations with
[CUDD](https://github.com/davidkebo/cudd), and pipes a description of
the result to `dot` for layout, which DDcal then draws on screen.

This repository holds Fabio Somenzi's DDcal releases (0.7, 0.8, 0.9),
unmodified, one tagged commit per version, the same way
[davidkebo/cudd](https://github.com/davidkebo/cudd) holds CUDD.

## Requirements

From `INSTALL`:

- [Graphviz](https://www.graphviz.org) 1.7 or later (`dot` must be on `PATH`)
- Perl 5.6.0 or later, with Perl/Tk (`Tk800.023` or later)
- flex 2.5.4 or later (or lex)
- bison 1.28 or later (or yacc)
- [CUDD](https://github.com/davidkebo/cudd) 2.3.1 or later

DDcal 0.9's `INSTALL` records it as last tested with CUDD 2.5.1, GCC
4.8.x/4.9.1, bison 3.0.2, flex 2.5.x, Graphviz 2.36/2.38, and Perl
5.14-5.20 with Perl-Tk 804.03x, on GNU/Linux and Cygwin.

## Building

```sh
git clone https://github.com/davidkebo/ddcal.git
cd ddcal
```

Edit the `Makefile`'s `WHERE`, `PREFIX`, `EXE`, and `PL` definitions if
needed (in particular, `WHERE` must point at a built CUDD tree; see
[davidkebo/cudd](https://github.com/davidkebo/cudd) for building CUDD
itself), then:

```sh
make
./DDcal.pl -program ./ddcal
```

The `examples/` directory has `.ddc` files to load from DDcal's `Load`
button.

```sh
make install
```

installs to `/usr/local/bin` by default (change `PREFIX` in the
Makefile to install elsewhere). DDcal.pl is installed as `DDcal` on
Unix and as `DDcal.pl` on Windows/Cygwin.

## License

See [`LICENSE`](LICENSE): "This program is free software; you can
redistribute it and/or modify it under the same terms as Perl itself,"
per `DDcal.pl`'s own header. No other license is applied.

## Related

- [davidkebo/cudd](https://github.com/davidkebo/cudd) — the CUDD
  package DDcal is built on.
