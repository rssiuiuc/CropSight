# CropSight: towards a large-scale operational framework for object-based crop type ground truth retrieval using street view and PlanetScope satellite imagery

![Project Status](https://img.shields.io/badge/status-work%20in%20progress-yellow)

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
  <b>CropSight Flowchart</b>
</p>

## Dataset 
### UncertainFusionNet
Millions of GSV images are collected annually, capturing a wide range of scenes including buildings, houses, trees, and more. To collect representative GSV images of crop species from this massive dataset, the collected images are roughly labeled with the aid of the `Cropland Data Layer (CDL)` and then selected using a proposed `sampling` strategy. The CDL-generated labels for each GSV image may contain errors due to misclassifications. To address these issues, each image undergoes visual interpretation and is further labeled accordingly. Images containing other items or with crops that are difficult to distinguish are labeled as "others." The following shows the final processed dataset of dominant crop species for the southern region of the United States.
 
<p align="center">
<img src="src/CropGSV dataset.png" width="850" >
<br>
<b>Crop type ground-level view dataset (CropGSV). </b>
</p>


### Segmentation Anything Model (SAM)
With the crop type labels retrieved from the geotagged cropland field-view images, SAM is employed and fine-tuned to delineate the cropland boundaries associated with these crop type images. SAM is a highly effective state-of-the-art model designed to segment an object of interest in an image given certain prompts provided by a user (Kirillov et al., 2023). SAM diverges from traditional segmentation models by introducing a pioneering promptable segmentation strategy. Utilizing satellite imagery as the primary input and coordinates derived from geotagged field-view images as point prompts, SAM model emerges as an optimally tailored solution for extracting the cropland boundary corresponding to each field-view image in CropSight.
 
 <p align="center">
<img src="src/CropBoundary.png" width="850" >
<br>
<b>Cropland boundary ground-truth dataset (CropBoundary). </b>
</p>

### Application 
With CropSight, we collected some crop type ground truth using Google Street View and PlanetScope satellite imagery. The following examples shows Application of CropSight in US and Brazil.
<p align="center">
  <img src="src/Brazil_Map_S4.png" width="850" >
  <br>
  <b>Map of object-based crop type ground truth produced by CropSight using latest images (2023) in Brazil. Crop type labels are overlaid on Google Earth imagery. The accuracy of crop type classification and boundary delineation is assessed by randomly sampling and comparing against visually interpreted GSV-based ground truth data. </b>
</p>


<p align="center">
  <img src="src/Fig18.png" width="850" >
  <br>
  <b>Maps of object-based crop type ground truth produced by CropSight using latest images (2023). These maps represent four distinct study areas, each situated in one of our four study areas A-D. (a) displays the overlay of crop type labels on Google Maps. (b) displays the overlay of crop type labels on off-season PlanetScope images. </b>
</p>




## Author
Yin Liu (yinl3@illinois.edu)

Chunyuan Diao (chunyuan@illinois.edu)

[Remote Sensing Space-Time Innovation Lab](https://diaorssilab.web.illinois.edu/)

Department of Geography & GIScience, University of Illinois at Urbana-Champaign


## Acknowledgement
This project is supported by the National Science Foundation’s Office of Advanced Cyberinfrastructure under grant 2048068.

## Citation
If you use this work in any way, please mention this citation:
```markdown
@article
{Title: Using a semantic edge-aware multi-task neural network to delineate agricultural parcels from remote sensing images,
 Authors: Liu, Yin and Diao, Chunyuan and Mei, Weiye and Zhang, Chishan,
 Publication: ISPRS Journal of Photogrammetry and Remote Sensing,
 Year: 2024,
 Volume:216
 Page: 66-89,
 DOI: 10.1016/j.isprsjprs.2024.07.025}
