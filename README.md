# OctoPrint and OctoLapse Profiles for Prusa XL Multi Tool 3D Printers
Requires Prusa Firmware 5.1.0 or Higher

In this repo you will find a couple of files you can import into OctoPrint to enable both OctoPrint control and OctoLapse timelapse for use with a Prusa XL 5 Head Multi-Tool 3D Printer.

I originally created these profiles by modifying the OctoPrint and OctoLapse Prusa MINI profiles to have a larger bed area, multiple tool heads, and slightly different x y offsets than the Prusa Mini profiles had.

# OcotoPrint Configuration
OctoPrint reqires that you either maunally enter the printer's information, or use the built in API to upload new printer profiles. 

To get started with the API, clone or download this repo, then check out OcotoPrint's documentation at the following link to learn how to use the API to upload the OctoPrintPrusaXL.json found in this repo : https://docs.octoprint.org/en/master/api/printerprofiles.html

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
6. Click the Confirm button to add the new profile to OctoPrint.
7. Back on the Printer Profiles, screen, click the star icon next to your new printer proflie to make it the default for OctoPrint.


# OctoLapse Configuration
1. Navigate to OctoPrint Settings -> Plugins -> OctoLapse
2. Click the Import Settings... button
3. Navigate your local storage to where you've saved OctoLapse - Prusa XL - Breit Ideas Inc v0.9 settings.json
4. Select OctoLapse - Prusa XL - Breit Ideas Inc v0.9 settings.json and click Import.
5. Click the Printers tab in the OctoLapse setting window.
6. Click the star icon next to "Prusa XL - Breit Ideas Inc. v0.9" to set it as the default profile for OctoLapse.
