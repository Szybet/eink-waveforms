# eink-waveforms
This repo, those files are so called waveforms for e-ink screens. They calibrate the display for best contrast for example. Using a wrong one may cause pernament damage to the capsules inside the screen.

So this repo exists primarly to backup those waveforms because if you lost your original one, you can use the one you found online ( image clones for example ) - but to minimaze the risk you may take one that is from a device that is from the same line up, produced in a similar time. In that way the waveform across production lines may be similar, maybe identical

The file names have the "SN" number on them, which is on the package and differs across devices, and time so it's propably the best way to choose.

## How to take a backup
Because of maybe diffrent eink waveforms lenghts, it may differ, so for the Nia it is:
```
sudo dd if=<sd card or cloned image file> of=<output file> bs=1 skip=7340042 count=582519
```
## How to restore?
For the nia:
```
sudo dd if=<the fd file> of=<sd card or cloned image file> bs=1 seek=7340042 count=582519
```
I propose that you take a second backup to check if it applied correctly
## Other informations
- Bless hex editor is a very good tool to look arround those files / images
  - for the nia, look up offsets 7340000 and 7922450 on a full image or just a file taken like this: `sudo dd if=<sd card or image> of=<outpuf file> bs=1M skip=0 count=100`
- Write to the real image, not the compressed one :)
- https://github.com/akemnade/kobo-firmware-extractor/tree/main is a proper extraction tool and should work for all devices, to just extract you do:`
extract-kobohidden /dev/mmcblk0 14336 epdc.fw`
