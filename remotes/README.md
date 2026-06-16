Codes for individual Sony remotes.

These are mostly going to be codes for remotes I own or was able to have access to learn the codes myself, at least initially.  These are listed with "Source: [1]" at the top.

The code data is formatted in the `[D 00-0-00 F 000]` format, which reflects how the codes are actually organized and will sort easily.
The device code has 1 to 3 parts depending on its length.

```
Format             Bits     Transmission order -->
[D aa      F fff]  12 bits  f0 f1 f2 f3 f4 f5 f6  a0 a1 a2 a3 a4
[D aa-b    F fff]  15 bits  f0 f1 f2 f3 f4 f5 f6  a0 a1 a2 a3 a4  b0 b1 b2
[D aa-b-cc F fff]  20 bits  f0 f1 f2 f3 f4 f5 f6  a0 a1 a2 a3 a4  b0 b1 b2  c0 c1 c2 c3 c4
```

Examples:
```
[D 01      F 021]  Sony12, device 1, function 21 (TV: Power)
                   Bits: 1010100 10000
[D 04-2    F 018]  Sony15, device 68, function 18 (Boombox: Volume +)
                   Bits: 0100100 00100 010
[D 26-1-09 F 050]  Sony20, device 26.73, function 50 (DVD1: Play)
                   Bits: 0100110 01011 100 10010
```

Conversions to the more common device code formats:
```
Sony15: D   = A + 32 * B
Sony20: D   = A + 32 * B + 256 * C
        D.S = A.(B + 8 * C)
```
