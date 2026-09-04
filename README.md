# Valhalla Scientific 2724A

Documentation for the Valhalla Scientific 2724A Programmable Precision
Resistance Standard and its CPR variant — a 1980s decade resistance standard
built around a Motorola MC68A09P.

## Contents

| Document | Pages | |
|---|---|---|
| `2724A_Operation_Manual.pdf` | 56 | Operation manual |
| `2724A_Service_Manual.pdf` | 74 | Service manual, including all 15 drawing sheets |
| `2724A_Firmware_Reference.pdf` | 32 | Firmware reference — see below |

All three have a linked table of contents and PDF bookmarks.

## About the manuals

The Operation and Service manuals are rebuilt from scans of the originals. The
text has been transcribed and retypeset so it is searchable and selectable,
while every figure, table image and drawing sheet is the **original scanned
artwork**. Nothing has been redrawn, traced or reinterpreted — where a drawing
appears, it is the manufacturer's own drawing.

Copyright in the original manuals rests with Valhalla Scientific. They are
reproduced here as a service to owners of a long-discontinued instrument, with
no claim of ownership and no commercial intent.

## About the firmware reference

`2724A_Firmware_Reference.pdf` is **not** a Valhalla document. It was produced
by disassembling the instrument's 8K main ROM (IC519) and documents what the
firmware actually does — including a fair amount the manuals do not cover:

- the complete IEEE-488 command set, including four undocumented forms
- the memory map, and the NOVRAM calibration and user data format with the
  arithmetic of both checksums
- the calibration state machine, and what the firmware does when the NOVRAM
  checksum fails (it loads ROM defaults, so the instrument then reads wrong
  while appearing to work)
- the display subsystem, its character set, and the full message catalogue
- the differences between the standard and CPR firmware builds

The two builds are told apart by the checksum word the firmware stores at
`$E000` and verifies at every reset: `$F688` for the standard build, `$A4B9`
for CPR.

## Accuracy

The manual transcriptions were proofread against the scans. The firmware
reference is derived from analysis of the ROM images; where something could not
be determined, it says so rather than guessing.

Offered as-is, with no warranty. Servicing mains-powered test equipment is at
your own risk.
