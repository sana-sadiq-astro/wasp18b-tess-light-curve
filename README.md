# Measuring the orbit and size of the exoplanet WASP-18 b from TESS data

Author: Sana Sadiq

## What this project does
I used public TESS data to recover the orbital period, transit depth and planet radius of the hot Jupiter WASP-18 b, and compared my results with published values.

## Data
NASA TESS, target TIC 100100827 (WASP-18), SPOC 2-minute cadence, accessed with Lightkurve.
- Sector 2: main analysis
- Sector 3: independent check

## Method
1. Download and normalize the light curve.
2. Remove slow trends with a flattening filter.
3. Search for repeating dips with a Box Least Squares (BLS) periodogram.
4. Fold the data on the best period.
5. Convert the transit depth to a planet radius.

## Results
| | This analysis | Published (NASA Exoplanet Archive) |
|---|---|---|
| Orbital period | 0.9415 d (Sector 2), 0.9412 d (Sector 3) | 0.94145 d |
| Transit depth | about 0.95% (Sector 2), 0.96% (Sector 3) | n/a |
| Planet radius | about 1.19 Jupiter radii | 1.24 +/- 0.08 Jupiter radii |

The two sectors agree, and my radius is within the published uncertainty. The stellar radius used (1.2561 solar radii) is from the NASA Exoplanet Archive.

## Limitations
- BLS duration was tested on a coarse grid, so the duration is a rough estimate.
- I did not fit a full transit model, so the radius ignores limb darkening.
- The main analysis uses one sector; Sector 3 is an independent check.

## Files
- `WASP_18b_TESS_transit_analysis.ipynb`: full code and outputs

## Related project
A follow-up project measures the timing of every WASP-18 b transit across 10 TESS sectors: see `transit-timing-pipeline`.
