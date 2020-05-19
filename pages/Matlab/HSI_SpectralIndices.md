---
title: Spectroscopic and Remote Sensing indices
description: Estimation of several chemical parameters based on literature indices. Some were created from spectroscopic and hyperspectral devices, others from remote sensing (multi- and hyper-spectral sensors).
permalink: HSI_SpectralIndices.html
sidebar: Matlab_sidebar
---

# Toolbox
The mandatory data to use this toolbox are a hyperspectral image (M), the corresponding RGB image (RGB), depth (dm), and wavelength (wl). Then, the toolbox will find with wl if it is VNIR or SWIR data. Then, it will propose to you all the possible indices that you can choose to estimate. Finally, an image correlation between the selected indices is made at the end.

## VNIR example
Here we can see an example with lamination. White laminae present higher values that correspond to the diatoms in spring and summer. Whereas dark laminae corresponding to winter have the lowest values.

{% include image.html file="Chloro.jpg" %}

The correlation matrix shows that even if 18 indices are related to chlorophylls and 3 to oxides, they don't have the same trend, so it must be chosen wisely.

{% include image.html file="Corr_VNIR_Indice.jpg" %}

## SWIR example

The reflectance at 1935 nm highlights the moisture abundance, with higher values corresponding to low moisture abundance and inversely. So light deposits seem to have lower moisture than dark ones.

{% include image.html file="Moisture.jpg" %}

The correlation matrix shows that several indices are highly correlated.

{% include image.html file="Corr_SWIR_Indice.jpg" %}

# Spectroscopic and hyperspectral indices:
This toolbox uses the following list of spectroscopic and remote sensing indices. If you find that important resources are not included, please feel free to contact me.
## VNIR 400-1000nm
* Chlorophylls R675/R750 
```markdown
Das, B., Vinebrooke, R.D., Sanchez-azofeifa, A., Rivard, B., Wolfe, A.P. (2005) Inferring sedimentary chlorophyll concentrations with reflectance spectroscopy : a novel approach to reconstructing historical changes in the trophic status of mountain lakes. Canadian Journal of Fisheries and Aquatic Sciences 62: 1067–1078
```
* Chlorophylls R645/R675 
```markdown
Das, B., Vinebrooke, R.D., Sanchez-azofeifa, A., Rivard, B., Wolfe, A.P. (2005) Inferring sedimentary chlorophyll concentrations with reflectance spectroscopy : a novel approach to reconstructing historical changes in the trophic status of mountain lakes. Canadian Journal of Fisheries and Aquatic Sciences 62: 1067–1078
```
* Chlorophylls R660/R670 
```markdown
von Gunten, L., Grosjean, M. (2009) High-resolution, quantitative climate reconstruction over the past 1000 years and pollution history derived from lake sediments in Central Chile. Philosophisch-naturwissenschaftlichen Fakultät 246
```
* Chlorophylls R590/R690 
```markdown
Trachsel, M., Grosjean, M., Schnyder, D., Kamenik, C., Rein, B. (2010) Scanning reflectance spectroscopy (380–730 nm): a novel method for quantitative high-resolution climate reconstructions from minerogenic lake sediments. Journal of Paleolimnology 44: 979–994
```
* Chlorophylls R675-R750 
```markdown
Das, B., Vinebrooke, R.D., Sanchez-azofeifa, A., Rivard, B., Wolfe, A.P. (2005) Inferring sedimentary chlorophyll concentrations with reflectance spectroscopy : a novel approach to reconstructing historical changes in the trophic status of mountain lakes. Canadian Journal of Fisheries and Aquatic Sciences 62: 1067–1078
```
* Chlorophylls R645-R675 
```markdown
Das, B., Vinebrooke, R.D., Sanchez-azofeifa, A., Rivard, B., Wolfe, A.P. (2005) Inferring sedimentary chlorophyll concentrations with reflectance spectroscopy : a novel approach to reconstructing historical changes in the trophic status of mountain lakes. Canadian Journal of Fisheries and Aquatic Sciences 62: 1067–1078
```
* Chlorophylls dR660-dR690 
```markdown
Das, B., Vinebrooke, R.D., Sanchez-azofeifa, A., Rivard, B., Wolfe, A.P. (2005) Inferring sedimentary chlorophyll concentrations with reflectance spectroscopy : a novel approach to reconstructing historical changes in the trophic status of mountain lakes. Canadian Journal of Fisheries and Aquatic Sciences 62: 1067–1078
```
* Chlorophylls d675 
```markdown
Das, B., Vinebrooke, R.D., Sanchez-azofeifa, A., Rivard, B., Wolfe, A.P. (2005) Inferring sedimentary chlorophyll concentrations with reflectance spectroscopy : a novel approach to reconstructing historical changes in the trophic status of mountain lakes. Canadian Journal of Fisheries and Aquatic Sciences 62: 1067–1078
```
* Chlorophylls d690 
```markdown
Wolfe, A.P., Vinebrooke, R.D., Michelutti, N., Rivard, B., Das, B. (2006) Experimental calibration of lake-sediment spectral reflectance to chlorophyll a concentrations: methodology and paleolimnological validation. Journal of Paleolimnology 36: 91–100
```
* Chlorophylls RABD670 
```markdown
Rein, B., Sirocko, F. (2002) In-situ reflectance spectroscopy - analysing techniques for high-resolution pigment logging in sediment cores. International Journal of Earth Sciences 91: 950–954
```
* Chlorophylls I-band 
```markdown
Rein, B., Sirocko, F. (2002) In-situ reflectance spectroscopy - analysing techniques for high-resolution pigment logging in sediment cores. International Journal of Earth Sciences 91: 950–954
```
* Chlorophylls Area650-750 
```markdown
Wolfe, A.P., Vinebrooke, R.D., Michelutti, N., Rivard, B., Das, B. (2006) Experimental calibration of lake-sediment spectral reflectance to chlorophyll a concentrations: methodology and paleolimnological validation. Journal of Paleolimnology 36: 91–100
```
* Chlorophylls Area650-700 
```markdown
Wolfe, A.P., Vinebrooke, R.D., Michelutti, N., Rivard, B., Das, B. (2006) Experimental calibration of lake-sediment spectral reflectance to chlorophyll a concentrations: methodology and paleolimnological validation. Journal of Paleolimnology 36: 91–100
```
* Chlorophylls Area690-730 
```markdown
Trachsel, M., Grosjean, M., Schnyder, D., Kamenik, C., Rein, B. (2010) Scanning reflectance spectroscopy (380–730 nm): a novel method for quantitative high-resolution climate reconstructions from minerogenic lake sediments. Journal of Paleolimnology 44: 979–994
```
* Chlorophylls Area600-760 
```markdown
Das, B., Vinebrooke, R.D., Sanchez-azofeifa, A., Rivard, B., Wolfe, A.P. (2005) Inferring sedimentary chlorophyll concentrations with reflectance spectroscopy : a novel approach to reconstructing historical changes in the trophic status of mountain lakes. Canadian Journal of Fisheries and Aquatic Sciences 62: 1067–1078
```
* Chlorophylls Area600-650 
* Chlorophylls Area690-730 
* Chlorophylls (Area650-700)/R670 
* Phycocyanin (Area600-630)/R615
* Bacteriochlorophyll a RABD846
* Carotenoids RABD510 
```markdown
Rein, B., Sirocko, F. (2002) In-situ reflectance spectroscopy - analysing techniques for high-resolution pigment logging in sediment cores. International Journal of Earth Sciences 91: 950–954
```
* Oxydes d555 
* Oxydes RABA400-560 
* Iron Oxydes R720/R880  
```markdown
Jackisch, R., Lorenz, S., Zimmermann, R., Möckel, R., Gloaguen, R. (2018) Drone-borne hyperspectral monitoring of acid mine drainage: An example from the Sokolov lignite district. Remote Sensing 10: 1–23
```

## SWIR 1000-2500nm
* Clay R2200 
* Clay RABA2190-2230 
* Hydroxyl bonds R1450 
* Moisture R1935 
* R1935/R1450 
* Normalized Differenced Gypsum Ratio (NDGI) 
```markdown
Milewski, R., Chabrillat, S., Brell, M., Schleicher, A.M., Guanter, L. (2019) Assessment of the 1.75 μm absorption feature for gypsum estimation using laboratory, air- and spaceborne hyperspectral sensors. International Journal of Applied Earth Observation and Geoinformation 77: 69–83
```
* Calcite R2340 
```markdown
Sun, L., Khan, S., Godet, A. (2018) Integrated ground-based hyperspectral imaging and geochemical study of the Eagle Ford Group in West Texas. Sedimentary Geology 363: 34–47
```
* Illite-muscovite crystallinity R1900/R2200 
```markdown
Doublier, M.P., Roache, T., Potel, S. (2010) Short-wavelength infrared spectroscopy: A new petrological tool in low-grade to very low-grade pelites. Geology 38: 1031–1034
```
* Kaolinite Crystallinity Index (KCI) 
```markdown
Alonso de Linaje, V., Khan, S.D. (2017) Mapping of diagenetic processes in sandstones using imaging spectroscopy: A case study of the Utrillas Formation, Burgos, Spain. Sedimentary Geology 353: 114–124
```

# Remote sensing indices:
## VNIR 400-1000nm 
* Difference Vegetation Index (DVI)
```markdown
Tucker, C. "Red and Photographic Infrared Linear Combinations for Monitoring Vegetation. Remote Sensing of Environment 8 (1979): 127–150
```
* Enhanced Vegetation Index (EVI)
```markdown
Huete, A., et al. "Overview of the Radiometric and Biophysical Performance of the MODIS Vegetation Indices." Remote Sensing of Environment 83 (2002):195–213
```
* Global Environmental Monitoring Index (GEMI)
```markdown
Pinty, B., and M. Verstraete. GEMI: a Non-Linear Index to Monitor Global Vegetation From Satellites. Vegetation 101 (1992): 15-20
```
* Green Atmospherically Resistant Index (GARI)
```markdown
Gitelson, A., Y. Kaufman, and M. Merzylak. "Use of a Green Channel in Remote Sensing of Global Vegetation from EOS-MODIS." Remote Sensing of Environment 58 (1996): 289-298
```
* Green Chlorophyll Index (GCI)
```markdown
Gitelson, A., Y. Gritz, and M. Merzlyak. "Relationships Between Leaf Chlorophyll Content and Spectral Reflectance and Algorithms for Non-Destructive Chlorophyll Assessment in Higher Plant Leaves." Journal of Plant Physiology 160 (2003): 271-282
```
* Green Difference Vegetation Index (GDVI)
```markdown
Sripada, R., et al. "Determining In-Season Nitrogen Requirements for Corn Using Aerial Color-Infrared Photography." Ph.D. dissertation, North Carolina State University, 2005
```
* Green Leaf Index (GLI)
```markdown
Louhaichi, M., M. Borman, and D. Johnson. "Spatially Located Platform and Aerial Photography for Documentation of Grazing Impacts on Wheat." Geocarto International 16, No. 1 (2001): 65-70
```
* Green Normalized Difference Vegetation Index (GNDVI)
```markdown
Gitelson, A., and M. Merzlyak. "Remote Sensing of Chlorophyll Concentration in Higher Plant Leaves." Advances in Space Research 22 (1998): 689-692
```
* Green Optimized Soil Adjusted Vegetation Index (GOSAVI)
```markdown
Sripada, R., et al. "Determining In-Season Nitrogen Requirements for Corn Using Aerial Color-Infrared Photography." Ph.D. dissertation, North Carolina State University, 2005
```
* Green Ratio Vegetation Index (GRVI)
```markdown
Sripada, R., et al. "Aerial Color Infrared Photography for Determining Early In-season Nitrogen Requirements in Corn." Agronomy Journal 98 (2006): 968-977
```
* Green Soil Adjusted Vegetation Index (GSAVI)
```markdown
Sripada, R., et al. "Determining In-Season Nitrogen Requirements for Corn Using Aerial Color-Infrared Photography." Ph.D. dissertation, North Carolina State University, 2005
```
* Infrared Percentage Vegetation Index (IPVI)
```markdown
Crippen, R. "Calculating the Vegetation Index Faster." Remote Sensing of Environment 34 (1990): 71-73.
```
* Leaf Area Index (LAI)
```markdown
Boegh, E., H. Soegaard, N. Broge, C. Hasager, N. Jensen, K. Schelde, and A. Thomsen. "Airborne Multi-spectral Data for Quantifying Leaf Area Index, Nitrogen Concentration and Photosynthetic Efficiency in Agriculture." Remote Sensing of Environment 81, no. 2-3 (2002): 179-193
```
* Modified Non-Linear Index (MNLI)
```markdown
Yang, Z., P. Willis, and R. Mueller. "Impact of Band-Ratio Enhanced AWIFS Image to Crop Classification Accuracy." Proceedings of the Pecora 17 Remote Sensing Symposium (2008), Denver, CO
```
* Modified Simple Ratio (MSR)
```markdown
Chen, J. "Evaluation of Vegetation Indices and Modified Simple Ratio for Boreal Applications." Canadian Journal of Remote Sensing 22 (1996): 229-242
```
* Modified Soil Adjusted Vegetation Index 2 (MSAVI2)
```markdown
Qi J., Kerr Y., Chehbouni A., 1994. External factor consideration in vegetation index development. Proc. of Physical Measurements and Signatures in Remote Sensing, ISPRS, 723-730.
```
* Non-Linear Index (NLI)
```markdown
Goel, N., and W. Qin. "Influences of Canopy Architecture on Relationships Between Various Vegetation Indices and LAI and Fpar: A Computer Simulation." Remote Sensing Reviews 10 (1994): 309-347
```
* Normalized Difference Vegetation Index (NDVI)
```markdown
Rouse, J., R. Haas, J. Schell, and D. Deering. Monitoring Vegetation Systems in the Great Plains with ERTS. Third ERTS Symposium, NASA (1973): 309-317
```
* Optimized Soil Adjusted Vegetation Index (OSAVI)
```markdown
Rondeaux, G., M. Steven, and F. Baret. "Optimization of Soil-Adjusted Vegetation Indices." Remote Sensing of Environment 55 (1996): 95-107
```
* Renormalized Difference Vegetation Index (RDVI)
```markdown
Roujean, J., and F. Breon. "Estimating PAR Absorbed by Vegetation from Bidirectional Reflectance Measurements." Remote Sensing of Environment 51 (1995): 375-384
```
* Soil Adjusted Vegetation Index (SAVI)
```markdown
Huete, A. "A Soil-Adjusted Vegetation Index (SAVI)." Remote Sensing of Environment 25 (1988): 295-309
```
* Simple Ratio 650 (SR650)
```markdown
Birth, G., and G. McVey. "Measuring the Color of Growing Turf with a Reflectance Spectrophotometer." Agronomy Journal 60 (1968): 640-643
```
* Sum Green Index (SGI)
```markdown
Lobell, D., and G. Asner. "Hyperion Studies of Crop Stress in Mexico." Proceedings of the 12th Annual JPL Airborne Earth Science Workshop, Pasadena, CA (2003)
```
* Transformed Difference Vegetation Index (TDVI)
```markdown
Bannari, A., H. Asalhi, and P. Teillet. "Transformed Difference Vegetation Index (TDVI) for Vegetation Cover Mapping" In Proceedings of the Geoscience and Remote Sensing Symposium, IGARSS '02, IEEE International, Volume 5 (2002)
```
* Triangular Greenness Index (TGI)
```markdown
Hunt, E., C. Daughtry, J. Eitel, and D. Long. "Remote Sensing Leaf Chlorophyll Content Using a Visible Band Index." Agronomy Journal 103, No. 4 (2011): 1090-1099
```
* Visible Atmospherically Resistant Index (VARI)
```markdown
Gitelson, A., et al. "Vegetation and Soil Lines in Visible Spectral Space: A Concept and Technique for Remote Estimation of Vegetation Fraction. International Journal of Remote Sensing 23 (2002): 2537−2562
```
* Wide Dynamic Range Vegetation Index (WDRVI)
```markdown
Gitelson, A. "Wide Dynamic Range Vegetation Index for Remote Quantification of Biophysical Characteristics of Vegetation." Journal of Plant Physiology 161, No. 2 (2004): 165-173.
Henebry, G., A. Viña, and A. Gitelson. "The Wide Dynamic Range Vegetation Index and its Potential Utility for Gap Analysis." Gap Analysis Bulletin 12: 50-56
```
* WorldView Improved Vegetation Index (WV-VI)
```markdown
Wolf, A. Using WorldView 2 Vis-NIR MSI Imagery to Support Land Mapping and Feature Extraction Using Normalized Difference Index Ratios. Unpublished report, Longmont, CO: DigitalGlobe (2010)
```
* Atmospherically Resistant Vegetation Index (ARVI)
```markdown
Kaufman, Y., and D. Tanre. "Atmospherically Resistant Vegetation Index (ARVI) for EOS-MODIS. IEEE Transactions on Geoscience and Remote Sensing 30, no. 2 (1992): 261-270
```
* Modified Chlorophyll Absorption Ratio Index (MCARI)
```markdown
Daughtry, C., et al. "Estimating Corn Leaf Chlorophyll Concentration from Leaf and Canopy Re?ectance." Remote Sensing Environment 74 (2000): 229–239
```
* Modified Chlorophyll Absorption Ratio Index - Improved (MCARI2)
```markdown
Haboudane, D., et al. "Hyperspectral Vegetation Indices and Novel Algorithms for Predicting Green LAI of Crop Canopies: Modeling and Validation in the Context of Precision Agriculture." Remote Sensing of Environment 90 (2004): 337-352
```
* Modified Red Edge Normalized Difference Vegetation Index (MRENDVI)
```markdown
Datt, B. "A New Reflectance Index for Remote Sensing of Chlorophyll Content in Higher Plants: Tests Using Eucalyptus Leaves." Journal of Plant Physiology 154 (1999): 30-36.
Sims, D. and J. Gamon. "Relationships Between Leaf Pigment Content and Spectral Reflectance Across a Wide Range of Species, Leaf Structures and Developmental Stages." Remote Sensing of Environment 81 (2002): 337-354
```
* Modified Red Edge Simple Ratio (MRESR)
```markdown
Sims, D., and J. Gamon. "Relationships Between Leaf Pigment Content and Spectral Reflectance Across a Wide Range of Species, Leaf Structures and Developmental Stages." Remote Sensing of Environment 81 (2002):337-354.
Datt, B. "A New Reflectance Index for Remote Sensing of Chlorophyll Content in Higher Plants: Tests Using Eucalyptus Leaves." Journal of Plant Physiology 154 (1999):30-36
```
* Modified Triangular Vegetation Index (MTVI)
```markdown
Haboudane, D., et al. "Hyperspectral Vegetation Indices and Novel Algorithms for Predicting Green LAI of Crop Canopies: Modeling and Validation in the Context of Precision Agriculture." Remote Sensing of Environment 90 (2004): 337-352
```
* Modified Triangular Vegetation Index - Improved (MTVI2)
```markdown
Haboudane, D., et al. "Hyperspectral Vegetation Indices and Novel Algorithms for Predicting Green LAI of Crop Canopies: Modeling and Validation in the Context of Precision Agriculture." Remote Sensing of Environment 90 (2004): 337-352
```
* Red Edge Normalized Difference Vegetation Index (RENDVI)
```markdown
Gitelson, A., and M. Merzlyak. "Spectral Reflectance Changes Associated with Autumn Senescence of Aesculus Hippocastanum L. and Acer Platanoides L. Leaves." Journal of Plant Physiology 143 (1994): 286?292.
Sims, D., and J. Gamon. "Relationships Between Leaf Pigment Content and Spectral Reflectance Across a Wide Range of Species, Leaf Structures and Developmental Stages." Remote Sensing of Environment 81 (2002): 337-354
```
* Transformed Chlorophyll Absorption Reflectance Index (TCARI)
```markdown
Haboudane, D., et al. "Hyperspectral Vegetation Indices and Novel Algorithms for Predicting Green LAI of Crop Canopies: Modeling and Validation in the Context of Precision Agriculture." Remote Sensing of Environment 90 (2004): 337-352
```
* Triangular Vegetation Index (TVI)
```markdown
Broge, N., and E. Leblanc. "Comparing Prediction Power and Stability of Broadband and Hyperspectral Vegetation Indices for Estimation of Green Leaf Area and Canopy Chlorophyll Density." Remote Sensing of Environment 76 (2000): 156-172
```
* Vogelmann Red Edge Index 1 (VREI1)
```markdown
Vogelmann, J., B. Rock, and D. Moss. "Red Edge Spectral Measurements from Sugar Maple Leaves." International Journal of Remote Sensing 14 (1993): 1563-1575
```
* Vogelmann Red Edge Index 2 (VREI2)
```markdown
Vogelmann, J., B. Rock, and D. Moss. "Red Edge Spectral Measurements from Sugar Maple Leaves." International Journal of Remote Sensing 14 (1993): 1563-1575
```
* Simple Ratio 680 (SR680)
```markdown
Sims, D.A., Gamon, J.A. (2002) Relationships between leaf pigment content and spectral reflectance across a wide range of species, leaf structures and developmental stages. Remote Sensing of Environment 81: 337–354
```
* Simple Ratio 705 (SR705)
```markdown
Sims, D.A., Gamon, J.A. (2002) Relationships between leaf pigment content and spectral reflectance across a wide range of species, leaf structures and developmental stages. Remote Sensing of Environment 81: 337–354
```
* Normalized Difference 680 (ND680)
```markdown
Sims, D.A., Gamon, J.A. (2002) Relationships between leaf pigment content and spectral reflectance across a wide range of species, leaf structures and developmental stages. Remote Sensing of Environment 81: 337–354
```
* Normalized Difference 705 (ND705)
```markdown
Sims, D.A., Gamon, J.A. (2002) Relationships between leaf pigment content and spectral reflectance across a wide range of species, leaf structures and developmental stages. Remote Sensing of Environment 81: 337–354
```
* Modified Simple Ratio 705 (mSR705)
```markdown
Sims, D.A., Gamon, J.A. (2002) Relationships between leaf pigment content and spectral reflectance across a wide range of species, leaf structures and developmental stages. Remote Sensing of Environment 81: 337–354
```
* Modified Normalized Difference 705 (mND705)
```markdown
Sims, D.A., Gamon, J.A. (2002) Relationships between leaf pigment content and spectral reflectance across a wide range of species, leaf structures and developmental stages. Remote Sensing of Environment 81: 337–354
```
* Plant Senescence Reflectance Index (PSRI)
```markdown
Merzlyak, J., et al. "Non-destructive Optical Detection of Pigment Changes During Leaf Senescence and Fruit Ripening." Physiologia Plantarum 106 (1999): 135-141
```
* Water Band Index (WBI)
```markdown
Penuelas, J., et al. "The Reflectance at the 950-970 Region as an Indicator of Plant Water Status." International Journal of Remote Sensing 14 (1993): 1887-1905.
Champagne, C., et al. "Mapping Crop Water Status: Issues of Scale in the Detection of Crop Water Stress Using Hyperspectral Indices." Proceedings of the 8th International Symposium on Physical Measurements and Signatures in Remote Sensing, Aussois, France (2001): 79-84
```
* Anthocyanin Reflectance Index 1 (ARI1)
```markdown
Gitelson, A., M. Merzlyak, and O. Chivkunova. "Optical Properties and Nondestructive Estimation of Anthocyanin Content in Plant Leaves." Photochemistry and Photobiology 71 (2001): 38-45
```
* Anthocyanin Reflectance Index 2 (ARI2)
```markdown
Gitelson, A., M. Merzlyak, and O. Chivkunova. "Optical Properties and Nondestructive Estimation of Anthocyanin Content in Plant Leaves." Photochemistry and Photobiology 71 (2001): 38-45
```
* Carotenoid Reflectance Index 1 (CRI1)
```markdown
Gitelson, A., et al. "Assessing Carotenoid Content in Plant Leaves with Reflectance Spectroscopy." Photochemistry and Photobiology 75 (2002): 272-281
```
* Carotenoid Reflectance Index 2 (CRI2)
```markdown
Gitelson, A., et al. "Assessing Carotenoid Content in Plant Leaves with Reflectance Spectroscopy." Photochemistry and Photobiology 75 (2002): 272-281
```
* Photochemical Reflectance Index (PRI)
```markdown
Sims, D.A., Gamon, J.A. (2002) Relationships between leaf pigment content and spectral reflectance across a wide range of species, leaf structures and developmental stages. Remote Sensing of Environment 81: 337–354
```
* Structure-Insensitive Pigment Index (SIPI)
```markdown
Sims, D.A., Gamon, J.A. (2002) Relationships between leaf pigment content and spectral reflectance across a wide range of species, leaf structures and developmental stages. Remote Sensing of Environment 81: 337–354
```
* Red Green Ratio Index (RGRI)
```markdown
Gamon, J., and J. Surfus. "Assessing Leaf Pigment Content and Activity With a Reflectometer." New Phytologist 143 (1999): 105-117
```
* Burn Area Index (BAI)
```markdown
Chuvieco, E., M. Pilar Martin, and A. Palacios. “Assessment of Different Spectral Indices in the Red-Near-Infrared Spectral Domain for Burned Land Discrimination.” Remote Sensing of Environment 112 (2002): 2381-2396.
Martín, M. Cartografía e inventario de incendios forestales en la Península Iberica a partir de imágenes NOAA AVHRR. Doctoral thesis, Universidad de Alcalá, Alcalá de Henares (1998).
```
* Iron Oxide Ratio (IOR)
```markdown
Segal, D. "Theoretical Basis for Differentiation of Ferric-Iron Bearing Minerals, Using Landsat MSS Data." Proceedings of Symposium for Remote Sensing of Environment, 2nd Thematic Conference on Remote Sensing for Exploratory Geology, Fort Worth, TX (1982): pp. 949-951.
Drury, S. Image Interpretation in Geology. London: Allen and Unwin (1987), 243 pp.
```
* WorldView New Iron Index (WV-II)
```markdown
Wolf, A. Using WorldView 2 Vis-NIR MSI Imagery to Support Land Mapping and Feature Extraction Using Normalized Difference Index Ratios. Unpublished report, Longmont, CO: DigitalGlobe (2010)
```
* WorldView Soil Index (WV-SI)
```markdown
Wolf, A. Using WorldView 2 Vis-NIR MSI Imagery to Support Land Mapping and Feature Extraction Using Normalized Difference Index Ratios. Unpublished report, Longmont, CO: DigitalGlobe (2010)
```
* Normalized Difference Water Index (NDWI)
```markdown
McFeeters, S. "The use of Normalized Difference Water Index (NDWI) in the Delineation of Open Water Features." International Journal of Remote Sensing 17 (1996): 1425-1432
```
* Normalized Difference Mud Index (NDMI)
```markdown
Bernstein, L. S., X. Jin, B. Gregor, and S. Adler-Golden. "Quick Atmospheric Correction Code: Algorithm Description and Recent Upgrades." Optical Engineering 51, No. 11 (2012): 111719-1 to 111719-11
```
* WorldView Built-Up Index (WV-BI)
* WorldView Non-Homogeneous Feature Difference (WV-NHFD)
```markdown
Wolf, A. Using WorldView 2 Vis-NIR MSI Imagery to Support Land Mapping and Feature Extraction Using Normalized Difference Index Ratios. Unpublished report, Longmont, CO: DigitalGlobe (2010).
```
* WorldView Water Index (WV-WI)
```markdown
Wolf, A. Using WorldView 2 Vis-NIR MSI Imagery to Support Land Mapping and Feature Extraction Using Normalized Difference Index Ratios. Unpublished report, Longmont, CO: DigitalGlobe (2010).
```

## SWIR 1000-2500nm
* Normalized Difference Nitrogen Index (NDNI)
```markdown
Serrano, L., J. Penuelas, and S. Ustin. "Remote Sensing of Nitrogen and Lignin in Mediterranean Vegetation from AVIRIS Data: Decomposing Biochemical from Structural Signals." Remote Sensing of Environment 81 (2002):355-364.
Fourty, T., et al. "Leaf Optical Properties with Explicit Description of Its Biochemical Composition: Direct and Inverse Problems." Remote Sensing of Environment 56 (1996):104-117.
```
* Cellulose Absorption Index (CAI)
```markdown
Daughtry, C. "Discriminating Crop Residues from Soil by Short-Wave Infrared Reflectance." Agronomy Journal 93 (2001): 125-131.
Daughtry, C., E. Hunt Jr., and J. McMurtrey III. "Assessing Crop Residue Cover Using Shortwave Infrared Reflectance." Remote Sensing of Environment 90 (2004): 126-134.
```
* Lignin Cellulose Absorption Index (LCAI)
```markdown
Daughtry, C., E. Hunt, Jr., P. Doraiswamy, and J. McMurtrey III. "Remote Sensing the Spatial Distribution of Crop Residues." Agronomy Journal 97 (2005): 864-871.
```
* Normalized Difference Lignin Index (NDLI)
```markdown
Serrano, L., J. Penuelas, and S. Ustin. "Remote Sensing of Nitrogen and Lignin in Mediterranean Vegetation from AVIRIS Data: Decomposing Biochemical from Structural Signals." Remote Sensing of Environment 81 (2002): 355-364.
Fourty, T., et al. "Leaf Optical Properties with Explicit Description of Its Biochemical Composition: Direct and Inverse Problems." Remote Sensing of Environment 56 (1996): 104-117.
Melillo, J., J. Aber, and J. Muratore. "Nitrogen and Lignin Control of Hardwood Leaf Litter Decomposition Dynamics." Ecology 63 (1982): 621-626.
```
* Clay Ratio (CR)
```markdown
Drury, S. Image Interpretation in Geology. London: Allen and Unwin (1987), 243 pp
```
* Sand moisture index (SMI)
* SWIR Fine particles Index (FI)