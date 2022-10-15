# simpsons2_audio
simpsons.

Audio files need to be cleaned (contains data from my testing :P) 

### this isn't meant to have all the audio, this was mainly created from testing and having fun while doing so.

## Speech
* HOMER - Homer | Unfinished
* MRG - Marge | Unfinished
* COLLECT_SFX - Collect Sound Fx | Finished
* SIMPSONS2_GAMEPLAY - Gameplay Sound Fx for Simpsons | Unfinished [missing sounds]

## Music
* SUNDAY_DRIVE | Finished
* HIT_RUN | Finished

## Needs Removal (not needed for this)
* PAIN_NIKO - test
* NIKO_EXTRAS - test
* PAIN_LUIS - test
* LUIS_EXTRAS - test
* PAIN_JOHNNY - test
* JOHNNY_EXTRAS - test
* M_ZOMBIE - test

## research
```
  Adding speech
  example - this can be done in CfxLua 5.4
  voiceNameHash = atStringHash("homer")
  speechContextHash = atStringHash("generic_hi") -- dont include the "_%2d"
  speechHashShitIdk = voiceNameHash ^= speechContextHash
  In Codewalker
  <Item type="ByteArray">
   <Name>speechHashShitIdk</Name>
   <RawData>01 01 00</RawData> -- the first number is how many speech contexts there are ie: generic_hi_01, generic_hi_02 etc, the next one is the "container id". third value no clue. Be aware that this is hex values and not normal integers
  </Item>
  Adding the voice
  <Item type="ByteArray">
   <Name>homer</Name>
   <RawData>00</RawData> im not sure what goes here, it can be 00, but i have seen it be different values for voices.
  </Item>
  <Item type="Container" ntOffset="0">
   <Name>1</Name> this is the "container id", starting from 0
   <ContainerHash>dlc_sp_sounds/homer_simpson</ContainerHash>
  </Item>
```
