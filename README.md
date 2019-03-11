# vfatqc-python-scripts

Branch|[Travis CI](https://travis-ci.org)|[Coveralls](https://www.coveralls.io)|[Codecov](https://www.codecov.io)|[Codacy](https://www.codacy.com)|[Landscape](https://www.landscape.io)|[CodeClimate](https://www.codeclimate.com)
---|---|---|---|---|---|---
master|[![Build Status](https://travis-ci.org/cms-gem-daq-project/vfatqc-python-scripts.svg?branch=master)](https://travis-ci.org/travis-ci.org/cms-gem-daq-project/vfatqc-python-scripts)|[![Coveralls Status](https://coveralls.io/repos/github/cms-gem-daq-project/vfatqc-python-scripts/badge.svg?branch=master)](https://coveralls.io/github/cms-gem-daq-project/vfatqc-python-scripts?branch=master)|[![codecov](https://codecov.io/gh/cms-gem-daq-project/vfatqc-python-scripts/branch/master/graph/badge.svg)](https://codecov.io/gh/cms-gem-daq-project/vfatqc-python-scripts)|[![Codacy Badge](https://api.codacy.com/project/badge/Grade/00f0de54bcc94812b553ebeab74e9320)](https://www.codacy.com/app/cms-gem-daq-project/vfatqc-python-scripts?utm_source=github.com&amp;utm_medium=referral&amp;utm_content=cms-gem-daq-project/vfatqc-python-scripts&amp;utm_campaign=Badge_Grade)|[![Landscape Status](https://landscape.io/github/cms-gem-daq-project/vfatqc-python-scripts/master/landscape.svg)](https://landscape.io/github/cms-gem-daq-project/vfatqc-python-scripts/master)|[![Code Climate](https://codeclimate.com/github/cms-gem-daq-project/vfatqc-python-scripts/badges/gpa.svg)](https://codeclimate.com/github/cms-gem-daq-project/vfatqc-python-scripts)
develop|[![Build Status](https://travis-ci.org/cms-gem-daq-project/vfatqc-python-scripts.svg?branch=develop)](https://travis-ci.org/travis-ci.org/cms-gem-daq-project/vfatqc-python-scripts)|[![Coveralls Status](https://coveralls.io/repos/github/cms-gem-daq-project/vfatqc-python-scripts/badge.svg?branch=develop)](https://coveralls.io/github/cms-gem-daq-project/vfatqc-python-scripts?branch=develop)|[![codecov](https://codecov.io/gh/cms-gem-daq-project/vfatqc-python-scripts/branch/develop/graph/badge.svg)](https://codecov.io/gh/cms-gem-daq-project/vfatqc-python-scripts)|[![Codacy Badge](https://api.codacy.com/project/badge/Grade/00f0de54bcc94812b553ebeab74e9320)](https://www.codacy.com/app/cms-gem-daq-project/vfatqc-python-scripts?utm_source=github.com&amp;utm_medium=referral&amp;utm_content=cms-gem-daq-project/vfatqc-python-scripts&amp;utm_campaign=Badge_Grade)|[![Landscape Status](https://landscape.io/github/cms-gem-daq-project/vfatqc-python-scripts/develop/landscape.svg)](https://landscape.io/github/cms-gem-daq-project/vfatqc-python-scripts/develop)|[![Code Climate](https://codeclimate.com/github/cms-gem-daq-project/vfatqc-python-scripts/badges/issue_count.svg)](https://codeclimate.com/github/cms-gem-daq-project/vfatqc-python-scripts)

# Setup (Developers Only):

This section is for developers only.  All others the DAQ machine has been setup for you and you don't need to take any action (ignore this section).


The `$SHELL` variable `$ELOG_PATH` should be defined:

```
export ELOG_PATH=/your/favorite/elog/path
```

Also a useful `$SHELL` variable is `$BUILD_HOME` which should be the directory at the start of your working directory.
Checkout the `sw_utils` repository by executing:

```
cd $BUILD_HOME
git clone https://github.com/cms-gem-daq-project/sw_utils.git
```

Then execute:

```
source sw_utils/scripts/setup_gemdaq.sh -c <cmsgemos tag> -g <gem-plotting tag> -G <gem-plotting dev version optional> -v <vfatqc tag> -V <vfatqc dev version optional>
```

Tags for each of the repo's can be found:

* [cmsgemos](https://github.com/cms-gem-daq-project/cmsgemos/tags) version X.Y.Z (`-c X.Y.Z`)
* [gemplotting](https://github.com/cms-gem-daq-project/gem-plotting-tools/tags) version X.Y.Z-dev**A** (`-g X.Y.Z -G A`)
* [vfatqc](https://github.com/cms-gem-daq-project/vfatqc-python-scripts/tags) version X.Y.Z-dev**B** (`-v X.Y.Z -V B`)

Where `X`, `Y`, `Z`, `A` and `B` are integers, and most likely will be different for each of the repositories. If a development version is not to be used (normal case), you can drop the `-G` and/or `-V` options. If this is the first time you are executing the above command, it will create a Python `virtualenv` for you and install the `cmsgemos`, `gemplotting`, and `vfatqc` packages. It may take some time to download them, so be patient and do not interrupt the installation.

> **Example**
>
> ```
> source setup_gemdaq.sh -c 0.3.1 -g 1.3.1 -G 1 -v 2.5.0 -V 1
> ```
>
> This command will install the following packages:
>
> * [cmsgemos](https://github.com/cms-gem-daq-project/cmsgemos/tags) version 0.3.1 (`-c 0.3.1`)
> * [gemplotting](https://github.com/cms-gem-daq-project/gem-plotting-tools/tags) version 1.1.3-dev1 (`-g 1.3.1 -G 1`)
> * [vfatqc](https://github.com/cms-gem-daq-project/vfatqc-python-scripts/tags) version 2.5.0-dev1 (`-v 2.5.0 -V 1`)

In addition to installing the dependencies, the script will try to guess `$DATA_PATH` based on the machine you are using.

To disable the python env execute:

```
deactivate
```

To re-enable the python env, source the script again:

```
cd $BUILD_HOME
source sw_utils/scripts/setup_gemdaq.sh
```

Note that you should always source the setup script from the same directory.

# Running Scans:

See extensive documentation written at:

[GEM DOC Twiki Page](https://twiki.cern.ch/twiki/bin/viewauth/CMS/GEMDOCDoc#How_to_Run_Scans)

# Contributing

See guidelines included in [CONTRIBUTING.md](https://github.com/cms-gem-daq-project/vfatqc-python-scripts/blob/master/.github/CONTRIBUTING.md)

[travisci-svg]: https://cdn.svgporn.com/logos/travis-ci.svg
[coveralls-svg]: https://cdn.svgporn.com/logos/coveralls.svg
[codecov-svg]: https://cdn.svgporn.com/logos/codecov.svg
[codacy-svg]: https://cdn.svgporn.com/logos/
[landscapeio-svg]: https://cdn.svgporn.com/logos/
[codeclimate-svg]: https://cdn.svgporn.com/logos/codeclimate.svg
