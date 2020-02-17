# ![MakerGear Logo](https://cdn.shopify.com/s/files/1/0030/7372/files/mg_logo_colors_small.jpg) M3 Profiles for Simplify3D
Official Repository of Simplify3D profiles for the MakerGear M3 3D Printer. We're adding new materials continuously so check back frequently.

### Simplify 3D Users
We will be working on a video and article for dual workflow. We recommend using the factory files in 	
	Simplify3D- > Independent Dual -> factoryFiles


### Profile Description
| Abbreviation | Description |
| ----------- | ----------- |
| M3ID 2 Color.factory | 2 Color/ 2 model prints |
| M3ID Duplication.factory | Single model prints, once printing with each extruder simultaneously |
| M3ID Left Only.factory | Left Extruder only |
| M3ID Right Only.factory | Right Extruder only |


### How to Print with Two Colors (Same Material)
Here is how to manually import the FFF profiles into Simplify3D:
1. File -> Import FFF Profile 
	Pick 'MakerGear M3 ID Base.fff', located in Simplify3D- > Independent Dual -> MakerGear M3 ID Base.fff
2. Import both models into S3D
3. Align both models in your workspace.
	Typically the easiest way to do this is to select both models and go to
		Edit -> Align Selected Model Origins
	However if your models were created incorrectly you may need to manually adjust the model positions
4. You can double-click a single model to bring up the Position/Scaling/Rotation sidebar on the right
5. Select both models in the Models sidebar on the left
6. You can now use the Position/Scaling/Rotation window to adjust your model
	NOTE: All models must fit between X positions X25 and X200.
7. Create a new Process and pick the "MakerGear M3 ID" profile
8. Select "Both Extruders T0" from the Auto-Configure Extruders Drop Down
9. Click 'Select Models' and pick the model for T0
10. Create a new Process and pick the "MakerGear M3 ID" profile
11. Select "Both Extruders T1" from the Auto-Configure Extruders Drop Down
12. Click 'Select Models' and pick the model for T1
13. Adjust any settings you need to in your processes
14. Select both processes and click 'Prepare to print'
15. Make sure your processes are sliced correctly in the pop-up window that appears, and click 'OK'
16. Check your G-code preview
17. Click 'Save Toolpaths to Disk' and save your Gcode to your computer
18. Upload your Gcode to Your M3ID via OctoPrint
19. Print your Gcode

### Misc Notes
The default profiles use both Ooze shield and a prime pillar. For faster prints you may wish to disable one or the other.

### A Note to Duplication Mode users
To correctly use duplication mode your two hotends must have a correct physical Z-Height. Use the following instructions to check your hot-ends.

1. From the Terminal Tab, enter
	M503
and click 'Send'

2. Now look for a line that looks like

	`Recv: echo:  M218 T1 X252.00 Y0.00 Z-0.08`

	(It may help you to click 'Autoscroll' to turn off the autoscroll function)

3. The value that follows 'Z' must be between -.1 and .1. If the value is 

4. If the value is outside of this range, you will need to physically reset your hotend positions. This will be addressed in a future version of the plugin.

### Other Duplication Mode notes
* For duplication mode you only need one process, the T0 process. There is a option for Duplication mode in the Extruder Auto drop-down.
* Your entire model must fit between X positions  X0 and X100.
* We recommend that duplication users use a raft to help smooth out any differences in Z-Height.
* Simplify3D will only show you a preview of the T0 model in the Gcode preview: you will not see the T0 model.



