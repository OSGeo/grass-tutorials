---
title: 'Tutorials for the GRASS geocomputation engine'
tags:
  - GRASS
authors:
  - name: Brendan A. Harmon
    orcid: 0000-0002-6218-9318
    affiliation: 1
  - name: Veronica Andreo
    orcid: 0000-0002-4633-2161
    affiliation: 2
  - name: Anna Petrasova
    orcid: 0000-0002-5120-5538
    affiliation: 3
  - name: Vaclav Petras
    orcid: 0000-0001-5566-9236
    affiliation: 3
  - name: Caitlin Haedrich
    orcid: 0000-0003-4373-5691
    affiliation: 3
  - name: Corey White
    orcid: 0000-0002-2903-9924
    affiliation: 3
affiliations:
 - name: Louisiana State University, United States
   index: 1
   ror: 05ect4e57
 - name: Instituto Gulich, Argentina
   index: 2
   ror: 00pw52a85
 - name: North Carolina State University, United States
   index: 3
   ror: 04tj63d06
date: 2 September 2025
bibliography: paper.bib

---

![An example of fractal terrain generated with GRASS and eroded with LandLab from a [tutorial](https://grass-tutorials.osgeo.org/content/tutorials/numpy_integration/grass_numpy_integration.html) on scientific modeling. This tutorial demonstrates a seamless workflow for scientific modeling in Python, showing how gridded data can be passed as arrays between GRASS, NumPy [@Harris:2020], and Landlab [@Barnhart:2020]. \label{fig:figure_1}](figure_1.png){ width=100% }

# Summary

This collection of tutorials is an introduction to the GRASS geospatial processing engine. GRASS is an open source computational engine for spatiotemporal data management, analysis, modeling, and simulation [@GRASS; @Neteler:2008]. As an engine that can be integrated in data science pipelines with shell scripting, Python, R, Jupyter, and Colab, there are many ways to use GRASS.  While GRASS already had extensive documentation of individual processing tools, tutorials were needed to introduce the many ways to interface with the tools and combine them into computational workflows (\autoref{fig:figure_1}). These open education tutorials - which cover integrations, core features, and disciplinary applications - were developed as part of an effort to grow the GRASS community. The tutorials are built with Quarto and are deployed as webpages paired, when appropriate, with Jupyter computational notebooks. The tutorials are available at https://grass-tutorials.osgeo.org under both the GNU Free Documentation License v1.2 or later and the Creative Commons Attribution-ShareAlike 4.0 International License.

# Statement of Need

As GRASS has grown from its roots as a geographic information system [@Westervelt:2004], it has evolved into a geocomputational engine with many interfaces. As an engine, it can be integrated in geospatial data science pipelines using shell scripting, application programming interfaces, tangible interfaces [@Petrasova:2018], computational notebooks [@Haedrich:2023], cloud computing environments [@Neteler:2019; @White:2023], or high performance computing environments. While GRASS is well documented with books, a user manual, developer manuals, and a wiki, it lacked official tutorials. Over the years, the community developed many tutorials across different platforms, but as these are independently maintained, many have become outdated and obsolete. The current roadmap for GRASS – established in 2024 – calls for official new tutorials to encourage community growth and demonstrate integrations in data science pipelines. 

The design and implementation of the new official tutorials for GRASS was based on experience teaching university courses and conference workshops using open educational resources. Over the last decade, the GRASS community has developed many open educational resources, experimenting with delivery via web documents, computational notebooks, and cloud computing services. Online tutorials for GRASS have been built from source in HTML [@Petras:2015], built from Markdown with a static site generator [@Harmon:2020], included Jupyter notebooks [@Haedrich:2023], and used cloud computing services such as Binder [@Petrasova:2019], Whole Tale [@Andreo:2023a], and Google Colab [@Andreo:2023b]. @Petras:2015 used a modular structure with tabsets to teach the core interfaces for GRASS – the GUI, CLI, and Python API – separating explanatory text introducing geospatial concepts from software specific text for each interface. This scaffolding helps learners to focus on concepts, while building their skills with increasingly complex interfaces. @Haedrich:2023 developed the GRASS–Jupyter integration to incorporate more scripting into a graduate-level course on geospatial computing and simulation. The package extends the existing GRASS Python APIs with data visualization and management tools for the Jupyter environment. The new course materials include Jupyter Notebooks that combine tutorials and assignments, allowing students to write and modify code, interact with examples, and explain their reasoning in markdown, all within a single document. Based on these experiences, our design principles for the new tutorials include teaching geospatial concepts discretely from software specifics to encourage spatial thinking, supporting live coding to encourage computational thinking, and using an open source publishing system to build documents from plain text tracked with version control.

![An example of image fusion of principal components analysis of multi-band images of the San Francisco volcanic field from a [tutorial](https://grass-tutorials.osgeo.org/content/tutorials/remote_sensing_visualization/GRASS_remotesensing.html) introducing the basics of remote sensing in GRASS. This tutorial demonstrates how to process and visualize multi-band remote sensing imagery. \label{fig:figure_2}](figure_2.png){ width=100% }

# Description

## Learning Objectives

This collection of tutorials was designed to teach geocomputational thinking using the GRASS geoprocessing engine. To introduce computational approaches to thinking [@NRC:2010; @Weintrop:2016] about space and time, the tutorials cover the fundamentals of geoprocessing with GRASS, integrations of GRASS into data science pipelines, and disciplinary applications of GRASS. The tutorials were designed for self-study by learners of all levels, integration into courses, and deployment in workshops.

## Instructional Design

In order to teach a computational approach to thinking about spatiotemporal phenomena through different interfaces to the GRASS engine, the tutorials were designed: 

* as modules for reuse and remixing, 
* as worked examples to reduce cognitive load, 
* as interactive lessons for active learning and engagement, 
* as scaffolded prose and code to structure learning, 
* and as computable content to teach computational thinking. 

Drawing on the education benefits of computational notebooks [@Barba:2022], the tutorials introduce geocomputational concepts through worked examples that synthesize prose explanations, graphics, and executable code. The tutorials, which range from introductory to advanced, have a modular design for reuse and remixing so that learners can choose their own course of study and teachers can select modules for their lesson plans. The tutorials build in complexity from introductory to core to disciplinary modules. A set of getting-started tutorials introduce different ways to interface with the GRASS engine. The core tutorials cover important concepts such as geovisualization (\autoref{fig:figure_2}), map algebra (\autoref{fig:figure_3}), geospatial modeling, and the temporal framework. Disciplinary tutorials demonstrate applications for GRASS in domains such as climatology, ecology, hydrology, geomorphology, and terrain generation (\autoref{fig:figure_4}). The disciplinary tutorials build engagement by working through applications in the learner’s domain and thus motivate further exploration. Throughout the tutorials, different ways to interface with GRASS are presented as tabs in code blocks, so that learners can work their way through the same tutorial repeatedly using increasingly challenging interfaces – building proficiency first with the graphical user interface (GUI), then with the command line interface (CLI), and finally with the Python or R application programming interfaces (API).

![An example of synthetic terrain generated using map algebra from a [tutorial](https://grass-tutorials.osgeo.org/content/tutorials/map_algebra/basic_map_algebra.html) introducing the basics of map algebra in GRASS. This tutorial demonstrates local algebraic operations using the raster map calculator, focal operations using nearest neighbors analysis, zonal operations using conditional statements with the raster map calculator, and global operations using raster metadata. \label{fig:figure_3}](figure_3.png){ width=100% }

## Implementation

To reach a broad audience, the tutorials in this collection are published as web documents for immediate, easy access via web browsers. When appropriate, web documents are accompanied by a downloadable computational notebook, encouraging  interactivity, engagement, and geocomputational thinking. The tutorials – which are built and deployed using the Quarto scientific publishing system [@Quarto] – are written in Markdown with YAML frontmatter. Tutorials are composed in Markdown for human-readable source code, efficient version control, executable code blocks for different interfaces, rendering in multiple formats, and reproducibility. As this open education project aims to teach different ways to interface with GRASS, executable code for multiple relevant interfaces such as the GUI, CLI, Python, or R can be included in tutorials as tabsets. Once tutorials have been written, they are reviewed by the GRASS Development Team, rendered as web documents and Jupyter notebooks, and deployed to an Open Source Geospatial Foundation website. The source code for the tutorials is built in the GitHub [repository](https://github.com/OSGeo/grass-tutorials) and deployed to the website <https://grass-tutorials.osgeo.org> using GitHub Actions. 

![An example of fractional Brownian motion from a [tutorial](https://grass-tutorials.osgeo.org//content/tutorials/noise/noise.html) introducing procedural noise in GRASS. This tutorial demonstrates stochastic functions for procedurally generating data. \label{fig:figure_4}](figure_4.png){ width=100% }

## Content

This official collection of tutorials is maintained by the GRASS Development Team as part of the documentation for the GRASS geocomputational engine (\autoref{table:official}). This ensures that tutorials are standardized, undergo rigorous review, and are maintained and updated as GRASS evolves. The website also includes a curated collection of external tutorials that are hosted and maintained by their creators (\autoref{table:external}). 

: Official GRASS tutorials \label{table:official}

| Modules      | Tutorials                                               | Level | Lang.   |
|--------------|---------------------------------------------------------|-------|---------|
| Integrations | Get started with GRASS GUI                              | Beg   | En      |
|              | Get started with GRASS & Python in Jupyter Notebooks    | Beg   | En      |
|              | Get started with GRASS in Google Colab                  | Beg   | En      |
|              | Getting started with GRASS for Conda                    | Beg   | En      |
|              | Get started with GRASS in Jupyter Notebooks on Windows  | Beg   | En      |
|              | Quick comparison: R and Python GRASS interfaces         | Int   | En      |
|              | Get started with GRASS & R: the rgrass package          | Adv   | En      |
| Core         | Basics of map algebra                                   | Beg   | En      |
|              | Making plots with GRASS                                 | Beg   | En      |
|              | Visualizing and modeling terrain from DEMs              | Beg   | En & Pt |
|              | Introduction to remote sensing with GRASS               | Beg   | En & Pt |
|              | Making thematic maps                                    | Beg   | En      |
|              | Introduction to time series in GRASS                    | Int   | En      |
|              | Temporal subset, import and export                      | Int   | En      |
|              | Temporal aggregations                                   | Adv   | En      |
|              | Temporal algebra                                        | Adv   | En      |
|              | Temporal accumulation                                   | Adv   | En      |
|              | Temporal gap-filling                                    | Adv   | En      |
|              | Temporal query with vector data                         | Adv   | En      |
|              | Modeling movement in GRASS                              | Adv   | En & Pt |
| Disciplinary | Basic earthworks                                        | Beg   | En      |
|              | Gully modeling                                          | Beg   | En      |
|              | Coastal infrastructure                                  | Beg   | En      |
|              | Terrain synthesis                                       | Int   | En      |
|              | Procedural noise                                        | Int   | En      |
|              | Hydro-flattening a digital elevation model              | Int   | En      |
|              | Using GRASS, NumPy, and Landlab for scientific modeling | Int   | En      |
|              | fasterRaster: faster raster processing in R using GRASS | Int   | En      |
|              | Estimating wind fetch                                   | Adv   | En      |
|              | Parallelization of overland flow simulation             | Adv   | En      |

: External tutorials \label{table:external}

| Modules      | Tutorials                                                       | No. | Level   | Lang.   |
|--------------|-----------------------------------------------------------------|-----|---------|---------|
| Integrations | Unleash the power of GRASS                                      | 5   | Beg-Adv | En      |
|              | GRASS for remote sensing data processing with Jupyter Notebooks | 1   | Adv     | En      |
| Core         | NCSU geospatial modeling and analysis course                    | 13  | Beg-Int | En      |
|              | Geoprocessamento com GRASS                                      | 1   | Beg-Int | Pt      |
|              | Tutoriales de GRASS en grasswiki                                | 4   | Beg-Int | Es      |
|              | GISMentors                                                      | 30  | Beg-Adv | En & Cs |
| Disciplinary | Deforestation study using GRASS                                 | 1   | Beg     | En      |
|              | Teledetección, OBIA y series de tiempo                          | 5   | Beg-Adv | Es      |
|              | GIS for designers                                               | 12  | Beg-Int | En      |
|              | GRASS for environmental monitoring and disease ecology          | 2   | Beg-Int | En      |
|              | Processing lidar and UAV point clouds                           | 1   | Beg-Int | En      |
|              | Physically-based hydrologic modeling using GRASS r.topmodel     | 1   | Int     | En      |
|              | Spatio-temporal data handling and visualization                 | 1   | Int     | En      |
|              | Ecodiv.earth tutorials                                          | 16  | Beg-Adv | En      |
|              | Urban growth modeling with FUTURES                              | 1   | Adv     | En      |

## Acknowledgements

The development of the tutorial platform and the majority of the tutorials presented in this collection were supported by the U.S. National Science Foundation under Award No. [2303651](https://www.nsf.gov/awardsearch/showAward?AWD_ID=2303651). This grant directly funded the development of tutorials and also funded mentor support for community contributors working on tutorial content. Two tutorials received additional partial support from NSF Award No. [2322073](https://www.nsf.gov/awardsearch/showAward?AWD_ID=2322073) granted to Natrx, Inc. Another tutorial was developed with combined support from NSF Award No. 2322073 and USDA NRCS Award No. NR233A750023C043. We thank the GRASS development team and the broader GRASS community for their continued support and contributions to this educational effort.

## References
