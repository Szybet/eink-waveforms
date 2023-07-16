# eink-waveforms
This repo, those files are so called waveforms for e-ink screens. They calibrate the display for best contrast for example. Using a wrong one may cause pernament damage to the capsules inside the screen.

So this repo exists primarly to backup those waveforms because if you lost your original one, you can use the one you found online ( image clones for example ) - but to minimaze the risk you may take one that is from a device that is from the same line up, produced in a similar time. In that way the waveform across production lines may be similar, maybe identical

## How to take a backup
Because of maybe diffrent eink waveforms lenghts, it may differ, so for the Nia it is:
```
sudo dd if=<sd card or cloned image file> of=<output file> bs=1 skip=7340042 count=582519
```
