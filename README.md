sfa_scripts
-------------
**Name:** Brett Austin  
  **Directory Structure:** `sfa_scripts/src/smartsave.py` contains the entirety of the code sample\
  **Explanation of Code Sample:** A smart save tool for use in Maya. Creates a standardized file naming convention as well as a navigable GUI.
  - A) `smartsave.py` needs to be in your `\Documents\maya\scripts` folder for this to work. Allows user to open the GUI that is implemented with PySide 2 by calling these commands in the Maya Script Editor:
  ```
  import smartsave
  reload (smartsave)
  
  sm = smartsave.SmartSaveUI()
  sm.show()
  ```
  These commands can be condensed into a clickable button on the Maya Shelf simply by choosing the Save Script to Shelf option in the Maya Script Editor.
  - B) Resizes responsively with:
      - Sensible width and height limits
      - Each widget remaining visible while the window is resizing
      - Task and version boxes have fixed widths, meaning it won't go higher than a set amount when resizing
      - Descriptor field expands when resizing
  - C) Initializes a default text value of a widget to the default specified by the scene file object **(Ex: main_model_v001.ma)**
      - Descriptor Default: main
      - Task Default: model
      - Version Default: 1
  - D) Saving untitled Maya scene renames it to chosen convention such as previous example of **main_model_v001.ma**
  - E) Folder path input field, when in an untitled scene, defaults to the `/maya/projects/default/scenes` folder once the user saves
  - F) If no path and no scene is specified by the user, defaults to the `/maya/projects/default/scenes` folder with a preset default naming convention once the user saves
  - G) Folder path input field, when in an existing named scene, defaults to the path of the currently opened scene once the user saves
  - H) If a folder directory in a path doesn't exist, a warning is logged and a folder is created in the necessary spot once the user saves
  - I) Folder browse button lets user browse through directories and select a folder path
      - Updates the folder path input field with the newly selected folder path
  - J) Save Increment button allows user to:
      - Saves current scene to the next available version in the folder path
      - GUI updates to reflect the new version after the save occurs
      - Increments to the highest version even if there are skipped versions **(Ex: _v003 and _v006 means the next would be _v007)**
      
**Date when Code was Written (Excluding Updates to Readme):**\
First Commit: February 27, 2021\
Final Commit: March 26, 2021
