# simpsons2_audio
simpsons.

### this isn't meant to have all the audio, this was mainly created from testing and having fun while doing so.

## Speech
- HOMER - Homer | Unfinished
- MRG - Marge | Unfinished
- COLLECT_SOUNDFX - Collect Sound Fx | Finished
- SIMPSONS2_GAMEPLAY - Gameplay Sound Fx for Simpsons | Unfinished [missing sounds]

## Music
- SUNDAY_DRIVE | Finished
- HIT_RUN | Finished

# research

  ### Oddities
  -Speech Audio had to be done through openIV using flag "DescriptorsInOrder True" without that flag the audio wouldn't play.
  -The Speech AWCs cannot be opened on Codewalker

  ### Adding speech
  #### I did not find out how the hashing was done. I found this from https://github.com/Parik27/V.Rainbomizer/blob/master/scripts/voice-line-gen.py#L52
  #### example - this can be done in CfxLua 5.4
  ```lua
  voiceNameHash = joaat("homer")
  speechContextHash = joaat("generic_hi") -- dont include the "_%2d"
  speechHashShitIdk = voiceNameHash ^= speechContextHash; -- in hex (b445c9b3)
  ```

# In Codewalker
   ## Adding the speech
      Name
          Make sure it is in hex
      RawData
          The first number is how many variations there are, ie: generic_hi_01, generic_hi_02 etc.
          The next one is the "container id". 
          Third value no clue. 
          Be aware that this is hex values and not normal integers
      
          <Item type="ByteArray">
           <Name>speechHashShitIdk</Name> 
           <RawData>01 01 00</RawData>
          </Item>

   ### Adding the voice

      Name
          Voice Name
      RawData
          I'm not sure what goes here, it can be 00, but i have seen it be different values for voices.

          <Item type="ByteArray">
           <Name>homer</Name>
           <RawData>00</RawData>
          </Item>

      Name
          This is the "container id", starting from 0
      ContainerHash
          The AWC Directory

          <Item type="Container" ntOffset="0">
           <Name>1</Name> 
           <ContainerHash>dlc_sp_sounds/homer_simpson</ContainerHash>
          </Item>

