---
title: 'Generate the ManiaScript references'
taxonomy:
    category:
        - docs
---


>>>>>> The latest Maniaplanet reference generation can be found here: [https://maniaplanet.github.io/maniascript-reference/](https://maniaplanet.github.io/maniascript-reference/)

Generate an html version of the documentation
======================

If you take a look at the file generated by ManiaPlanet you will see that it's not really user friendly and not always comfortable to use. Some tools allow you to generate a nicer documentation in a lot of different formats. Here I'll only talk about Doxygen, but there is a lot of other tools available.

>>>>>> The latest Maniaplanet reference generation can be found here: [https://maniaplanet.github.io/maniascript-reference/](https://maniaplanet.github.io/maniascript-reference/)

![](doc-exemple.png)

1. Download Doxygen on the official website: [www.doxygen.org‎](http://www.stack.nl/~dimitri/doxygen/download.html#srcbin‎) (doxygen-1.8.13-setup.exe at the time of writing)
2. Install Doxygen, it should be pretty straightforward. Just be sure to select the Doxywizard GUI component during the process.
3. We will try to keep a clean working environment. Create a folder and name it "ManiaScriptDocumentation".
4. In this folder create 3 sub-folders:
	* Working
	* Sources
	* Documentation
5. Edit the GenerateDoc.bat file that you created earlier in the ManiaPlanet folder to make it generate the documentation in our new Sources folder: `ManiaPlanet.exe  /generatescriptdoc=C:\Path\To\ManiaScriptDocumentation\Sources\doc.h`.
6. Run GenerateDoc.bat and check that there is now a doc.h file inside the Sources folder.
7. Run Doxywizard (StartMenu > doxygen > Doxywizard).
8. In the top field (step 1), select the Working directory you created earlier.
9. In the Wizard tab we will configure how the documentation will be generated.
	* Project
		* Project Name: give a name to the documentation.
		* Project synopsis: a brief description about the documentation.
		* Project version or id: a version number.
		* Project logo: a logo to display on the documentation.
		* Source code directory: here select the Sources directory we created before.
		* Scan recursively: you can leave it unchecked.
		* Destination directory: this time select the Documentation directory.
	* Mode
		* Leave the default settings.
	* Output
		* Check HTML and select "with navigation panel". You can also change the color of the documentation here.
		* Uncheck the other formats (LaTeX, Man pages, RTF, XML).
	* Diagrams
		* Select "Use built-in class diagram generator".
10. We won't do anything in the Expert tab, so you can click directly on the Run tab.
11. Click on "Run doxygen". Doxygen will now generate the documentation. Once it's done, just click on the "Show HTML output" button to see your brand new documentation in HTML format.
12. __IMPORTANT:__ before closing Doxywizard, remember to save your settings. To do that click on File > Save As at the top of the window and save the configuration file into the Working directory.
13. You can also click on Settings > Use current settings at startup to load your configuration automatically each time you launch Doxywizard.

Example / Advanced
======================

You can find a fully working documentation batch generator [here (.zip)](http://utils.bside-community.com/CreateDoc.zip).
Follow the ReadMe.txt instruction to get it working.

1. Open the Working directory
2. Edit the GenerateDoc.bat file
3. Change the first three lines
	* ManiaPlanetDrive: set the drive letter of the hard disk containing ManiaPlanet
	* ManiaPlanetDir: set the directory where the ManiaPlanet.exe is
	* DoxygenDir: set the directory where the doxygen.exe is
4. Save the file and quit
5. Double click on GenerateDoc.bat
6. Close the ManiaPlanet window
7. Press enter to close the Windows command prompt
8. Open the index.html file with your Internet browser to read the documentation