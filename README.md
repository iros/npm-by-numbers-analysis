# NPM By Numbers, the Numbers

This is a companion repo to the `npm-by-numbers` repo hosted here:
http://github.com/iros/npm-by-numbers and hosted live here: http://npmbynumbers.bocoup.com.

## Prerequisites

This repository assumes that you have a local couchdb instance of skimdb, npm's metadata repository about its packages (everything but the binaries.)

You can set it up via the instructions here which will get you a vagrant instance up in no time: https://github.com/iros/local-npmjs-skimdb


## Data

Aside from creating a clone of npm's skimdb, this repo also contains scripts to generate
data files that can be used to analyze the data. They are all in the `scripts` directory.
All data goes into the `data` directory.

## Scripts

All scripts live in the `scripts` directory. All scripts write to `data/aggregate`.

### Prep scripts:

* `get_all_docs.js` - creates a file for each package under `data/packages`. It is a prerequisite for `get_all_packages.sh`.
* `get_all_packages.sh` - creates `data/all_packages_names.json` which is just an array of all available packages.
  It is a prerequisite for all other scripts.

### Data Scripts

* `build_metadata.js` - Builds a general metadata file for all packages called `data/packages_meta.csv`
* `build_dependencies.js` - Builds two dependency tree files, one for regular dependencies, and one for dev dependencies.
* `build_keyword_graph.js` - Builds a keyword source & target pairs for all keyword co-occurance + weight (count)
* `build_versions.js` - Builds a list of all versions per package & associated timestamps.

