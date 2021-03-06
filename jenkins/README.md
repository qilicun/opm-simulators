# opm-simulators jenkins build scripts:

**build-opm-simulators.sh**:
This is a helper script which contains functions for building,
testing and cloning opm-simulators and its dependencies.

**build.sh**:
This script will build dependencies, then build opm-simulators and execute its tests.
It is intended for post-merge builds of the master branch.

**build-pr.sh**:
This script will build dependencies, then build opm-simulators and execute its tests.
It inspects the $ghbPrBuildComment environmental variable to obtain a pull request
to use for ert, opm-common, opm-parser, opm-material, opm-core and
opm-grid (defaults to master) and then builds $sha1 of opm-simulators.

It is intended for pre-merge builds of pull requests.

You can optionally specify a given pull request to use for ert, opm-common,
opm-parser, opm-material, opm-core and opm-grid through the trigger.
The trigger line needs to contain ert=&lt;pull request number&gt; and/or
opm-common=&lt;pull request number&gt; and/or opm-parser=&lt;pull request number&gt;
and/or opm-material=&lt;pull request number&gt;
and/or opm-core=&lt;pull request number&gt;
and/or opm-grid=&lt;pull request number&gt;
and/or opm-output=&lt;pull request number&gt;.

**run-spe.sh**:
This script will execute the SPE1, SPE3 and SPE9 cases, then compare against
OPM and Eclipse reference results. It is meant to be executed after either
of the two build scripts above.

**run-norne.sh**:
This script will execute the Norne case, and generate a document with
plots of the results. It is meant to be executed after either
of the two build scripts above.

**run-polymer.sh**:
This script will execute the simple2D polymer case, then compare against
Eclipse reference results. It is meant to be executed after either
of the two build scripts above.
