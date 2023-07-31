# 3D Printers
![Picture of Ultimaker 3D Printer](https://cdn.discordapp.com/attachments/983922080879869962/1135469515489148998/Ultimaker_History_-_6_Ultimaker_2.png)
## What is a 3D Printer?
A 3D printer creates a 3D object layer by layer only where material is needed. In doing this, you can make custom parts for exactly what you want. If you can design it, a 3D printer can make it. :D
## Why use a 3D Printer?
Using a 3D printer versus something like a Laser Cutter has its advantages. With a Laser Cutter, you are limited to the piece of material that you put in. But, if you are creating multiple flat objects, a Laser Cutter can do it faster, and more efficiently. Typically, when using a Laser Cutter, you also need a air filtration system, but with some materials in 3D Printing, you do not need a filtration system.

## Types of 3D Printers
### FDM (Fused Deposition Modeling)
FDM or Fused Deposition Modeling is the most common form of 3D printing thanks to its ease of use and cost-effectiveness. FDM printing uses a strand of plastic which is melted and pushed through a nozzle to form your model. 
### SLA (Stereolithography)
SLA or Stereolithography is a resin based form of 3D printing. This uses a UV based resin and a screen to cure the resin in certain spots. Resin printing tends to have great detail and quality, but has toxic fumes, and must be cured in a light box after printing. 
### SLS (Selective Laser Sintering)
SLS or Selective Laser Sintering is a very expensive form of 3D printing which uses lasers and a powder which is melted to form your 3D model. With SLS, you can print with extremely advanced materials, and even metal. The cleanup tends to be a little messy, and due to its price is usually only used in enterprise applications. 

## Common Types of Filament for FDM
![Picture of Filament](https://cdn.discordapp.com/attachments/898001388288741426/1135480694538240000/lighter.png)
### PLA (Polylactic Acid)
PLA or Polylactic Acid is a starch based filament, and is one of the most popular 3D printing filaments thanks to it not needing an enclosure, heated bed, and it not putting off toxic fumes. PLA has a glass transition temperature (around 65°C) which is the temperature where the material starts to deform. PLA prefers to be printed around 200°C. PLA is structurally strong, but deforms easily under pressures, and is not UV resistant. 
### PET-G (Polyethylene Terephthalate Glycol)
PET-G or Polyethylene Terephthalate Glycol is a polymer that is very similar to soda bottles. This is another popular 3D printing filament due it not needing an enclosure along with it not putting off toxic fumes. PET-G needs a heated bed. When printing PET-G on a glass bed, make sure to put glue stick down to help with release of the material. PET-G has a glass transition temperature of 85°C, and prefers to be printed around 245°C. PET-G tends to bend easier, but does not deform as easily as PLA. PET-G is UV resistant.
### ABS (Acrylonitrile Butadiene Styrene)
ABS or Acrylonitrile Butadiene Styrene is a very interesting type of 3D printing filament. ABS is once again popular for 3D printing, but nto as popular as PLA or PET-G because it requires an enclosure and puts off toxic fumes. ABS needs an enclosure, a heated bed, and a chamber filter to filter out the toxic fumes. ABS has a glass transition temperature of about 105°. ABS likes to be printed at 250°C. When printing with ABS, you parts will strink due to warping so take that into consideration when designing. 
## Components
### Hotend
The hotend is the piece of a 3D printer that heats and extruders the molten filament onto the bed.

![Picture of Nozzle](https://cdn.discordapp.com/attachments/898001388288741426/1135474400028807168/Extruder.png)

### Extruder
The extruder is the piece of the 3D printer that pushes the filament into the hotend creating flow.

![Picture of Extruder](https://cdn.discordapp.com/attachments/898001388288741426/1135474401131905114/Real_Extruder.png)

### Bed
The bed is where the molten filament sits and "lives" until you take it off the bed. This bed is typically heated to help the filament really stick down. There is typically a steel plate with a coating that magnetically attaches to the bed to help with removal. The most common type is Textured PEI. Another alternative to a steel plate is a glass bed. When using a glass bed, be sure to put some glue stick down to help with removal of the print.

![Picture of Bed](https://cdn.discordapp.com/attachments/898001388288741426/1135476188974948443/IMG_4184.jpg)

## When we use 3D Printers
We use 3D printers to maker complex and intricate parts that can only be achieved by 3D printing. We also use this to make replacement part for tools, use them as templates, and use them as parts on our robot. An example of this is on our 2023 robot as shown below:

![2023 Charged Up Robot](https://cdn.discordapp.com/attachments/898001388288741426/1135484459953684550/Spacer.png)

## Getting Started
### Bambu Labs
The printers that we most commonly use are Bambu Lab's 3D printers. They have disrupted the 3D printing market with their consumer level and prosumer Core XY 3D printers. We use these printers because they are cheap (relativly speaking), dimensionally accurate, and print SUPER fast (if you didn't know, 3D printing is typically VERY VERY slow). Needless to say, these printers achieve everything we want it to, and that is why we use them. 
### Bambu Studio
First, you will need to head to https://bambulab.com/en/download/studio to download the latest version of Bambu Studio for your platform. After doing this, you will need to launch it.

To import your STL to Bambu Studio, you will need to click the cube with a little plus as indicated below
![How to import STL](https://cdn.discordapp.com/attachments/898001388288741426/1135486523974877204/Add_Part.png)

After doing this, you will be asked to select your STL, which it will then open. 

From here, you can select your infill, support, and quality settings. 
![How to change settings](https://cdn.discordapp.com/attachments/898001388288741426/1135487340580712499/Your_Settings.png)

If you look to the top of the model, you should see a bar which will let you turn, move, and paint your supports onto your model. 
![Top Bar](https://cdn.discordapp.com/attachments/898001388288741426/1135488126723297290/Bar.png)

After selecting all your settings, you will need to hit Slice Plate which will turn your model into a bunch of code (G-Code)  the printer to move to a certain place on certain layers. 
![Slice](https://cdn.discordapp.com/attachments/898001388288741426/1135488785283567687/Print.png)

Now, you will want to look at the sliced model, and look for areas that may need support. 

After comfirming that the model is ready to print, you will need to press print on the top right. 
![Print](https://cdn.discordapp.com/attachments/898001388288741426/1135489503105142816/Print.png)

Finally, a screen will pop up, prompting you to send it to the printer. Click "Send", and you have successfully send off your first 3D print. 
![Send](https://cdn.discordapp.com/attachments/898001388288741426/1135489999559721032/Send.png)