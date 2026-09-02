# Biomedical Open Case Studies: Making Version Controlled Reproducible Analyses

### Useful Links

-   HTML: <https://www.opencasestudies.org/ocs-bio-version-control/>
-   GitHub:
    <https://github.com/opencasestudies/ocs-bio-version-control>

### Disclaimer

The purpose of the [Open Case
Studies](https://opencasestudies.github.io) project is **to demonstrate
the use of various data science methods, tools, and software in the
context of messy, real-world data**. A given case study does not cover all 
aspects of the research process, is not claiming to be the most appropriate 
way to analyze a given data set, and should not be used in the context of 
making policy or clinical decisions without external consultation from scientific 
experts or medical care professionals. In addition, due to size constraints, 
datasets used within a case study may be a subset of the original/full dataset.

### License

This work is licensed under the Creative Commons Attribution-NonCommercial 4.0 [(CC BY-NC 4.0)](https://creativecommons.org/licenses/by-nc/4.0/deed.en) United States License unless otherwise noted.

### Citation

To cite this case study:

Teichman, Sarah and Wright, Carrie. (2026). [https://github.com/opencasestudies/ocs-bio-version-control/](https://github.com/opencasestudies/ocs-bio-version-control/). Making version-controlled reproducible analyses (Version v1.0.0).

### Funding

This work is funded through the National Institutes of Health, specifically the National Institute of General Medical Sciences: Grant Number 1R25GM160622.

### Acknowledgments

We would like to acknowledge [Candace Savonen](https://www.cansavvy.com), [Casey Greene](https://greenelab.com/members/casey-greene.html), [Emma Lathouwers](https://greenelab.com/members/emma-lathouwers.html), and [Taylor Reiter](https://taylorreiter.github.io) for their expert review of this case study.

We would also like to acknowledge the National Institute of General Medical Sciences for funding this work (1R25GM160622).

Icons are from [iconpacks](https://www.iconpacks.net).

Avatars are from [getavataaars](https://getavataaars.com).

### Title

Making Version Controlled Reproducible Analyses

### Prerequisites

To follow along with this case study, you'll need the following installed:

- R ([install here](https://www.r-project.org))
- RStudio ([install here](https://posit.co/download/rstudio-desktop)) or Positron ([install here](https://positron.posit.co/install.html)) or another IDE compatible with R

It will also be helpful to be have the following skills:

- basic R skills (many introductory courses can be found online, including [this one](https://hutchdatascience.org/Intro_to_R/))
- familiarity with `dplyr` and `ggplot2`, or willingness to learn (these [`dplyr`](https://rstudio.github.io/cheatsheets/data-transformation.pdf) and [`ggplot2`](https://rstudio.github.io/cheatsheets/data-visualization.pdf) cheatsheets may be helpful, as well as the original [open case studies](https://www.opencasestudies.org/search.html))

You do not need to have any previous Git and GitHub knowledge or experience for this case study. 

### Target Audience

The target audience for this case study is scientists and researchers who use R but do not use version control.

### Motivation

This case study introduces version control in the context of a realistic collaborative scientific project. 
Using a meta-analysis of infant gut microbiome studies as an example, learners work through a preliminary 
data analysis while managing a version-controlled research workflow with Git and GitHub. This case study teaches
what version control is and the role it plays in collaborative and reproducible science, and gives the learner 
practice in created a version-controlled repository and tracking changes to an analysis using Git and GitHub. 

### Main Questions

The main questions in this case study are the following:

1. How does the use of version control contribute to transparent and reproducible science?
1. How can Git and GitHub be used to facilitate collaboration on a research project?
1. In this meta-analysis of infant git microbiome samples, how do the original studies compare in their sampling designs?

### Learning Objectives

The learning objectives of this case study are the following:

<u>**Data Science Learning Objectives**</u>

1. Understand ways in which version control facilitates reproducible science
1. Understand how version control works by recording differences between versions of a project
1. Follow a workflow to create and make changes to a repository with Git and GitHub
1. Make pull requests to propose changes to a codebase and request review from a collaborator
1. Organize a repository for a project with a README file and folders for data, figures, and results

<u>**Biological/Bioinformatics Objectives:**</u>

1. Understand the value and limitations of combining data from multiple studies in a meta-analysis.
1. Use visualizations to compare sampling designs across a set of studies. 

### Context 

A microbiome is a collection of microorganisms that live in a particular environment. One commonly studied microbiome is the human gut microbiome. 
In this case study, we examine data from several studies that have collected longitudinal gut microbiome samples from infant-mother pairs in order to
understand how the infant gut microbiome develops over time and how it relates to the maternal microbiome. 

A meta-analysis combines data or results from multiple studies investigating a common research question. The scientific
paper that reference performed a meta-analysis of eight longitudinal gut microbiome studies. In the case study, we ask how comparable
the original studies in their study design, specifically in terms of their sample sizes and longitudinal sampling designs.

### Introduction to Git and GitHub

We provide an explanation of how reproducibility fits into the scientific process and how version control facilitates reproducible analyses.
We describe Git and GitHub and how they work together. We guide the learner through creating a GitHub account and their first GitHub repository. 
We next walk through installing Git locally and connecting Git and GitHub to each other. The learner makes a local clone of their first GitHub repo, 
and works through the staging, commiting, pushing, and pulling process. We then have the learner download a folder of files related to the microbiome
meta-analysis study design comparison, and have them track the folder locally with Git and make a remote version on GitHub. Finally, we discuss
branches and have the learner make a new branch for their analysis. 

### Scientific Project Organization

We include a section on recommendations for scientific project organization. This includes file and folder organization, README documents,
files to track with Git and .gitignore files, and working with large files. 

### What are the Data?

In this case study, we will investigate data about samples from [this meta-analysis](https://www.tandfonline.com/doi/full/10.1080/19490976.2021.1911571) of mother and infant gut {{< glossary "microbiome">}} studies. Wang et al. identified a set of eight studies that collected mother and infant gut microbiome samples over time and performed metagenomic sequencing. These studies collectively include 1,496 samples. The variables that we will use to answer our questions include:

Variable | Details
-------- | -------
**Study** | Original study the sample comes from 
**SampleID** | ID for sample
**PersonID** | ID for participant the sample came from
**Category** | Either "mother" or "infant"
**Sampling from papers** | Sampling time frame described in paper 
**Sampling, day** | Day after birth that the sample was collected on

### Limitations

We describe limitations of this data, as well as limitations of version control (including the need to make commits, challenges of version control with large files, and the future evolution of version control software).

### Ethical Considerations

We describe several ethical considerations of working with version control, including taking care to not include PII or PHI in online repositories. 

### Packages used in this case study

Package    | Use
---------- |-------------
[here](https://here.r-lib.org) | To construct file paths within folders
[readxl](https://readxl.tidyverse.org){target="_blank"}      | To read excel files into R
[dplyr](https://dplyr.tidyverse.org){target="_blank"}      | To combine and manipulate data tables
[ggplot2](https://ggplot2.tidyverse.org) | To visualize data
[stringr](https://stringr.tidyverse.org) | To manipulate strings


### Data Import

In this section, we ask the learner to open the file in their repository that laods data, run the file, and answer a question about the dataset. 

### Data Wrangling

In this section, we ask the learner to open the file in their repository that wrangles data, run the file, and answer a question about the wrangled data.

### Data Visualization

In this section, we guide the learner through creating two plots to compare the designs of the studies included in the meta-analysis. After each update, 
the learner documents changes in the README document and stages and commits their changes. Finally, they push their updates to the remote repository.

### Pull Requests

In this section, we describe what a pull request is and why it is useful, and prompt the learner to create a pull request with their plots and analysis. 

### Summary 

This section summarizes the case study, gives the learner a chance to drag and drop elements of their version controlled workflow from the case study into the correct order,
emphasizing major steps along the way. This section also includes the main image, reminding the learner of the motivation for using version control instead of emailing project 
files back and forth with collaborators.

### Troubleshooting Git and GitHub

This section provides guidance for dealing with merge conflicts, stopping version control for specific files, and for mistakenly committing large files.
It also provides guidance on using AI for troubleshooting Git and GitHub.

### Continued Learning

This section provides suggestions to reinforce version control skills by making other scientific project folders into version-controlled repositories, 
adding additional branches to their analysis from the case study, and adding collaborators to repositories. This section also introduces the concept of forking,
and guides the learner in forking a repository with files for their analysis, adding in the plots they made in the case study, and opening a pull request from their
fork. 

### Other notes and resources

- [happy git with R](https://happygitwithr.com): online book that covers most relevant topics for using Git and GitHub with R
- [How to Use Git/GitHub with R](https://rfortherestofus.com/2021/02/how-to-use-git-github-with-r): blog post about getting Git and GitHub set up and working with RStudio. This uses the built-in Git GUI in RStudio instead of GitHub Desktop
- [Dangit, Git!?!](https://dangitgit.com/en): brief description of some common Git errors and how to resolve them
- [Intro to reproducibility in cancer informatics](https://jhudatascience.org/Reproducibility_in_Cancer_Informatics/): short course on reproducibility for scientific projects, includes Git and GitHub in chapter 4 and provides other resources on reproducibility
- [Advanced reproducibility in cancer informatics](https://jhudatascience.org/Adv_Reproducibility_in_Cancer_Informatics/): short course on more advanced reproducibility for scientific projects, includes GitHub in chapter 3 and provides other resources on reproducibility
- [Carpentries](https://carpentries.org):
  - [Install Git](https://carpentries.github.io/workshop-template/install_instructions/): instructions on installing Git (and other types of software)
  - [Set up Git](https://swcarpentry.github.io/git-novice/02-setup.html): instructions on setting up Git
  - [Build on existing branch](https://docs.carpentries.org/resources/curriculum/fetch-existing-branch.html): instructions on how to work from a branch on someone else's fork of a repository 
- [Hands on introduction to Git and GitHub](https://training.arcadiascience.com/workshops/20220920-intro-to-git-and-github/lesson/): another introduction to Git and GitHub, covering some overlapping material and some additional material
- [Contributing to Galaxy Training Network with GitHub](https://training.galaxyproject.org/training-material/topics/contributing/tutorials/github-contribution/tutorial.html): tutorial on how to contribute to an open source project with GitHub
- [GitHub cheatsheet](https://education.github.com/git-cheat-sheet-education.pdf): cheatsheet with Git commands that can be used in the command line
