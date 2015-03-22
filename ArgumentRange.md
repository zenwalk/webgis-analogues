## What are the values that each argument of the `createParameters()` function can take? ##

As this interface is provided with a limited amount of data, and also due to memory constraints and to avoid server failures, we provide a general overview of the values that each parameter in the interface can take. All these values are related with the `createParameters()` function, which is the `analogues` initialization function:

| **Arguments** | **Suggested range** |
|:--------------|:--------------------|
| x | Values between -180 and 180. Can be decimal, but ensure the combination `x,y` falls in land areas |
| y | Values between -60 and 90. Can be decimal, but ensure the combination `x,y` falls within land areas |
| method | Can **ONLY** be `"ccafs"` or `"hal"`, in lower case letters, and quoted. |
| hal.rad | Vector of length 2 (`c(a,b)`), in which `a` will be taken for temperature and `b` for rainfall. Both positions can be set to `NA`, or can take any numeric value > 0 |
| hal.mad | Vector of length 2 (`c(a,b)`), in which `a` will be taken for temperature and `b` for rainfall. Both positions can be set to `NA`, or can take any numeric value > 0 |
| hal.mrd | Vector of length 2 (`c(a,b)`), in which `a` will be taken for temperature and `b` for rainfall. Both positions can be set to `NA`, or can take any numeric value > 0. Please, make sure that at least one of `hal.rad`, `hal.mad` and `hal.mrd` has at least one position with a value. |
| z | Any value > 1. Please avoid very big (i.e. > 10) values |
| scenario | First element **MUST** always be `"current"`, 2nd and following elements as with the example data: `"a1b_2020_2049_bccr_bcm2_0"`, `"a1b_2020_2049_cccma_cgcm3_1_t47"`, `"a1b_2020_2049_cccma_cgcm3_1_t63"`, `"a1b_2020_2049_cnrm_cmr"`, `"a1b_2020_2049_csiro_mk3_0"`, `"a1b_2020_2049_csiro_mk3_5"`, `"a1b_2020_2049_gfdl_cm2_0"`, `"a1b_2020_2049_gfdl_cm2_1"`, `"a1b_2020_2049_giss_aom"`, `"a1b_2020_2049_giss_model_eh"`, `"a1b_2020_2049_giss_model_er"`, `"a1b_2020_2049_iap_fgoals1_0_g"`, `"a1b_2020_2049_ingv_echam4"`, `"a1b_2020_2049_inm_cm3_0"`, `"a1b_2020_2049_ipsl_cm4"`, `"a1b_2020_2049_miroc3_2_hires"`, `"a1b_2020_2049_miroc3_2_medres"`, `"a1b_2020_2049_miub_echo_g"`, `"a1b_2020_2049_mpi_echam5"`, `"a1b_2020_2049_mri_cgcm2_3_2a"`, `"a1b_2020_2049_ncar_ccsm3_0"`, `"a1b_2020_2049_ncar_pcm1"`, `"a1b_2020_2049_ukmo_hadcm3"`, `"a1b_2020_2049_ukmo_hadgem1"`  |
| vars | Can be `"tmean"`, `"prec"`, or `c("tmean","prec")` |
| weights | Can be `"dtr"` or any value. And **MUST** be equal length to `vars`. If `length(vars)=2` then `weights=c(1,1)`, or `weights=("dtr",1)` |
| ndivisions | 12 |
| env.data | Directory to server's climate data? Should not be an option to the user |
| ext | `".asc"`. Should not be an option to the user. |
| direction | One of three values: `"backward"`, `"forward"`, or `"none"` |
| growing.season | Can be only 1 month, or many consecutive months up to 12. The series of months **MUST** be continuous, but please take into account that `c(10:12,1:3)` is still a continuous series, as month 1 follows month 12 (of the previous year) |
| accross.year | Switch. Can **ONLY** be `TRUE` or `FALSE`, or alternatively `T` or `F`.|
| normalise | Switch. Can **ONLY** be `TRUE` or `FALSE`, or alternatively `T` or `F`. |
| keep.lag	 | Keep always as `FALSE` or `F`. Users don't need to have access to this parameter. |