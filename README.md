# Crop-type-information-retrieval-from-Google-Street-View-images
## About

The Crop Type Information Retrieval (CTIR) Framework is an open-source toolkit that helps to automatically retrieve field-level crop type information from massive Google Street View (GSV) images. This scalable framework enables the efficient collection of GSV images from the Google Maps Platform and the automatic identification of GSV images to generate in-situ crop-type labels over large areas. The CTIR framework supports the complete workflow of automatically retrieving ground truth labels of croplands, including GSV metadata collection, GSV panoramic image downloading and processing, and GSV image classification. This open-source toolkit aims to enhance agriculture development by collecting accurate ground truth data of crop types from open-source data sources. This data can be used by researchers and practitioners across multiple disciplines to develop effective solutions for agriculture-related problems. By using this toolkit, users can improve the accuracy of crop classification, yield estimation, and other agricultural applications.

## Workflow of CTIR
### 1. GSV metadata collection 
[Google colab](https://colab.research.google.com/drive/1WsbVxqH2A7FrLV7guVRx4HaEU6cwz2aJ#scrollTo=dxYrIqi1AmZG&line=1&uniqifier=1)

Function `collectGSV` has `panoids = streetview.panoids(lat=x, lon=y)` it.

```javascript
[{'panoid': 'E9DDnTQsKTcgpH9NHI6MaA', 'lat': 39.36998876974609, 'lon': -91.47946938753894, 'year': 2009, 'month': 3}, {'panoid': '17hKTtanmJahKVoRW2K25w', 'lat': 39.36997271381018, 'lon': -91.47946938753894, 'year': 2021, 'month': 12}, {'panoid': '3Tm5g6lPAjClKQEdQIqc5g', 'lat': 39.36984071070807, 'lon': -91.47946909232498}, {'panoid': 'brlitF-PRFlM4mK_VYbHFg', 'lat': 39.3701044774849, 'lon': -91.47946983035992}, {'panoid': 'piNgln2_TUk-iKbqTzNkzA', 'lat': 39.36957715579746, 'lon': -91.47947027318088}, {'panoid': 'KWthHUJiJvfeCRwLSqQaAA', 'lat': 39.36970869798013, 'lon': -91.47946953514592}, {'panoid': 'ASq1hW2FU34tsX8dsr5pYw', 'lat': 39.37023608736976, 'lon': -91.4794699041634}, {'panoid': 'eOPsj4WZYJABlikxXgazUQ', 'lat': 39.37036659341757, 'lon': -91.47946968275292}]
```

<p align="center">
  <img src="src/GSV_metadata.jpg" width="450">
  <br>
  <b>The avaiable GSV metadata.</b>
</p>

### 2. GSV roadside images preparation

#### 2.1 GSV panoramic image downloading
With the `panoid` of collected GSV metadata, the corresponding GSV panoramic images can be downloaded from Google Maps Platform through function `downloadGSV`. The orientation that the vehicle headed when collecting the GSV panoramic images is also retrived through `downloadGSV`. For example,  one GSV image is avaiable at location of (41.54170024691091,-88.29999867944885), and the vehicle was heading to 271° when collecting this GSV panoramic image. The north rotation is 271°.
<p align="center">
  <img src="src/QDWxWb7c1sVcLeoquYPTHw_41.54170024691091_-88.29999867944885_2021_8_358.7471008300781_pano.jpg" width="450">
  <br>
  <b>The avaiable GSV metadata.</b>
</p>

#### 2.2 GSV panoramic image clipping
The two roadsides street view images are retrived from the original GSV panoramic images using an function `NFOV`. This function supports the extraction of a normal field of view from a panoramic image, centered on any point you choose. The implementation is highly optimized for speed and efficiency, computing every pixel projection mapping at once. It uses bilinear interpolation to create smoother images, resulting in a more realistic and immersive viewing experience.

<p align="center">
  <img src="src/Panoramic clipping.gif" width="1000"  loopcount="1">
  <br>
  <b>The avaiable GSV metadata.</b>
</p>

### 3. GSV image classification

#### 3.1 Training and test dataset preparation
More than millisions GSV images are collected once year, which includes various scenes, building, house, trees, etc. In order to collect the representative GSV images of crop species from massive GSV images, the GSV images are roughly labelled with the auxiliary **Cropland data layer (CDL)** and selcted with **a sampling stratege**. CDL is a raster, geospatial dataset created by the United States Department of Agriculture (USDA) that provides information about the type of crops grown on agricultural lands in the United States. The CDL is produced annually and provides data for every state in the US. The CDL is based on satellite imagery and other remote sensing data and uses a supervised classification algorithm to identify the crop type on each pixel of the image. The crop types identified in the CDL include grains, oilseeds, cotton, fruits, vegetables, and hay. With the specific location 

. The view of GSV images is analysed Cropland data layer (CDL).
the GSV images is selected based on the percentage of crop species that each GSV corresponds to. It is calculated using Cropland data layer (CDL). According to the orientation information and CDL, the 


#### 3.2 Model (ViTResFusionNet) training 
[Google colab](https://colab.research.google.com/drive/1WsbVxqH2A7FrLV7guVRx4HaEU6cwz2aJ#scrollTo=2y4QtgcoA9De&line=1&uniqifier=1)



#### 3.3 Generate automatic labels for agricultural 

#
This repo contains code to automatically generate labels for agricultural parcels given Google Street View i
mages and aerial imagery at a resolution of 1-meter (National Agriculture Imagery Program (NAIP)). This code has been used ot generate crop type labels for U.S.

## Acknowledgement
This project is supported by the National Science Foundation’s Office of Advanced Cyberinfrastructure under grant 1849821





