AIFS vs ERA5 RMSE Analysis (Central Europe, 10 days)

This project evaluates AIFS Single forecasts against ERA5 reanalysis by computing RMSE over a Central Europe region for a 10-day period. The main focus of the project is on robust data handling, automation, and reproducible processing, rather than on scientific interpretation of forecast performance.

The workflow includes robust downloading of AIFS and ERA5 data, handling short data availability windows through daily automation, and implementing safeguards against network failures, incomplete downloads, and storage limits. Forecast–reanalysis pairing is performed rigorously by computing valid times from AIFS initialization time and lead time and matching them with ERA5 analysis times, while avoiding unnecessary file openings.

Although AIFS is trained on ERA5, their grids are not exactly identical; therefore, grid alignment and longitude reordering are explicitly checked and corrected before RMSE computation. RMSE is computed per grid cell and aggregated by lead time, day, and hour, with results stored in NetCDF format for efficient reuse.

The pipeline produces diagnostic plots based on the computed RMSE fields, including spatial RMSE maps and comparisons using different background datasets such as land–sea masks, orography, and climate-region context. Overall, the project demonstrates a complete, automated, and robust processing pipeline for comparing operational forecast data with reanalysis products.