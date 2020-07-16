# txtfmt (forked from [recode_rs](https://github.com/hsivonen/recode_rs))

[![Apache 2 / MIT dual-licensed](https://img.shields.io/badge/license-Apache%202%20%2F%20MIT-blue.svg)](https://github.com/hsivonen/recode_rs/blob/master/COPYRIGHT)

txtfmt is a command-line tool converting between the character encodings
defined in the [Encoding Standard][1].

It is written primarily as sample code that demonstrates the use of
[encoding_rs][2], which is why it has an option for using UTF-16 (as opposed
to the default UTF-8) as the intermediate encoding, even though such an option
doesn't really make sense from the perspective of using the program as
non-sample code.

[1]: https://encoding.spec.whatwg.org/
[2]: https://github.com/hsivonen/encoding_rs

## Building from a local git clone

Using release-channel Rust:

```
cargo build --release
```

With SIMD acceleration on x86, x86_64 and Aarch64:

```
cargo build --release --features simd-accel
```

## Usage

```
txtfmt [-f INPUT_ENCODING] [-t OUTPUT_ENCODING] [-o OUTFILE] [INFILE] [...]
```

### Options

```
    -o, --output PATH   set output file name (- for stdout; the default)
    -f, --from-code LABEL
                        set input encoding (defaults to UTF-8)
    -t, --to-code LABEL set output encoding (defaults to UTF-8)
    -u, --utf16-intermediate
                        use UTF-16 instead of UTF-8 as the intermediate
                        encoding
    -h, --help          print usage help
```

## Release notes

### 0.1.0

-   Initial forked release
