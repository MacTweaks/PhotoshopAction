**Photoshop Action for artFileTool**

This will cause the GUI to display what look like glitches because the modified files will not be the right dimensions. Only test a few folders each time so that you can still navigate properly.

I split the artfiles folder into groups and then added them to ArtFile.bin sequentially to narrow down on what folders have effected which elements and so that I could still navigate the interface.


**How to Make a Photoshop Action**

1. Open Action Tab via Window > Action 
2. Press New Folder 
3. Press New Action
4. Import one of the .png files 
5. Press Record 
6. Delete the layer and/or add fill layer  
7. Stop Record 
8. Open File > Script 


**Photoshop Action**

1. Install Xcode 

2. Install Command Line Tools 

3. Install https://www.macports.org/

4. Install http://www.imagemagick.org/script/index.php

5. Run the Photoshop Action 

6. Delete all .png files using the search function in Finder 

7. In Terminal cd to the folder 

8. Convert .psd files to .png 

```find . -type f -iname '*.psd' | sed -E "s/^((.*)\.psd)$/convert '\1' '\2.png'/" | bash```

9. Delete all .psd files using the search function in Finder 

10. Rename files ending in -01 

```find . -type f -iname '*-0.png' | sed -E "s/^((.*)-0.png)$/mv '\1' '\2'.png/" | bash```

11. Delete files ending in all other numbers 

```find . -type f -iname '*-[123456789].png' -delete```

