# OctoPrint and OctoLapse Profiles for Prusa XL Multi Tool 3D Printers
Requires Prusa Firmware 5.1.0 or Higher

In this repo you will find a couple of files you can import into OctoPrint to enable both OctoPrint control and OctoLapse timelapse for use with a Prusa XL 5 Head Multi-Tool 3D Printer.

I originally created these profiles by modifying the OctoPrint and OctoLapse Prusa MINI profiles to have a larger bed area, multiple tool heads, and slightly different x y offsets than the Prusa Mini profiles had.

# OcotoPrint Configuration
OctoPrint reqires that you either maunally enter the printer's information, or use the built in API to upload new printer profiles. 

To get started with the API, clone or download this repo, then check out OctoPrint's documentation at the following link to learn how to use the API to upload the OctoPrintPrusaXL.json found in this repo: https://docs.octoprint.org/en/master/api/printerprofiles.html

To manually configure OctoPrint, follow these steps, ensuring your new printer profile looks like the screenshots in the Screenshots folder within this repo.

1. Navigate to OctoPrint Settings -> Printer -> Printer Profiles
2. Click the + Add Profile... button
3. In the General tab's fields, enter the following information
    1. Name: Prusa XL
    2. Identifier: _default
    3. Model: Prusa XL
4. In the Print bed & build volume tab's fields, configure the following fields
    1. Form Factor: Rectangular
    2. Origin: Lower Left
    3. Heated Bed: Checked
    4. Heated Chamber: Unchecked
    5. Width (X): 360 mm
    6. Depth (Y): 360 mm
    7. Height (Z): 360 mm
5. Custom Bounding Box: Checked
    1. X Coordinates: Min: -10 Max 360
    2. Y Coordinates: Min: 0 Max 360
    3. Z Coordinates: Min -1 MAx: 360
6. In the Axes tab's fields, configure the following:
    1. X: 6000
    2. Y: 6000
    3. Z: 200
    4. E: 300
7. In the Hotend & extruder tab, configure the following:
    1. Nozzle Diameter: 0.4 or whatever size you're using. This screen doesn't have multiple fields to accommodate multiple nozzle sizes, but I do have both 0.4 and 0.6 nozzles installed on my Prusa XL right now. I have this field set to 0.4 and am able to use both nozzle sizes just fine so not sure how important this field really is.
    3. Number of Extruders: 5 or however many you have
    4. Shared Nozzle: Unchecked
    5. Offset T1: X: 0 Y: 0
    6. Offset T2: X: 0 Y: 0
    7. Offset T3: X: 0 Y: 0
    8. Offset T4: X: 0 Y: 0
    9. Default extrusion length: 5 mm
8. Click the Confirm button to add the new profile to OctoPrint.
9. Back on the Printer Profiles screen, click the star icon next to your new printer proflie to make it the default for OctoPrint.


# OctoLapse Configuration
1. Navigate to OctoPrint Settings -> Plugins -> OctoLapse
2. Click the Import Settings... button
3. Navigate your local storage to where you've saved OctoLapse - Prusa XL - Breit Ideas Inc v0.9 settings.json
4. Select OctoLapse - Prusa XL - Breit Ideas Inc v0.9 settings.json and click Import.
5. Click the Printers tab in the OctoLapse setting window.
6. Click the star icon next to "Prusa XL - Breit Ideas Inc. v0.9" to set it as the default profile for OctoLapse.

# Printing, Shooting Time-lapse Videos, and Known Issues
If you've completed the configuration sections and connected your Raspberry Pi to the Prusa XL's USB C port, you should be ready to start printing. In PrusaSlicer's settings, I suggested disabling Prusa's bgcode generation for each printing project you do and go with standard gcode, unless you install additional OcotoPrint plugins. I have not tested the OctoPrint bgcode plugin with this setup personally, I just stick with standard gcode.

When you start a print with OctoPrint, do not be surprised if the printer starts its autohoming and bed mesh calibration, then stops for 5-8 minutes - this is the Prusa XL's built in "absorbing heat" feature and you won't see any indication this is what is going on in OcotoPrint or on the Prusa XL's screen, like you would normally see when doing a USB drive based print job. I have not found a way to ask the Prusa XL to skip the absorbing heat step, but my printer does start printing after the same amount of time you'd expect if you did see that "Absorbing Heat" message on the Prusa XL's screen.

I haven't had any trouble with Octolapse settings but you should be aware that your print time can vary widely depending on these settings and the number of tool changes in your print.

On occasion, OcotoPrint may pop up a warning telling you the object(s) you are about to print are too big for the build area. As long as you are confident your print is not bigger than the Prusa XL's max of 360x360x360 mm, try clicking the Print button one more time. I have yet to run into any issues with this workaround and I'm not sure what exactly is causing the popup warning.
