<h1 align="center"> Google Summer of Code 2022</h1>
<p align="center"><i>with</i> </p>
<h2 align="center"><a href="https://summerofcode.withgoogle.com/organizations/4724093699489792/">Cuneiform Digital Library Initiative (CDLI)</a></h2>

<h2 align="center"><img src=https://user-images.githubusercontent.com/74586135/193470025-ad213327-a1ca-4f85-9df5-4a5692ee6d6f.png /> </h2>


<h2 align="center"><i>Project Report on "<a href="https://summerofcode.withgoogle.com/proposals/details/4DK6p7UC">Seal Portal</a>" </i> </h2>

## About the project

The seals portal aims at displaying all of the resources in the CDLI concerning a seal, aggregated in one place, with important features like viewing image annotations and graphical representation of seals chemistry. 

<i>Proposal</i> : [Seal Portal](https://docs.google.com/document/d/1xEGPcdK9PDpQEgvwRCurv4YYFGQaSwJxwf5r62MpTUA/edit?usp=sharing)\
<i>Contributions to CDLI</i> : [Merge Requests](https://gitlab.com/cdli/framework/-/merge_requests?scope=all&state=merged&author_username=aditiansingh)\
<i>Weekly Blogs</i> : [Blog](https://cdli-gh.github.io/blog/gsoc22/SealsPortal/index)

Mentor : [Jacob Dahl](https://www.orinst.ox.ac.uk/people/jacob-l-dahl) and [Timo Homburg](https://github.com/situx)

### Objectives and Deliverables
Completed tasks -> :heavy_check_mark: <br> Ongoing task -> :white_check_mark:

| \# | Objectives                    | Associated Deliverables         | Additional deliverables | issue(s) | Pull Requests |    Status | 
| --- | ----------------------------- | -------------------------------------------- | -------- |-------| -------- | ---- |
| 1 |  Implement required changes to the database and edit the model files accordingly| Setting up the image_annotations table <br>- Creating respective model files <br>- Bulk update of image_annotations table | |[#1336](https://gitlab.com/cdli/framework/-/issues/1136) | [!649](https://gitlab.com/cdli/framework/-/merge_requests/649) |:heavy_check_mark:|
| 2 | The seals portal | - Displaying Best Attested Composite seals with image and description.<br>- Create a table and respective model files for best_attested_seals <br>- Tabular representation of seals, categorized by period.<br>- Displaying and grouping seals categories: Physical Seals, Composite Seals, Sealings, All CDLI seals| - Creating Well Attested seals add and edit forms |[#700](https://gitlab.com/cdli/framework/-/issues/700)<br> [#1227](https://gitlab.com/cdli/framework/-/issues/1227)<br>[#1241](https://gitlab.com/cdli/framework/-/issues/1241)|[!661](https://gitlab.com/cdli/framework/-/merge_requests/661)<br>[!700](https://gitlab.com/cdli/framework/-/merge_requests/700)<br>[!737](https://gitlab.com/cdli/framework/-/merge_requests/737)|:heavy_check_mark: |
| 3 | Implementing seals single view | Implementation of a PHP library for graphical representation of chemical information of seals.<br>- A feature to view only top n elements (based on weight)<br>A switch to convert the graph into a table view. <br> - Graphical visualisation of element weight in that seal in the form of line chart and bar graph | -Creating add edit forms for seal chemistry.<br>-Creating add edit forms for seal chemistry standards. <br> - Export of chemical data as CSV | [#1332](https://gitlab.com/cdli/framework/-/issues/1132)<br>| [!687](https://gitlab.com/cdli/framework/-/merge_requests/687)<br>[!707](https://gitlab.com/cdli/framework/-/merge_requests/707) | :heavy_check_mark: |
| 4 | Adding image annotation viewer and integrating it with annotorious-open seadragon |Create the viewer page<br>- Generate tiles for deepzoom<br>- Integrate with annotorious-openseadragon||[#736](https://gitlab.com/cdli/framework/-/issues/736)<br>[#1288](https://gitlab.com/cdli/framework/-/issues/1288)| [Viewer page branch](https://gitlab.com/cdli/framework/-/tree/phoenix/feature/viewerpage) | :heavy_check_mark: |
| 5 | Implement a convertor from coco format to w3c.json format |To Study more about w3c.json and COCO image annotations format<br>- Comparing both coco and w3c.json annotation formats to create SVG points layout<br>- Writing a python script that takes in coco_format and gives w3c.json format<br>- Add the convertor to the docker container.|| [#1430](https://gitlab.com/cdli/framework/-/issues/1430) | [Standalone repository for conversion](https://github.com/cdli-gh/coco-convertor) <br/>[!743](https://gitlab.com/cdli/framework/-/merge_requests/743)  |:heavy_check_mark: |


### Additional Deliverables
These deliverables were implemented by Lars Willighagen and myself during the two week research visit to the Wolfson college, University of Oxford.

| \# | Objectives                    | Associated Deliverables         |  Pull Requests |    Status | 
| --- | ----------------------------- | -------------------------------------------- | -------- |-------|
| 1 |  Add credits for image annotations | On the reader page users can see who created, and who modified the annotations| [!740](https://gitlab.com/cdli/framework/-/merge_requests/740) | :heavy_check_mark: 
| 2 | Bulk upload for image annotations  | Users can upload a W3c.json file and it will be added to the database | [!741](https://gitlab.com/cdli/framework/-/merge_requests/741) <br> I have worked on the upload and confirm upload interface - [Branch link](https://gitlab.com/cdli/framework/-/tree/phoenix/feature/bulk-update-annotations) | :white_check_mark:|


## Preview of objectives

### 1. Seal Portal
  - *Final outcome:*
      - All Sources regarding CDLI seals have been aggregated at one place.
<center>

| Seal Portal |
| :---:	|
|<video src="https://user-images.githubusercontent.com/74586135/193475126-bc3c67fe-c7b2-4e69-b2f0-2ea0d90e6158.mp4" controls="controls">|
|  |

</center>

<center>

| Featured Seals Add forms |
| :---:	|
|<video src="https://user-images.githubusercontent.com/74586135/193475254-aadd6773-9290-4eac-bb55-325f282ac82e.mp4" controls="controls">|
|  |

</center>

<center>

| Featured Seals Edit forms |
| :---:	|
| <video src="https://user-images.githubusercontent.com/74586135/193475375-054b8139-feac-4351-ba52-e3ad63beea66.mp4" controls="controls"> |
|  |

</center>

### 2. Seal Single View
 - *Final outcome:*
    - Seal Chemistry Graphical and Tabular Visualizations for artifacts that are seals.
    - Export as CSV feature. 
<center>

| Seal Single View |
| :---:	|
| <video src="https://user-images.githubusercontent.com/74586135/193475341-ab1dd6e9-87d1-4501-a00c-c0a082141160.mp4" controls="controls"> |
| Seal single view for artifact with id 473511 |

</center>

### 3. Seal Chemistry Add forms

- *Final outcome:*
   - Users can add the chemical information about a seal by uploading a csv sheet and choosing a calibration file.
       - Users can also Export a chemistry file as CSV.
       - Admins can delete a particular Entry.
   - Users can also add a calibration file for standards of the instrument taking the chemical information.
       - This also includes credits information.

<center>

| Seal Chemistry Add form |
| :---:	|
| <video src="https://user-images.githubusercontent.com/74586135/193475320-a9d8311e-1a71-4e95-abe4-8a727d087428.mp4" controls="controls"> |
| Adding the seal chemistry using this sheet |
  
 
| Calibration Add form |
| :---:	|
| <video src="https://user-images.githubusercontent.com/74586135/193475304-69a02243-a9c9-40c5-999a-c2d3d12ae965.mp4" controls="controls"> |
| Adding the calibration using this sheet |

</center>

### 4. Artifact Viewer Page

- *Final outcome:*
   - Users can view zoomed version of an artifact image with annotated areas.
       - They can also view the credits for a particular annotation 
- *Methodology:*
   * This was achieved using the Annotorious and Openseadragon library.

<center>

| Artifact Viewer |
| :---:	|
| <video src=https://user-images.githubusercontent.com/74586135/193633826-a4a16a2c-e3ad-4c7d-9fcd-27956c05eb01.mp4 controls="controls">|
| Reader page for artifact Id |

</center>



## To Do (Post GSoC)

* Robust Testing of all newly added features.
* Addition of additional features.
* Documentation



## Acknowledgements
I would like to thank my mentors and reviewers Jacob Dahl, Emilie Page Perron, Lars Willighagen and Timo Homburg for clearing my doubts and supporting me throughout the journey. Participating in GSoC has enhanced my coding practices and has improved my analytical skills. I would definitely keep contributing to this amazing Organization!!

## Certificate
<img src="https://user-images.githubusercontent.com/74586135/212891704-9f76fe45-f3dd-4d4f-9b04-807295d2aae5.png" /> 


