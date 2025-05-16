# InVEST Plugin: Sediment Delivery Ratio with USLE C Raster Input

## About
A plugin for InVEST that provides an alternative version of the InVEST Sediment Delivery Ratio (SDR) model. This version expects USLE C values in a raster instead of in the biophysical table.

## Usage
1. First, install this plugin. The easiest way to do this is via the InVEST Workbench (version 3.16.0 or later). You can download and install this plugin using its git URL (`https://github.com/natcap/invest-sdr-usle-c-raster.git`), or, if you prefer, you can clone this repo to your computer and then install it using the path to your local copy.
2. Once the plugin has been installed, you can run it from the Workbench, just as you would run any InVEST model.

## Data Needs
The inputs required by this model are identical to the those of the InVEST SDR model, with the following exceptions:
1. An additional input is required: USLE C (raster): Cover-management factor for the USLE. Smaller values (closer to 0) indicate that less erosion is likely to come from this area. Values closer to 1 indicate that more erosion is likely to come from this area.
2. The Biophysical Table should not include a `usle_c` column. If you provide a biophysical table with a `usle_c` column, that column will be ignored. USLE C values are read from the USLE C raster instead.

For details about all other inputs, refer to the [InVEST SDR Data Needs in the InVEST User Guide](http://releases.naturalcapitalproject.org/invest-userguide/latest/en/sdr.html#data-needs).

## Sample Data
Sample data are provided for example/testing purposes only. For more information about the sample data and their sources, refer to the [sample data README](sample-data/_README_InVEST_SDR_USLE_C_Raster_sample_data.txt).

## Testing
Tests rely on `pytest`, which is _not_ included in the project dependencies, since the model itself does not require it. To run the tests:
1. Activate a virtual environment and ensure `pytest` is installed (e.g., via `mamba install pytest` or `conda install pytest`).
2. From the root of this repository, run `pytest tests`.
