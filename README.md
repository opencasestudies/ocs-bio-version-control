# Bio-OCS Quarto Template

This is a template for creating websites from qmd files hosted on GitHub with three helpful automations following a pull request to the repository:

- Spelling check
- Broken link check
- Website rendering.

This is all supported by the OTTR Template, specifically the [OTTR Quarto Web](https://github.com/ottrproject/OTTR_Quarto_Website) version.

- Check for spelling errors more intensively than RStudio and allow you to add words to the dictionary
- Check for broken links - you will be warned about broken links
- Automatic rendering of the website for previewing before merges
- Automatic rendering of the website upon merging to main
- Docker images that can be customized.

This specific template sets up the style and content template for Biomedical Open Case Studies (Bio-OCS).

## Repository Structure + Checklist for files to update when using the template

### Style and Configuration

* _quarto.yml -- Configurations for how the rendered website will look.
  * [x] Update the title on line 6
  * [x] Replace the Google analytics tracking ID ("G-XXXXXXXXXX") with the appropriate Bio_OCS case study specific tracking ID on line 17
  * [x] Update the GitHub Repository link to point to the specific open case studies repository instead of the template
    * [x] line 11
    * [x] line 28

The rest of these files will largely not need updated though a brief description of what each contains is provided.

* styles.css -- Defines html elements
* _brand.yml -- Logo and favicon definition
* config_automation.yml	-- Configurations for the OTTR Template automations. Update this file to toggle spelling or url check as well as minimum errors allowed for those checks or to update the docker image.

### Directories

* `data/`: Raw, imported, and wrangled datasets. `raw/pm25_data.csv`, `imported/pm25_data_imported.rda`, and `wrangled_data.csv` are template files that can be removed or overwritten by case study repositories.
* `assets/`: Template images such as the logo or icons.
* `img/`: This is where images should go for the case study background, motivation, etc.
  - [x] Replace the `mainplot.png` from the template with your main plot
  - [x] Add any additional case study specific (non-template) images in this directory
* `resources/`: Files related to OTTR checks (e.g., dictionary and a file of URLs to exclude/ignore from checking.).
* `.github/`: workflow files supporting the OTTR template automations
* `docs/`: the rendered files that GitHub pages will use -- refreshed through OTTR template automations.


### Content

For the overall content of the Open Case Study, each portion of the case study is split into individual `.qmd` files. They are included in order within the `index.qmd` file. Certain case studies will not have every component, and so we can toggle those on and off using short code and header booleans.  This is mostly for others using our case studies to teach, as they might want to have a version that only has part of the case study.  For our core team, we will likely have all components for our case studies. Below is a list of all of the sub-component `.qmd` files in checklist form. Besides the listed changes below, `index.qmd` should not need updated.

* [x] `index.qmd`
  * [x] Update Case Study Title
  * [x] Update any header booleans for section inclusion or add additional short code content-hidden sections as necessary
* [x] _main_image.qmd
  * Provides an example of including images with Quarto
  * [x] switch out `mainplot.png` within the `img` directory to be the case study main plot.
* [x] _ocs_frontmatter.qmd
* [x] _cite.qmd
* [x] _motivation.qmd
  * Provides an example of including images with Quarto (including those that you can click to open in a larger preview)
  * Provides an example of a custom definition box
* [x] _main_question.qmd
* [x] _los.qmd
  * [x] _data_science_los.qmd
  * [x] _statistical_los.qmd
  * [x] _biological_los.qmd
* [x] _packages.qmd
* [x] _context.qmd
  * Provides an example of including a video with Quarto
* [x] _data_description.qmd
* [x] _limitations.qmd
* [x] _bioethics.qmd
* [x] _data_import.qmd
* [x] _data_exploration.qmd
* [x] _data_wrangling.qmd
  * Provides an example of including code annotations with Quarto
* [x] _data_visualization.qmd
* [x] _data_analysis.qmd
  * Provides an example of using a column margin note with Quarto
  * Provides an example of a custom question opportunity box
* [x] _summary.qmd
* [x] _suggested_hw.qmd
* [x] _additional_info.qmd
* [x] _acknowledgements.qmd

* [x] **Verify**
  * [x] Every image ....
    * [x] has accompanying alt text (using `{fig-alt=""}`)
    * [x] has lightbox capability enabled (using `{.lightbox}`) so that images can be opened in a larger preview
