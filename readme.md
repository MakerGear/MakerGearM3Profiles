# ![MakerGear Logo](https://cdn.shopify.com/s/files/1/0030/7372/files/mg_logo_colors_small.jpg) M3 Profiles for Simplify3D
Official Repository of Simplify3D profiles for the MakerGear M3 3D Printer. We're adding new materials continuously so check back frequently.

### Installation Video
View the installation video on [MakerGear M3 Profile Installation Video on YouTube](https://youtu.be/WvLeIx0g9G8).


### Profile Description
| Abbreviation | Description |
| ----------- | ----------- |
| M3ID 2 Color.factory | Great for 2-Color Printing - both extruders use the same mat'l type, but different colors |
| M3ID Duplication.factory | Print two copies of the same object at once  |
| M3ID Left Only.factory | Use only the Left Extruder - Tool 0 (T0) |
| M3ID Right Only.factory | User only the Right Extruder - Tool 1 (T1) |


### Two-Color Printing Instructions (Same Material Type)
1. Manually import the FFF profiles into Simplify3D (if you have not already done so):
	* `File -> Import FFF Profile` 
	* Pick `MakerGear M3 ID Base.fff`, located in `Simplify3D- > Independent Dual -> MakerGear M3 ID Base.fff`
2. Import both of your STL models into Simplify3D
3. Align both models in your workspace. Typically the easiest way to do this is to select both models and go to: 
	* `Edit -> Align Selected Model Origins`
	* However if your models were created incorrectly you may need to manually adjust the model positions
	* Note: You can double-click a single model to bring up the Position/Scaling/Rotation sidebar on the right
4. Select both models in the Models sidebar on the left
5. You can now use the Position/Scaling/Rotation window to adjust your model
	* Note: All models must fit between X positions X25 and X200.
6. Create a new Process and pick the "MakerGear M3 ID" profile
7. Select "Both Extruders T0" from the Auto-Configure Extruders Drop Down
8. Click 'Select Models' and pick the model for T0
9. Create a new Process and pick the "MakerGear M3 ID" profile
10. Select "Both Extruders T1" from the Auto-Configure Extruders Drop Down
11. Click 'Select Models' and pick the model for T1
12. Adjust any settings you need to in your processes
13. Select both processes and click 'Prepare to print'
14. Make sure your processes are sliced correctly in the pop-up window that appears, and click 'OK'
15. Check your G-code preview
16. Click 'Save Toolpaths to Disk' and save your Gcode to your computer
17. Upload your Gcode to Your M3ID via OctoPrint
18. Print your Gcode

Note: The default profiles for two-color printing use both ooze shield and a prime pillar. For faster prints you may wish to disable one or the other.

### Duplication Mode Instructions
In order to correctly use duplication mode, your two hot-ends must have the correct physical Z-Height. Use the following instructions to check your hot-ends.

1. From the Terminal Tab, enter `M503` and click `Send`

2. Now look for a line that looks like

	`Recv: echo:  M218 T1 X252.00 Y0.00 Z-0.08`

	(It may help you to click 'Autoscroll' to turn off the autoscroll function)

3. The value that follows `Z` must be between -.1 and .1.

4. If the value is outside of this range, you will need to physically reset your hot-end positions. This will be addressed in a future version of the plugin.

#### Additional Duplication Mode Notes
* For duplication mode you only need one process, the T0 process. There is a option for Duplication mode in the Extruder Auto drop-down.
* Your entire model must fit between X positions  X0 and X100.
* We recommend using a raft to help smooth out any differences in Z-Height.
* Simplify3D will only show you a preview of the T0 model in the Gcode preview - you will not see the T0 model.



