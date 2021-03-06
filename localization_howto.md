# Running ZOLA PSF localization on test dataset
We provide instructions on how to run 3D localizations on the test data from the ZOLA package.

## Test data

Download and unzip [TEST-DATA.zip](https://github.com/imodpasteur/ZOLA-3D/releases/download/v0.1.9/TEST-DATA.zip) to get Mitochondria test data.

Mitochondrial protein TOM22 immunolabelled with Alexa 647 with corresponding bead calibration stack is imaged using tetrapod PSF.

## Localization

1. Open Mitochondria-tetrapod/data/Mito-sp4-SR-data-crop-small.tif
2. Select `Plugins` -> `ZOLA` -> `Localization` and enter optical and computational parameters. Click OK to start localization.

![localization dialog](https://github.com/imodpasteur/ZOLA-3D/blob/master/img/ZOLA_loc_mito_screenshot.png)

3. You will soon see automatically updated color-coded histogram.

![automatic histogram](https://github.com/imodpasteur/ZOLA-3D/blob/master/img/ZOLA_loc_mito_2D_hist20nm.png)

4. Once localization is done (elapsed time ~4 minutes on our Tesla GPU), you can filter the localization table.
Select `Plugins` -> `ZOLA -> Filtering`.
You will see three new windows: disclaimer, scatter plot which can be used to select ROI, and brightness and contrast dialog, which represents now histogram on z localizations.
We select a broad peak corresponding to the useful data and avoiding artifacts in the lower part of the axial range.
Click OK, enter maximum value of Chi2 = 3 and click OK once again.
Now our table is filtered.

![filtering dialog](https://github.com/imodpasteur/ZOLA-3D/blob/master/img/ZOLA_loc_filter.png)

5. In order to an axial projection we need to generate 3D histogram `Plugins` -> `ZOLA -> Visualization -> 2D/3D historgam`

![histogram dialog](https://github.com/imodpasteur/ZOLA-3D/blob/master/img/ZOLA_loc_hist_dialog.png)

6. Next, run `Reslice` (keyboard shortcut '/') form the left to see YZ stack. Mitochondrial organelles' hollow structure is readily apparent.

![mito ZY projection](https://github.com/imodpasteur/ZOLA-3D/blob/master/img/ZOLA_loc_mito_reslice.gif)

7. Don't forget to save updated localization table `Plugins` -> `ZOLA -> Import/Export -> Export table`
