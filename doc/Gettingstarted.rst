Getting started
===============

Installation
------------

The Video Opinion Mining(VEM) module can be downloaded either from pip or github, with the respective commands.

* :code:`pip install VideoOpinionMining`
* :code:`git+https://github.com/Labic-ICMC-USP/VEM.git`

To use, it is also needed to install some other modules. Most of them are listed in the file requirements.txt, so running
pip install -r requirements.txt and later using the following commands should be enough to get everything you need to run.

.. code:: python3

    git clone https://github.com/m3hrdadfi/soxan
    mv soxan/*

In case you are using colab, there is an example with all the modules being installed in the link 
https://colab.research.google.com/drive/1UqzA6bDgtZWGji652a0UjT7ZtDh3Xyi5?authuser=1#scrollTo=d3QJ6iSd-o3D

First steps
-----------

After installing the module with all of it's dependencies, import the vem module.

.. code:: python3

    from VideoOpinionMining import vem

Then create an instance of the class VEMProcessor passing the path to the video you want to be analyzed as a parameter.

.. code:: python3

    video_file = "emotions.mp4"
    example = vem.VEMProcessor(video_file)

Now, with a single command you can run all the analysis

.. code:: python3
    dataframe = example.process_video()


The results can then be seen either in the dataframe returned, or in the heatmaps generated in a folder called heatmaps.

Instead of a single line command, you can also use other classes to make your analysis your own way,
more details and extra uses can be found at the documentations session.
