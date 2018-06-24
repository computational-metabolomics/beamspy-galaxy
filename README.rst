BEAMS for Galaxy
========================
|Build Status (Travis)| |Git| |Bioconda| |License|

Galaxy tools for Python package BEAMS: 

Galaxy
------
`Galaxy <https://galaxyproject.org>`_ is an open, web-based platform for data intensive biomedical research. Whether on the free public server or your own instance, you can perform, reproduce, and share complete analyses. 


Developers & Contributors
-------------------------

#### Create local BEAMS Conda package
`> git clone https://github.com/computational-metabolomics/beams.git`<br>
#### Add metadata.yaml and build.sh files to the project - links [meta.yaml](https://gist.github.com/CS76/f717719033985400bbd5389fda7aeec8#file-beams-meta-yaml) and [build.sh](https://gist.github.com/CS76/f717719033985400bbd5389fda7aeec8#file-beams-build-sh)
`> conda build beams`<br>
##### On mac you need to run this with write permissions
`> sudo conda build beams`<br>

This will build the conda package and add it to your local conda build directory (we will need this CONDA_BLD_PATH full path later. On mac its usually `/users/<username>/miniconda3/conda-bld`)

#### Clone BEAMS-Galaxy wrapper tool and run galaxy using palanemo
##### Clone BEAMS-Galaxy wrapper tool from github
`> git clone https://github.com/computational-metabolomics/beams-galaxy`<br>
`> git checkout development # if branch doesnt exist ~ git fetch development`<br>
`> cd <beams-galaxy_project_location>/tools/beams`<br>

##### If you don't have planemo setup

`> virtualenv .venv; . .venv/bin/activate` <br> 
`> pip install "pip>=7" # Upgrade pip if needed.`<br>
`> pip install planemo`

##### Start galaxy server - Planemo (specify the galaxy server location and the conda channels for it to recognise the beams package) <br>
`> planemo serve --galaxy_root=<galaxy_server_location> --conda_exec=<conda_executable_location> --conda_channels=<conda_packages_location>,conda-forge`<br>

conda needs other dependencise so you have to add conda-forge to the conda-channels list

Bugs
----
Please report any bugs that you find `here <https://github.com/computational-metabolomics/beams-galaxy/issues>`_.
Or fork the repository on `GitHub <https://github.com/computational-metabolomics/beams-galaxy/>`_
and create a pull request (PR). We welcome all contributions, and we
will help you to make the PR if you are new to `git`.


Changes
-------


License
-------
Released under the GNU General Public License v3.0 (see `LICENSE file <https://github.com/computational-metabolomics/beams-galaxy/blob/master/LICENSE>`_)


.. |Build Status (Travis)| image:: https://img.shields.io/travis/computational-metabolomics/beams-galaxy.svg?style=flat&maxAge=3600&label=Travis-CI
   :target: https://travis-ci.org/computational-metabolomics/beams-galaxy

.. |Git| image:: https://img.shields.io/badge/repository-GitHub-blue.svg?style=flat&maxAge=3600
   :target: https://github.com/computational-metabolomics/beams

.. |Bioconda| image:: https://img.shields.io/badge/install%20with-bioconda-brightgreen.svg?style=flat&maxAge=3600
   :target: http://bioconda.github.io/recipes/beams/README.html

.. |License| image:: https://img.shields.io/pypi/l/beams.svg?style=flat&maxAge=3600
   :target: https://www.gnu.org/licenses/gpl-3.0.html
