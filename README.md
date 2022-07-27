# Land-Cover-Land-Use-for-Muranga-Ke-and-Kilimanjaro-TZ
1. Step: Download monthly maximum NDVI composites from Google Earth Engine (java)

2. Step: Download NDVI time-series (all available images within defined period) and harmonic coefficients from harmonic regression from Google Earth Engine (java)

3. Step: Download CHIRPS precipitation data (monthly sum) from Google Earth Engine (java)

4. Step: Preprocess NDVI time-series: stack data and calculate time-series mean and standard deviation (R)

5. Step: Prepare time-series data for TIMESAT input: convert original time-series to TIMESAT format, calculate harmonically fitted time-series based on harmonic coefficients and original time-series, convert to TIMESAT format (R)

6. Step: Create tuningdata for TIMESAT: extract time-series and precipitation values from training pixels, reformat pixels to small array, convert to TIMESAT format (R)

7. Step: Use TIMESAT and run SG filter for tuning data for all possible parameter sets and export fitted time-series (manually in TIMESAT)

8. Step: Calculate correlation between fitted time-series (Step 7) and precipitation of tuning data --> decide for the parameter set with the highest correlation (R)

9. Step: Use TIMESAT to calculate phenological metrics, (a) SG-filter with parameter set from Step 8, (b) harmonically fitted time-series, export phenological metrics (manually in TIMESAT)

10. Step: Export TIMESAT results: convert results to tiff files, stack metrics to layer stack, apply filter to extract seasons within study period (R)

11. Step: Run random forest classifications for all predictor sets (R)

