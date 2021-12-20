# 2022 Team Review: Mass Spectrometry-based Multi-Omics
### project information


**Purpose.** This document is for collecting relevant papers and a to-do list of concepts we want to cover and figures we want to make. We will use [Manubot](https://github.com/manubot/manubot) to write this manuscript and track contributions. See the remaining readme below this section or at the link above for more information about manubot. 

**Authorship.** I will be the last author, and I suggest that Yuming take the lead. We will decide author order for everyone else based on the contributions recorded via github. We can consider co-first or co-second author depending on contributions. Our target Journal is [Nature Methods](https://www.nature.com/nmeth/content). 

**Organizing and listing of papers** can be done via a shared google doc here https://docs.google.com/document/d/1eruym4GMuzwwJbnksKrqL0SAqpoDZDZEoXF4wLfPWeI/edit?usp=sharing

**Effort.** This review should take second priority after primary research projects. I recommend scheduling 1 hour per day to work on the review. Personally, I like to have that hour in the morning when I arrive, but you may prefer right before you leave or mid-day. You will be surprised with how much you get done if you spend 1 hour per day. Some days you might spend more or less time on this depending on how your primary project is progressing. I expect at least some progress by everyone each week. 

**The focus** of this review is to provide an overview of mass spectrometry based multi-omics. Each of us will have different focus sections and roles:
1. Introduction, other reviews, discussion, section editing, organization, and integration (Jesse)
2. Data collection methods (Yuming)
3. Data integration methods (Quinn)
4. Clinical applications of multi-omics (Amanda)

**How to use this document.** The following pages contain lists of manuscripts to cover in each section along with notes about each paper. See the first papers I have added for examples. Anyone should feel free to add any paper you find to any section you think it fits in. Please check that the paper is not already listed there. 

Writing a review is easy if you break it down into parts. 
First do literature searches for papers relevant to the topic. Make lists of those papers with a few brief notes about each paper when you add it to the list. 
Organize the discovered papers into related groups
Convert and extend notes into a paragraph describing each paper. Highly related papers can be grouped into the same paragraph. Remember to use one topic sentence at the beginning of the paragraph that gives the focus of that paragraph. 
While we are writing and collecting papers, think about what key concepts need to be represented by figures, or what meta-analyses we could easily do to summarize the field. Sketch those figures freehand or in drawing software and we can have a graphic designer finish them




# Automated scholarly manuscripts on GitHub

<!-- usage note: edit the H1 title above to personalize the manuscript -->

[![HTML Manuscript](https://img.shields.io/badge/manuscript-HTML-blue.svg)](https://jessegmeyerlab.github.io/2022-multi-omics-review/)
[![PDF Manuscript](https://img.shields.io/badge/manuscript-PDF-blue.svg)](https://jessegmeyerlab.github.io/2022-multi-omics-review/manuscript.pdf)
[![GitHub Actions Status](https://github.com/jessegmeyerlab/2022-multi-omics-review/workflows/Manubot/badge.svg)](https://github.com/jessegmeyerlab/2022-multi-omics-review/actions)

## Manuscript description

<!-- usage note: edit this section. -->

This repository is a template manuscript (a.k.a. rootstock).
Actual manuscript instances will clone this repository (see [`SETUP.md`](SETUP.md)) and replace this paragraph with a description of their manuscript.

## Manubot

<!-- usage note: do not edit this section -->

Manubot is a system for writing scholarly manuscripts via GitHub.
Manubot automates citations and references, versions manuscripts using git, and enables collaborative writing via GitHub.
An [overview manuscript](https://greenelab.github.io/meta-review/ "Open collaborative writing with Manubot") presents the benefits of collaborative writing with Manubot and its unique features.
The [rootstock repository](https://git.io/fhQH1) is a general purpose template for creating new Manubot instances, as detailed in [`SETUP.md`](SETUP.md).
See [`USAGE.md`](USAGE.md) for documentation how to write a manuscript.

Please open [an issue](https://git.io/fhQHM) for questions related to Manubot usage, bug reports, or general inquiries.

### Repository directories & files

The directories are as follows:

+ [`content`](content) contains the manuscript source, which includes markdown files as well as inputs for citations and references.
  See [`USAGE.md`](USAGE.md) for more information.
+ [`output`](output) contains the outputs (generated files) from Manubot including the resulting manuscripts.
  You should not edit these files manually, because they will get overwritten.
+ [`webpage`](webpage) is a directory meant to be rendered as a static webpage for viewing the HTML manuscript.
+ [`build`](build) contains commands and tools for building the manuscript.
+ [`ci`](ci) contains files necessary for deployment via continuous integration.

### Local execution

The easiest way to run Manubot is to use [continuous integration](#continuous-integration) to rebuild the manuscript when the content changes.
If you want to build a Manubot manuscript locally, install the [conda](https://conda.io) environment as described in [`build`](build).
Then, you can build the manuscript on POSIX systems by running the following commands from this root directory.

```sh
# Activate the manubot conda environment (assumes conda version >= 4.4)
conda activate manubot

# Build the manuscript, saving outputs to the output directory
bash build/build.sh

# At this point, the HTML & PDF outputs will have been created. The remaining
# commands are for serving the webpage to view the HTML manuscript locally.
# This is required to view local images in the HTML output.

# Configure the webpage directory
manubot webpage

# You can now open the manuscript webpage/index.html in a web browser.
# Alternatively, open a local webserver at http://localhost:8000/ with the
# following commands.
cd webpage
python -m http.server
```

Sometimes it's helpful to monitor the content directory and automatically rebuild the manuscript when a change is detected.
The following command, while running, will trigger both the `build.sh` script and `manubot webpage` command upon content changes:

```sh
bash build/autobuild.sh
```

### Continuous Integration

Whenever a pull request is opened, CI (continuous integration) will test whether the changes break the build process to generate a formatted manuscript.
The build process aims to detect common errors, such as invalid citations.
If your pull request build fails, see the CI logs for the cause of failure and revise your pull request accordingly.

When a commit to the `main` branch occurs (for example, when a pull request is merged), CI builds the manuscript and writes the results to the [`gh-pages`](https://github.com/jessegmeyerlab/2022-multi-omics-review/tree/gh-pages) and [`output`](https://github.com/jessegmeyerlab/2022-multi-omics-review/tree/output) branches.
The `gh-pages` branch uses [GitHub Pages](https://pages.github.com/) to host the following URLs:

+ **HTML manuscript** at https://jessegmeyerlab.github.io/2022-multi-omics-review/
+ **PDF manuscript** at https://jessegmeyerlab.github.io/2022-multi-omics-review/manuscript.pdf

For continuous integration configuration details, see [`.github/workflows/manubot.yaml`](.github/workflows/manubot.yaml).

## License

<!--
usage note: edit this section to change the license of your manuscript or source code changes to this repository.
We encourage users to openly license their manuscripts, which is the default as specified below.
-->

[![License: CC BY 4.0](https://img.shields.io/badge/License%20All-CC%20BY%204.0-lightgrey.svg)](http://creativecommons.org/licenses/by/4.0/)
[![License: CC0 1.0](https://img.shields.io/badge/License%20Parts-CC0%201.0-lightgrey.svg)](https://creativecommons.org/publicdomain/zero/1.0/)

Except when noted otherwise, the entirety of this repository is licensed under a CC BY 4.0 License ([`LICENSE.md`](LICENSE.md)), which allows reuse with attribution.
Please attribute by linking to https://github.com/jessegmeyerlab/2022-multi-omics-review.

Since CC BY is not ideal for code and data, certain repository components are also released under the CC0 1.0 public domain dedication ([`LICENSE-CC0.md`](LICENSE-CC0.md)).
All files matched by the following glob patterns are dual licensed under CC BY 4.0 and CC0 1.0:

+ `*.sh`
+ `*.py`
+ `*.yml` / `*.yaml`
+ `*.json`
+ `*.bib`
+ `*.tsv`
+ `.gitignore`

All other files are only available under CC BY 4.0, including:

+ `*.md`
+ `*.html`
+ `*.pdf`
+ `*.docx`

Please open [an issue](https://github.com/jessegmeyerlab/2022-multi-omics-review/issues) for any question related to licensing.
