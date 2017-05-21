

世面上除了使用mahout做推荐系统，还有别的吗？
来自：https://www.zhihu.com/question/39121455

需要看应用场景（基于内容的推荐引擎或协同过滤）、语言（Python、Java/Scala等）以及方案完整度（完整系统或库）。

1、基于内容的推荐 Python的话，推荐考察一下gensim：gensim: Topic modelling for humans。 http://radimrehurek.com/gensim/
Java的话，可以考虑easyrec：easyrec :: open source recommendation engine http://easyrec.org
另外可以考虑类似 solr 或 Elasticsearch 的 MoreLikeThis 或直接基于 lucene  term vector 方案（例如semanticvectors  https://github.com/semanticvectors/semanticvectors）。

2、协同过滤除了采用mahout外，目前我知道很多公司推荐引擎都转向spark MLLib（底层算法可以采用mahout）或GraphLab。

有几个完整解决方案的项目推荐考察一下（prediction、seldon都是基于spark的）：
prediction: PredictionIO Open Source Machine Learning Server http://predictionio.incubator.apache.org/index.html
seldon: Seldon - Open Source Machine Learning for Enterprise https://www.seldon.io
oryx(以前叫Myrrix)：cloudera/oryx: Simple real-time large-scale machine learning infrastructure. https://github.com/cloudera/oryx