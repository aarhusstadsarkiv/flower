# Frameworks: Lugui & Prefect
This document covers the task automation frameworks [Luigi](https://github.com/spotify/luigi) and [Prefect](https://github.com/PrefectHQ/prefect), by examining and comparing their features. The aim is to provide a base for framework decisions made when implementing our workflow system at Aarhus Stadsarkiv.

## Luigi
[Luigi](https://github.com/spotify/luigi) is a workflow management tool in active development by Spotify.

> The purpose of Luigi is to address all the plumbing typically associated with long-running batch processes. [1]

This framework aims to automate long-running batch processes -- these can be anything, and some examples given are e.g. Hadoop jobs, data dumping to/from databases, etc. Luigi can be used to "build pretty much any task you want" but seems to be optimised for use with Hadoop, Hive, and Pig. In addition, it has [file system abstractions for HDFS](https://luigi.readthedocs.io/en/latest/api/luigi.contrib.hdfs.html) and a web interface, where visualisation is available. Here, it is possible to search and filter tasks, as well as generating dependency graphs to show workflows. 

Luigi aims to be conceptually similar to GNU Make, and the developers argue that it is not built specifically for Hadoop:

> [...] it’s easy to extend it with other kinds of tasks. [2]

However, Spotify primarily uses Luigi for Hadoop tasks internally, and documentation would suggest that while it is possible to create any task in Luigi, the primary focal point is Hadoop and HDFS dependent tasks. 

Every workflow in Luigi is described using Python, which means that no XML files are necessary. An example workflow aggregating top artists is available on Spotify's [GitHub](https://github.com/spotify/luigi/blob/master/examples/top_artists.py). This workflow uses both HDFS, PostgreSQL, and Spark, all available from [contrib](https://luigi.readthedocs.io/en/stable/api/luigi.contrib.html) packages.

The two fundamental building blocks of Luigi are the `Task` and `Target` classes. They are both abstract and expect a few methods. Luigi comes with both `Task` and `Target` toolboxes -- in particular, it is argued that subclassing `Target` is rarely needed.

A `Target` is usually a file or file-like, for example a `LocalTarget` or a `HdfsTarget`. `Task`s consume `Target`s that were created by other (non-Luigi) tasks. A `Task` has methods that can be implemented in order to alter its behaviour, namely `run()`, `output()`, and `requires()`.

<center>![Luigi task flow](https://luigi.readthedocs.io/en/stable/_images/tasks_input_output_requires.png)

**Fig. 1**: Luigi task flow.</center>

[1]: https://luigi.readthedocs.io/en/stable/#background
[2]: https://luigi.readthedocs.io/en/stable/#philosophy