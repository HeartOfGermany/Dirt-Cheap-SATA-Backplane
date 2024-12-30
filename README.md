# Dirt-Cheap-SATA-Backplane

## Front side (left/first) and back side

<picture>
  <img width="350px" alt="Front side of the SATA Backplane" src="https://github.com/HeartOfGermany/Dirt-Cheap-SATA-Backplane/blob/main/front_side.png">
</picture>
<picture>
  <img width="350px" alt="Back side of the SATA Backplane" src="https://github.com/HeartOfGermany/Dirt-Cheap-SATA-Backplane/blob/main/back_side.png">
</picture>


This repo is intended to share plans for a super cheap DIY backplane. It is using KiCad and it fits the 100x100mm default of JLCPCB

Example: 100x100mm PCB x10pcs costs 15€ delivered to europe as the time of writing this. So 1 Backplane PCB costs just 1.50€ plus components. It uses 1.6mm 2 layer FR4.

## Features:
- LED Indicators
  - Activity LED (Bi-Color support!)
  - HDD Detect LED
  - 12V Power OK
  - 5V Power OK
  - 3.3V Power OK
  - 5V Power generator activated
  - 3.3V Power generator activated
- SATA or Floppy power input (or just solder your custom cable)
  - 12V only input (generate 5V and 3.3V automatically)
  - 12V+5V input (generate 3.3V automatically)
- Optional components
  - Do not need certain Indicators? Than leave them out
  - Do not need 5V or 3.3V generation? Than just do not solder in the converters
  - Just want to solder THT and NO SMD? Can do just that (But Activity LED requires 2 SOT23 transistors - but easier to solder than TO-92!
  - Just want to solder SMD? Also fine!
  - LED indicators to back side or front side? Do as you wish
  - Do not want to solder tons of decoupling? Just leave it out. It is optional and I only use the caps in the converter section of the schematic 

## How to use?
Steps:
1. Develop the board (JLCPCB worked fine for me)
2. Meanwhile order the Components, check the Schematic for purchasing links (no affiliate!)
3. Solder the components as you like
4. Test with an old HDD first!
5. Design some enclosure or cage, where you can screw the PCB onto the backside to slide it in and out again. After all... it is a Hot-Swap SATA Backplane. I used some wooden boards from an old drawer with some cut slots and a laser to get some ventilation slots. Than I used thin ply wood to mount the HDDs on (3mm max. recommended). These ply wood plates can slide in and out on the slotted boards, which form the surrounding. The uplink connectors are on the outside of the board. I will see if I will attach a reference image... Use your brain, it's not hard to build stuff!
6. How to nail alignment? The PCB has some mounting holes. Get yourself some flat standoffs and screw them in. Use some Alc to clean the backplate and the standoffs for adheasion. Now plug an upper and lower HDD in at least, to get the proper alignment. Use a dab of epoxy and just lay it on the backplate. The standoffs will glue in over the course of 24h (some gentle heat like 40-50°C speeds up a lot!) and you can than mount and unmount this as often by just unscrewing the screws (remember: after on comes off, so do not overtorque!). I recommend adding another layer to reinforce the joint and maybe even roughen the standoffs for better adheason, aswell as adding filler like quarz sand to the epoxy, to get a dang resilient, thick bond.

## Attention:
**DO**
- Use Flux. Tons of flux. If you are too cheap, use at least some Rosin intended for inhalation - it comes in 100g bags for just 2-3 bucks and is more efficient than those tiny containers with like 10g rosin.
- How to clean the flux residue easily? Use denatured Alc or Isopropyl to soak and than clean the board. You can also soak the board by wrapping in toilet paper and soaking it in Alc and leav it over night in a bag. Next day use tooth brush and carefully mobilize the rest of residues. Use some more to wash the rest away and your board will look like from factory
- Use enough heat! I make a lot of use of ground planes. Heat joints as fast as possible and go away to not damage components
- SATA connectors are hard to find on many proper stores, I got mine from Aliexpress - just double check the images to the PCB before ordering. The PCB allows some variation (Holes larger than needed). In theory you could also solder SMD equivalents in, if you can find some
- The Schematic contains a section "Parts List". A lot is from LCSC from China. It is like a dirt cheap Mouser/Digikey alternative, but of amazing quality. If you are cheap but want to ensure original components only, go there for your parts!
- Consider a Bismuth solder and some Amtech 559, if you are new to soldering. Requiring like 50K less temperature helps a LOT. It gives a ton of time to work on joints and constantly reflow, without overheating components (Especially ceramic caps are sensitive to re-heating a lot - could short)

**DON'T**
- Do not enable 3.3V or 5V generation, if your power input already supplies it! Check with the Voltage OK LEDs first! Otherwise the tiny buck converters try to provide 5V and 3.3V to your PC, which they cannot handle and they WILL overheat, potentially with permanent damage to the PCB.
- Do not use other thicknesses or materials than 1.6mm FR4!!! These could mess with the differential pair signalling, as the ground plane distance is very important to keep proper impedance
- Do NOT forget to use tons of flux. The PCB is easy to solder, if you use a decent cheap 60€/$ solder station with hot air, if Flux and Solder are good. Leaded solder helps a lot (though not healthy), or bismuth solder. Bismuth solder is a lot more brittle. Ensure, that the fillets form perfectly or rework them before use.
