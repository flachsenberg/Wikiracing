# Wikiracing

The [Wikiracing game](https://en.wikipedia.org/wiki/Wikiracing), also known as The Wikipedia Game, is a game with the goal of finding a sequence of links from one article to another article as fast as possible or with as few clicks as possible. Here, I focus on the latter variant.

In this small project I want to analyze the shortest paths within Wikipedia and especially find shortest paths (sequence of links) between articles and therefore solve the Wikipedia game. This has -- of course -- already been done before (see e.g. https://www.sixdegreesofwikipedia.com/). My goal was to build an end-to-end pipeline in [Scala](https://www.scala-lang.org/) with [Apache Spark](https://spark.apache.org/) that starts with the raw Wikipedia data (the XML dump of the articles), structures this data and finally builds the graph to run shortest path algorithms on it. All steps are performed with libraries already contained in Spark (namely [spark-xml](https://github.com/databricks/spark-xml) for parsing and [spark-graphx](https://spark.apache.org/docs/latest/graphx-programming-guide.html) for the graph representation).

The project is split over two [Jupyter](https://jupyter.org/) notebooks (using Spark with the [almond](https://almond.sh/) kernel).
The first notebook [Extract.ipynb](Extract.ipynb) demonstrates how to parse the XML dump of the Wikipedia and store it in a structured way for graph building. The second notebook [Analyze.ipynb](Analyze.ipynb) shows the analysis the Wikipedia graph and how to calculate the shortest paths between two articles.
