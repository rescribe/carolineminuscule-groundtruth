# OCR Ground truth for Caroline Minuscule

This ground truth repository is a work in process; it currently accounts for a part of our complete Caroline Minuscule training pool of around 70 manuscripts used for our OCRopus Caroline Minuscule model (see ocropus-models repository).

## Repository structure

Each manuscript used is contained in a directory, which contains subdirectories for each page and a `metadata.txt` file.

The page subdirectories are split into lines (by ocropus-gpageseg), with `.png` images and corresponding `.gt.txt` ground truth text files. These have been prepared for the OCRopus OCR engine, but should be usable by other OCR engines which work on a line by line basis. Please let us know if you adapt the ground truth to work with other OCR engines, we'd love to hear about it.

There are also now full colour page images in each manuscript directory, alongside plain text and ALTO XML representations of ground truth, which can be used for training with Kraken or transforming into other formats.

### License, provenance, metadata

The ground truth contained in this repository should be considered Public Domain, or licensed under Apache License 2.0, whichever suits your needs better.

The `metadata.txt` files in each manuscript directory describes its provenance and the licensing of the images. We have only used manuscript images which are freely redistributable and reusable.



## OCR Ground Truth Transcription Protocol

The ground truth published in this repository has been created according to a number of guidelines designed to find a compromise
between the quirks of medieval writing and the limitations of modern software (i.e. its incompatibility with certain medieval characters or the fact that some 
medieval characters are not represented in unicode).
With some respect, we simply made some executive decisions on the transcription guidelines where we felt this would best serve the overall purpose.

In general this meant deciding between diplomatic transcription (i.e. sticking to what it says on the page) and
gently modernized features (i.e. reinterpreting medieval signs into modern equivalents) with a view to specific categories. Read on for a summary of the rules and the respective rationale behind them.



SUMMARY

PUNCTUATION
- Modern: medieval punctuation is transcribed with modern equivalents; punctus elevatus transcribed as semicolon

CAPITALIZATION
- Diplomatic: Original capitalization retained

ABBREVIATIONS
- Diplomatic where possible: Retain abbreviations and render glyphs as opposed to expanded versions where possible
- "\*" where original character isn't served: OCRopus (at the point in time of transcription) could not handle some of the medieval glyphs, even where a Unicode version was present. 
Abbreviations not in OCRopus are uniformly transcribed as "\*", in the case of a combined character (such as a consonant with a macron) as the base character followed by "\*" (e.g. "t\*").
The list of accepted characters in OCRopus can be found in this repository, and downloaded and used as codec in the OCRopus training process. 

SPACING
- Diplomatic: Preserve manuscript spacing, i.e. give diplomatic transcription

NUMBERS
- Diplomatic: retain original version of both Roman and Arabic numerals
