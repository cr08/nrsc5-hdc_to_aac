# HDC_TO_AAC

The included program was taken from an older version of the [NRSC-5](https://github.com/theori-io/nrsc5) repository where it still exists and is usable as a standalone application. It has since been removed from that repo as it is unsupported and some broadcasts may have issues.

In my own personal testing with stations local to me, it is 100% usable. That said, this fork is provided as-is with no support.

### Build Instructions

     $ gcc -o hdc_to_aac src/hdc_to_aac.c

     $ gcc -o hdc_to_aac_std src/hdc_to_aac_std.c

In the future I would like to combine these into one program but C code is new to me. Will gladly accept PR's!

### Usage

The `nrsc5` application that tunes the HD Radio feeds and is capable of dumping an HDC feed is not included here. Please check the repository linked above for instructions how to compile and use that.

As of writing, there are two versions of this program:

hdc_to_aac - Takes file input and output. Export a raw HDC dump from `nrsc5` and output to an AAC file.

     hdc_to_aac ~/file.hdc ~/file.aac

hdc_to_aac_std - Takes both stdin and stdout data.

     nrsc5 --dump-hdc - 99.5 0 | ./hdc_to_aac_std | echo > file.aac

### Goals and future To-Do's

I'd like to create a solution to pipe the AAC data stream to a web stream whether that's over HTTP, RTMP, or another solution.