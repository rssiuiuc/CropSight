# Crop-type-information-retriveal-from-Google-Street-View-images

This repo contains code to automatically generate labels for agricultural parcels given Google Street View images and aerial imagery at a resolution of 1-meter (National Agriculture Imagery Program (NAIP)). This code has been used ot generate crop type labels for U.S.

## GSV metadata collection 
[Google colab](https://colab.research.google.com/drive/1WsbVxqH2A7FrLV7guVRx4HaEU6cwz2aJ#scrollTo=dxYrIqi1AmZG&line=1&uniqifier=1)

Function `downloadGSV` has `panoids = streetview.panoids(lat=x, lon=y)` it.

```javascript
[{'panoid': 'E9DDnTQsKTcgpH9NHI6MaA', 'lat': 39.36998876974609, 'lon': -91.47946938753894, 'year': 2009, 'month': 3}, {'panoid': '17hKTtanmJahKVoRW2K25w', 'lat': 39.36997271381018, 'lon': -91.47946938753894, 'year': 2021, 'month': 12}, {'panoid': '3Tm5g6lPAjClKQEdQIqc5g', 'lat': 39.36984071070807, 'lon': -91.47946909232498}, {'panoid': 'brlitF-PRFlM4mK_VYbHFg', 'lat': 39.3701044774849, 'lon': -91.47946983035992}, {'panoid': 'piNgln2_TUk-iKbqTzNkzA', 'lat': 39.36957715579746, 'lon': -91.47947027318088}, {'panoid': 'KWthHUJiJvfeCRwLSqQaAA', 'lat': 39.36970869798013, 'lon': -91.47946953514592}, {'panoid': 'ASq1hW2FU34tsX8dsr5pYw', 'lat': 39.37023608736976, 'lon': -91.4794699041634}, {'panoid': 'eOPsj4WZYJABlikxXgazUQ', 'lat': 39.37036659341757, 'lon': -91.47946968275292}]
```

<p align="center">
  <img src="src/GSV_metadata.jpg" width="450">
  <br>
  <b>The avaiable GSV metadata.</b>
</p>

## GSV metadata proprecessing
In order to collect the representative crop species GSV images, the view of GSV images is analysed 

the percentage of crop species that each GSV corresponds to is calculated using Cropland data layer (CDL). According to the orientation information and CDL, the 


## retrive Google Street View panoramic images from Google Maps Websites, 
[Google colab](https://colab.research.google.com/drive/1WsbVxqH2A7FrLV7guVRx4HaEU6cwz2aJ#scrollTo=2y4QtgcoA9De&line=1&uniqifier=1)

## Clip GSV panoramic images, 

## Generate automatic labels for agricultural 
