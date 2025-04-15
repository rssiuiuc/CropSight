# [CropSight: towards a large-scale operational framework for object-based crop type ground truth retrieval using street view and PlanetScope satellite imagery](https://www.sciencedirect.com/science/article/pii/S0924271624002922)

## Introduction

Collecting accurate ground truth data of crop types is a crucial challenge for agricultural research and development. The CropSight Framework is an open-source toolkit designed to automate the retrieval of object-based crop type information from massive Google Street View (GSV) images. With its scalable and efficient features, CropSight enables the automatic identification of GSV images and boundary delineation to generate in-situ object-based crop-type labels over large areas.

### Key Components
- **Large-Scale Operational Cropland Field-View Imagery Collection Method**: Systematically acquires representative geotagged cropland field-view images.
- **Uncertainty-Aware Crop Type Image Classification Model (UncertainFusionNet)**: Retrieves high-quality crop type labels with quantified uncertainty.
- **Cropland Boundary Delineation Model (SAM)**: Delineates cropland boundaries using PlanetScope satellite imagery.

## Workflow

<p align="center">
  <img src="src/CropSight Flowchart Fig2.png" width="900">
  <br>
  <b> Figure 1: CropSight Flowchart. </b>
</p>

## Dataset 
- ### UncertainFusionNet  
<p align="center">
<img src="src/CropGSV dataset.png" width="700" >
<br>
<b> Figure 2: Crop type ground-level view dataset (CropGSV) used to train UncertainFusionNet. </b>
</p>

- ### SAM
<p align="center">
<img src="src/CropBoundary.png" width="700" >
<br>
<b> Figure 3: Cropland boundary ground-truth dataset (CropBoundary) used to fine-tune SAM. </b>
</p>

## Application 

Using the CropSight framework, we collected crop type ground truth data from Google Street View and PlanetScope satellite imagery. Below are examples of the application of CropSight in the US and Brazil.

- ### Example 1: Brazil

<p align="center">
  <img src="src/Brazil_Map_S4.png" width="800">
  <br>
  <b>Figure 4: Object-based crop type ground truth map produced by CropSight using the latest images (2023) in Brazil. Crop type labels are overlaid on Google Earth imagery. The accuracy of crop type classification and boundary delineation is assessed by randomly sampling and comparing against visually interpreted GSV-based ground truth data.</b>
</p>

- ### Example 2: United States

<p align="center">
  <img src="src/Fig18.png" width="800">
  <br>
  <b>Figure 5: Object-based crop type ground truth maps produced by CropSight using the latest images (2023). These maps represent four distinct study areas in the United States (A-D). (a) Overlay of crop type labels on Google Maps. (b) Overlay of crop type labels on off-season PlanetScope images.</b>
</p>


## Example of Retrieving One Ground Truth

To see an example of how to retrieve one ground truth using the CropSight framework, refer to the [CropSight.ipynb](https://colab.research.google.com/drive/1yoTC0MrmTVOrDZNF7A7rNcK-XbthJ1Ub?usp=drive_link).

## CropSight-US: A National-Scale Object-based Crop Type Ground Truth Dataset

CropSight-US is an annual, object-based crop type ground truth dataset covering the contiguous United States (CONUS) from 2013 to 2023. Based on the CropSight workflow (Liu et al., 2024), it expands sample generation from specific sites to nationwide coverage, labeling 17 distinct crop types. The dataset integrates Google Street View imagery for crop type identification and Sentinel-2 imagery for field boundary delineation, addressing the challenge of large-scale ground truth data collection. To our knowledge, CropSight-US is the first nationwide, object-based crop type dataset derived from street view imagery, offering broad spatial and crop-type coverage.

CropSight-US is in its final stages of preparation and will be released soon as an open-source dataset.

<p align="center">
  <img src="src/CropSight-US-Flowchart.png" width="800">
  <br>
  <b>Figure 6: CropSight-US ground-truthing framework demonstrating the steps necessary to generate the CropSight-US products across CONUS for object-based crop type ground truth building on the CropSight by Liu et al. (2024).</b>
</p>

With the evaluated object-based crop type ground-truthing framework, we constructed an object-based field-level crop type ground truth dataset comprising 17 major crop type classes sampled from the GSV metadata pool we created. Each entry in the ground truth dataset includes the predicted crop type along with high or low confidence information from the CONUS-UncertainFusionNet model, the corresponding cropland boundary, and the year and month when the GSV image was captured. For each crop type, we first computed the average number of fields per ASD using the CSB dataset and assigned quantiles to each ASD based on field count. We then aggregated the available GSV metadata for each crop type within each ASD and calculated the average number of GSV metadata entries per ASD. Crop types contributing less than 2% of the total GSV metadata database were excluded from sampling. For each crop type, if an ASD contained fewer than or equal to the average number of GSV metadata entries, all available entries were used. For ASDs with above-average GSV metadata, additional samples were drawn based on their quantile ranking (Q1–Q4, with Q4 being the class with the highest number of GSV available). Specifically, the number of extra samples beyond the average was determined as 0.2, 0.4, 0.6, and 0.8 times the excess metadata count for ASDs in Q1, Q2, Q3, and Q4, respectively.

<p align="center">
  <img src="src/CropSight-US-Crop-Types.jpg" width="800">
  <br>
  <b>Figure 7: Samples of the reference dataset showcasing field-view images of 17 crop types included in CropSight-US.</b>
</p>


## Author
Yin Liu (yinl3@illinois.edu)

Zhijie Zhou (zhijiez2@illinois.edu)

Chunyuan Diao (chunyuan@illinois.edu)

[Remote Sensing Space-Time Innovation Lab](https://diaorssilab.web.illinois.edu/)

Department of Geography & GIScience, University of Illinois at Urbana-Champaign


## Acknowledgement
This project is supported by the National Science Foundation’s Office of Advanced Cyberinfrastructure under grant 2048068.

## Citation
If you use this work in any way, please mention this citation:
```markdown
@article
{Title: CropSight: towards a large-scale operational framework for object-based crop type ground truth retrieval using street view and PlanetScope satellite imagery,
 Authors: Liu, Yin and Diao, Chunyuan and Mei, Weiye and Zhang, Chishan,
 Publication: ISPRS Journal of Photogrammetry and Remote Sensing,
 Year: 2024,
 Volume:216
 Page: 66-89,
 DOI: 10.1016/j.isprsjprs.2024.07.025}
