<h1 align="center"> Google Summer of Code 2022</h1>
<p align="center"><i>with</i> </p>
<h2 align="center"><a href="https://summerofcode.withgoogle.com/organizations/4724093699489792/">Cuneiform Digital Library Initiative (CDLI)</a></h2>

<h2 align="center">![GSoC with CDLI](https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcRQLlztMEvCm115vczTLOX_KidDNblGQLP7Cg&usqp=CAU)</h2>

<h2 align="center"><i>Project Report on "<a href="https://summerofcode.withgoogle.com/proposals/details/4DK6p7UC">Seal Portal</a>" </i> </h2>

## About the project

The seals portal aims at displaying all of the resources in the CDLI concerning a seal, aggregated in one place, with important features like viewing image annotations and graphical representation of seals chemistry. 

<i>Proposal</i> : [Seal Portal](https://summerofcode.withgoogle.com/media/user/056513d8ee99/proposal/gAAAAABjN06fIkSbWCYO9tJezCTLCBd-0cXKhukG0saSM5HwVk_196XXfFvYBP6HLMcDhM6eua1z685QP73pm2QA-4sg8bAil80K0Lo7BYv-U5Irb_gwKVU=.pdf)\
<i>Contributions to CDLI</i> : [Merge Requests](https://gitlab.com/cdli/framework/-/merge_requests?scope=all&state=merged&author_username=aditiansingh)\
<i>Weekly Blogs</i> : [Blog](https://cdli-gh.github.io/blog/gsoc22/SealsPortal/index)

Mentor : [Jacob Dahl](https://www.orinst.ox.ac.uk/people/jacob-l-dahl) and [Timo Homburg](https://github.com/situx)

### Objectives and Deliverables

| \# | Objectives                    | Associated Deliverables         | Additional deliverables | issue(s) | Pull Requests |    Status | 
| --- | ----------------------------- | -------------------------------------------- | -------- |-------| -------- | ---- |
| 1 |  Implement required changes to the database and edit the model files accordingly| Setting up the image_annotations table <br>- Creating respective model files <br>- Bulk update of image_annotations table | |[#1336](https://gitlab.com/cdli/framework/-/issues/1136) | [!649](https://gitlab.com/cdli/framework/-/merge_requests/649) |:heavy_check_mark:|
| 2 | The seals portal | - Displaying Best Attested Composite seals with image and description.<br>- Create a table and respective model files for best_attested_seals <br>- Tabular representation of seals, categorized by period.<br>- Displaying and grouping seals categories: Physical Seals, Composite Seals, Sealings, All CDLI seals| - Creating Well Attested seals add and edit forms |[#700](https://gitlab.com/cdli/framework/-/issues/700)<br> [#1227](https://gitlab.com/cdli/framework/-/issues/1227)<br>[#1241](https://gitlab.com/cdli/framework/-/issues/1241)|[!661](https://gitlab.com/cdli/framework/-/merge_requests/661)<br>[!700](https://gitlab.com/cdli/framework/-/merge_requests/700)<br>[!737](https://gitlab.com/cdli/framework/-/merge_requests/737)|:heavy_check_mark: |
| 3 | Implementing seals single view | Implementation of a PHP library for graphical representation of chemical information of seals.<br>- A feature to view only top n elements (based on weight)<br>A switch to convert the graph into a table view. <br> - Graphical visualisation of element weight in that seal in the form of line chart and bar graph | -Creating add edit forms for seal chemistry.<br>-Creating add edit forms for seal chemistry standards. <br> - Export of chemical data as CSV | [#1332](https://gitlab.com/cdli/framework/-/issues/1132)<br>| [!687](https://gitlab.com/cdli/framework/-/merge_requests/687)<br>[!707](https://gitlab.com/cdli/framework/-/merge_requests/707) | :heavy_check_mark: |
| 4 | Adding image annotation viewer and integrating it with annotorious-open seadragon |Create the viewer page<br>- Generate tiles for deepzoom<br>- Integrate with annotorious-openseadragon||[#736](https://gitlab.com/cdli/framework/-/issues/736)<br>[#1288](https://gitlab.com/cdli/framework/-/issues/1288)| [!740](https://gitlab.com/cdli/framework/-/merge_requests/740)<br> [Viewer page branch](https://gitlab.com/cdli/framework/-/tree/phoenix/feature/viewerpage) | :heavy_check_mark: |
| 5 | Implement a convertor from coco format to w3c.json format |To Study more about w3c.json and COCO image annotations format<br>- Comparing both coco and w3c.json annotation formats to create SVG points layout<br>- Writing a python script that takes in coco_format and gives w3c.json format<br>- Add the convertor to the docker container.|| [#1430](https://gitlab.com/cdli/framework/-/issues/1430) | [Standalone repository for conversion](https://github.com/cdli-gh/coco-convertor) |:heavy_check_mark: |
| 6 | Search settings integration | Users will be able to save specific configuration of search settings and search results will be displayed accordingly. |[#540](https://gitlab.com/cdli/framework/-/issues/540) | [!332](https://gitlab.com/cdli/framework/-/merge_requests/332) | :heavy_check_mark: |
| 7 | Input flexibility enhancements |Users will have the flexibility to search with both UTF-8 and ASCII characters |[#597](https://gitlab.com/cdli/framework/-/issues/597)|[!375](https://gitlab.com/cdli/framework/-/merge_requests/375) |:heavy_check_mark: |
| 8 | Filter search results by RTI Image, Transliterations , 3D Data | Users can apply filters such as RTI Image, Transliterations, 3D Data and get search results | [#136](https://gitlab.com/cdli/framework/-/issues/136) | [!369](https://gitlab.com/cdli/framework/-/merge_requests/369) |:heavy_check_mark: |

## Preview of objectives

### 1. Keywords search
  - *Final outcome:*\
      Keywords search field can internally query all the fields of the database and return results accordingly.
  - *Methodology:*
      * Used Elasticsearch query DSL format in backend.
<center>

| Keyword's search |
| :---:	|
| <img src="assets/gifs/keywords.gif" width="800" height="450"> |
| Search results for "Vorderasiatisches Museum" in Keyword's field. |

</center>

### 2. Fuzzy Id's search
 - *Final outcome:*\
    Id's Search should yield results even if input query is not in exact format.
 - *Methodology:*
     * Processed the input query by applying regex operations before performing search.  
<center>

| Fuzzy Id's search |
| :---:	|
| <img src="assets/gifs/fuzzy-ids.gif" width="800" height="450"> |
| Search yields results even for improper input format "A1169" for Museum Id "OIM A01169" in Id's search |

</center>

### 3. Highlight inscriptions

- *Final outcome:*\
   Highlight the inscription input in search results.
- *Methodology:*
    * The text in the inscription field of each search result was processed using regex so that it can highlight the input query. 

<center>

| Highlight inscriptions |
| :---:	|
| <img src="assets/gifs/highlight-inscriptions.gif" width="800" height="450"> |
| Highlights the inscription input "muk" in search results |

</center>

### 4. Sign Value permutation

- *Final outcome:*\
   Search results of all possible sign-readings of input sign-values are returned.
- *Methodology:*
   * Sign names field was added and populated in database.
   * Containerised jtf-lib library in docker to make requests and get response in the framework.
   * Input query was converted to sign-names using jtf-lib and these sign-names along with sign-values are used to perform the search. 

<center>

| Sign Value permutation |
| :---:	|
| <img src="assets/gifs/sign-permutation.gif" width="800" height="450"> |
| All possible sign-readings of input "muk" can be searched with sign-name "MUG". |

</center>

### 5. Search Settings

- *Final outcome:*\
   Search settings can be saved in session and search results will be displayed accordingly. 
- *Methodology:*
   * Used cakePHP sessions to store the search settings and applied it on the search results.


<center>

| Search Settings |
| :---:	|
| <img src="assets/gifs/search-settings.gif" width="800" height="450"> |
| Removed "Museum collections" and "Period" from search results by modifing Search Settings.  |

</center>

### 6. Input flexibility enhancements

- *Final outcome:*\
   Users can search with both UTF-8 and ASCII characters
- *Methodology:*
   * Used UTF8 to ASCII mapping for converting the input into ASCII before performing search.

<center>

| Input flexibility enhancements |
| :---:	|
| <img src="assets/gifs/input-flexibility.gif" width="800" height="450"> |
| UTF-8 input "diš2" yields search results for ASCII format "disz2" |

</center>

### 7. Images and Transliteration Filter

- *Final outcome:*\
   Search results can be filtered w.r.t to Images and Transliteration according to the access of the user.
- *Methodology:*
   * Created new index for "Images" table.
   * Added elasticsearch queries which would filter results according to the access.

<center>

| Images and Transliteration Filter |
| :---:	|
| <img src="assets/gifs/images-filter.gif" width="800" height="450"> |
| Search results filtered having image type as "photo". |

</center>

## To Do (Post GSoC)

* Robust Testing of all newly added features.
* Documentation (User's and Developer's)

## Acknowledgements

Participating in GSoC was a great learning curve for me, I faced alot of challenges in this journey which helped me in learning new skills. I would like to thank my mentors [Vedant Wakalkar](https://www.linkedin.com/in/karna98/) and [Émilie](https://www.linkedin.com/in/epageperron/) for guiding me and helping me throughout my GSoC journey. I shall always be indebted to such a welcoming organisation to help me enhance my coding skills.
