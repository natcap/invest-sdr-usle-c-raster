# About
This plugin provides an alternative version of the InVEST Sediment Delivery Ratio (SDR) model. This version expects USLE C values in a raster instead of in the biophysical table.

The inputs required by this model are identical to the those of the [InVEST SDR model](https://storage.googleapis.com/releases.naturalcapitalproject.org/invest-userguide/latest/en/sdr.html), with the following exceptions:
- An additional input is required: USLE C (raster). This is a raster of cover-management factor values for the Universal Soil Loss Equation (USLE). Smaller values (closer to 0) indicate that less erosion is likely to come from this area. Values closer to 1 indicate that more erosion is likely to come from this area.
- The Biophysical Table should not include a `usle_c` column. If you provide a biophysical table with a `usle_c` column, that column will be ignored. USLE C values are read from the USLE C raster instead.
