# kadet-buildpack
Buildpack to install dependencies for the KADET project on Heroku

Add the [heroku-community/apt](https://buildpack-registry.s3.amazonaws.com/buildpacks/heroku-community/apt.tgz) buildpack to perform the installation of some dependencies.

This could be add by using the CLI

```bash
heroku buildpacks:add --index 1 heroku-community/apt
```

Next, this buildpack should be added to the project

```bash
heroku buildpacks:add --index 3 https://github.com/isccarrasco/kadet-buildpack
```

This will add the buildpack to compile and install the GOSDT library which is used on the KADET project.

In the setting section of the heroku project, add the next variables.

```
BITBUCKET_USERNAME=isccarrasco
BITBUCKET_TOKEN=***
```

The `Aptfile` is required in the source project and should contain

```
autotools-dev
automake
autoconf
g++

libboost-dev
libtbb-dev
ocl-icd-opencl-dev

graphviz
graphviz-dev
python3-dev

libmpc3
libmpfr6

libmpfr-dev
libmpc-dev
libgmp3-dev

python-gmpy2-common
python3-gmpy2
```
