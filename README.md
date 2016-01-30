dd-ng
=====

This is a simple wrapper around `dd` that provides the following features:

* Uses GNU-style syntax instead of weird mainframe-like syntax.
* Adds sanity check for writing to devices. Non-regular files can only be written to by using the `--no-preserve-raw-device` flag.

Note it does not yet support all `dd` options.

Usage
-----

    dd-ng [{--input-file|-i} FILE] [{--output-file|-o} FILE] [{--block-size|-b} BYTES] [--input-block-size BYTES]
          [--output-block-size BYTES] [{--input-seek|-k} BLOCKS] [{--output-seek|-s} BLOCKS] [--input-flags FLAGS]
          [--output-flags FLAGS] [--no-preserve-raw-device]

    --input-file FILE
    -iFILE

Source file, maps to `if` in `dd`.

    --output-file FILE
    -fFILE

Destination file, maps to `of` in `dd`.

    --block-size BYTES
    -bBYTES

Size of data in bytes (with suffixes like K, M, G supported) to read and write
at a time, maps to `bs` in `dd`.

    --input-block-size BYTES

Size of data to read at a time, maps to `ibs` in `dd`.

    --output-block-size BYTES

Size of data to write at a time, maps to `obs` in `dd`.

    --input-seek BLOCKS
    -kBLOCKS

Skip/seek BLOCKS blocks into the input file before beginning conversion, maps
to `skip` in `dd`.

    --output-seek BLOCKS
    -sBLOCKS

Skip/seek BLOCKS blocks into the output file before beginning conversion, maps
to `seek` in `dd`.

    --input-flags FLAGS

Apply the provided comma-separated flags to input file on conversion, maps to
`iflag` in `dd`.

    --output-flags FLAGS

Apply the provided comma-separated flags to output file on conversion, maps to
`oflag` in `dd`.

    --no-preserve-raw-device

Proceed with conversion even if the destination file is not a regular file.
Make sure to use the correct destination device to avoid data loss!
