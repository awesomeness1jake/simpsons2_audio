# simpsons2_audio
simpsons.

### this is used for the "simpsons_music_player", and was mainly created from testing and having fun while doing so.
Sorry for the wonky naming conventions of certain speeches, and how some voicelines are used incorrectly.

## Speech
- Bart - Bart
- Frk - Dr. Frink
- Hom - Homer
- Mrg - Marge



## Music
- SUNDAY_DRIVE | Finished
- HIT_RUN | Finished

# Research

  ### Oddities
  - Speech AWCs had to be done through openIV using flag "DescriptorsInOrder True" without that flag the audio wouldn't play.
  - The Speech AWCs cannot be opened on Codewalker

  ### Getting the speech hash thing (idk what this would be called)
  #### I did not find out how the hashing was done. I found this from https://github.com/Parik27/V.Rainbomizer/blob/master/scripts/voice-line-gen.py#L52
  #### example - Lua
  ```lua
  voiceNameHash = joaat("homer")
  speechContextHash = joaat("generic_hi") -- dont include the "_%02d"
  speechHashShitIdk = (voiceNameHash ~ speechContextHash); -- in hex (b445c9b3)
  ```
  #### example - CS
  ```cs
  uint voiceNameHash = joaat("homer");
  uint speechContextHash = joaat("generic_hi"); // dont include the "_%02d"
  uint speechHashShitIdk = (voiceNameHash ^ speechContextHash); // in hex (b445c9b3)
  ```

# In Codewalker
   ### This should be done preferably in a file named "*_speech.dat4.rel.xml" as it might lead to the bad
   ## Adding the speech
   ```xml 
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
   ```
   ## Adding the voice
   ```xml
   Name
          Voice Name
   RawData
          I'm not sure what goes here, it can be 00, but i have seen it be different values for voices.
   
   <Item type="ByteArray">
       <Name>homer</Name>
       <RawData>00</RawData>
   </Item>
   ```
   ## Adding the container
   ```xml
   Name
          This is the "container id", starting from 0
   ContainerHash
          The AWC Directory   

   <Item type="Container" ntOffset="0">
      <Name>1</Name> 
      <ContainerHash>dlc_sp_sounds/homer_simpson</ContainerHash>
   </Item>
   ```
