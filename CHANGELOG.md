# Change Log

## [HEAD](https://github.com/stellargraph/stellargraph/tree/develop)

[Full Changelog](https://github.com/stellargraph/stellargraph/compare/v0.7.1...HEAD)

**Implemented enhancements:** 
- Added directed GraphSAGE algorithm [\#479](https://github.com/stellargraph/stellargraph/pull/479)
- New demo of node classification on Twitter hateful users [\430](https://github.com/stellargraph/stellargraph/pull/430)
- New demo of graph saliency on Twitter hateful users [\#448](https://github.com/stellargraph/stellargraph/pull/448)
- Graph saliency maps for classificaiton interpretation implemented for GAT [\#435](https://github.com/stellargraph/stellargraph/pull/435)

**Refactoring:**
- Refactored Ensemble class into Ensemble and BaggingEnsemble. The former implements naive ensembles and the latter bagging ensembles. [\#459](https://github.com/stellargraph/stellargraph/pull/459)
- Changed from `keras` to use `tensorflow.keras` [\#471](https://github.com/stellargraph/stellargraph/pull/471)
- Removed `flatten_output` arguments for all models [\#447](https://github.com/stellargraph/stellargraph/pull/447)


**Fixed bugs:**
- Updated Yelp example to support new dataset version [\#442](https://github.com/stellargraph/stellargraph/pull/442)
- Fixed bug where some nodes and edges did not get a default type [\#451](https://github.com/stellargraph/stellargraph/pull/451)


## [0.7.2](https://github.com/stellargraph/stellargraph/tree/v0.7.2)

Limited Keras version to <2.2.5 and Tensorflow version to <2.0 in requirements, 
to avoid errors due to API changes in the recent versions of Keras and Tensorflow.


## [0.7.1](https://github.com/stellargraph/stellargraph/tree/v0.7.1)

[Full Changelog](https://github.com/stellargraph/stellargraph/compare/v0.7.0...v0.7.1)

**Fixed bugs:**
- Removed igraph and mplleaflet from `demos` requirements in `setup.py`. Python-igraph doesn't install on many systems and is only required for the clustering notebook. See the `README.md` in that directory for requirements and installation directions.
- Updated GCN interpretability notebook to work with new FullBatchGenerator API [\#429](https://github.com/stellargraph/stellargraph/pull/429)


## [0.7.0](https://github.com/stellargraph/stellargraph/tree/v0.7.0)

[Full Changelog](https://github.com/stellargraph/stellargraph/compare/v0.6.1...v0.7.0)

**Implemented enhancements:**
- SGC Implementation [\#361](https://github.com/stellargraph/stellargraph/pull/361) ([PantelisElinas](https://github.com/PantelisElinas))
- Updated to support Python 3.7 [\#348](https://github.com/stellargraph/stellargraph/pull/348)
- FullBatchNodeGenerator now supports a simpler interface to apply different adjacency matrix pre-processing options [\#405](https://github.com/stellargraph/stellargraph/pull/405)
- Full-batch models (GCN, GAT, and SGC) now return predictions for only those nodes provided to the generator in the same order [\#417](https://github.com/stellargraph/stellargraph/pull/417)
- GAT now supports using a sparse adjacency matrix making execution faster [\#420](https://github.com/stellargraph/stellargraph/pull/420)
- Added interpretability of GCN models and a demo of finding important edges for a node prediction [\#383](https://github.com/stellargraph/stellargraph/pull/383)
- Added a demo showing inductive classification with the PubMed dataset [\#372](https://github.com/stellargraph/stellargraph/pull/372)


**Refactoring:**
- Added build\(\) method for GraphSAGE and HinSAGE model classes [\#385](https://github.com/stellargraph/stellargraph/pull/385)
This replaces the node_model\(\) and link_model\(\) methods, which will be deprecated in future versions (deprecation warnings added).
- Changed the `FullBatchNodeGenerator` to accept simpler `method` and `transform` arguments [\#405](https://github.com/stellargraph/stellargraph/pull/405)


**Fixed bugs:**
- Removed label from features for pubmed dataset. [\#362](https://github.com/stellargraph/stellargraph/pull/362)
- Python igraph requirement fixed [\#392](https://github.com/stellargraph/stellargraph/pull/392)
- Simplified random walks to not require passing a graph [\#408](https://github.com/stellargraph/stellargraph/pull/408)


## [0.6.1](https://github.com/stellargraph/stellargraph/tree/v0.6.1) (1 Apr 2019)

**Fixed bugs:**
- a bug in passing graph adjacency matrix to the optional `func_opt` function in `FullBatchNodeGenerator` class
- a bug in `demos/node-classification/gcn/gcn-cora-example.py:144`: incorrect argument was used to pass
the optional function to the generator for GCN

**Enhancements:**
- separate treatment of `gcn` and `gat` models in `demos/ensembles/ensemble-node-classification-example.ipynb` 

## [0.6.0](https://github.com/stellargraph/stellargraph/tree/v0.6.0) (14 Mar 2019)

**Implemented new features and enhancements:**
- Graph Attention (GAT) layer and model (stack of GAT layers), with demos [\#216](https://github.com/stellargraph/stellargraph/issues/216), 
[\#315](https://github.com/stellargraph/stellargraph/pull/315)
- Unsupervised GraphSAGE [\#331](https://github.com/stellargraph/stellargraph/pull/331) with a demo [\#335](https://github.com/stellargraph/stellargraph/pull/335)
- Model Ensembles [\#343](https://github.com/stellargraph/stellargraph/pull/343)
- Community detection based on unsupervised graph representation learning [\#354](https://github.com/stellargraph/stellargraph/pull/354)
- Saliency maps and integrated gradients for model interpretability [\#345](https://github.com/stellargraph/stellargraph/pull/345)
- Shuffling of head nodes/edges in node and link generators at each epoch [\#298](https://github.com/stellargraph/stellargraph/issues/298)

**Fixed bugs:**
- a bug where seed was not passed to sampler in `GraphSAGELinkGenerator` constructor [\#337](https://github.com/stellargraph/stellargraph/pull/337)
- UniformRandomMetaPathWalk doesn't update the current node neighbors [\#340](https://github.com/stellargraph/stellargraph/issues/340)
- seed value for link mapper [\#336](https://github.com/stellargraph/stellargraph/issues/336)

## [0.5.0](https://github.com/stellargraph/stellargraph/tree/v0.5.0) (11 Feb 2019)

**Implemented new features and enhancements:**

- Added model calibration [\#326](https://github.com/stellargraph/stellargraph/pull/326)
- Added `GraphConvolution` layer, `GCN` class for a stack of `GraphConvolution` layers,
  and `FullBatchNodeGenerator` class for feeding data into `GCN` models [\#318](https://github.com/stellargraph/stellargraph/pull/318)
- Added GraphSAGE attention aggregator [\#317](https://github.com/stellargraph/stellargraph/pull/317)
- Added GraphSAGE MaxPoolAggregator and MeanPoolAggregator [\#278](https://github.com/stellargraph/stellargraph/pull/278)
- Added shuffle option to all `flow` methods for GraphSAGE and HinSAGE generators [\#328](https://github.com/stellargraph/stellargraph/pull/328)
- GraphSAGE and HinSAGE: ensure that a MLP can be created by using zero samples [\#301](https://github.com/stellargraph/stellargraph/issues/301)
- Handle isolated nodes in GraphSAGE [\#294](https://github.com/stellargraph/stellargraph/issues/294)
- Ensure isolated nodes are handled correctly by GraphSAGENodeMapper and GraphSAGELinkMapper [\#182](https://github.com/stellargraph/stellargraph/issues/182)
- EdgeSplitter: introduce a switch for keeping the reduced graph connected [\#285](https://github.com/stellargraph/stellargraph/issues/285)
- Node2vec for weighted graphs [\#241](https://github.com/stellargraph/stellargraph/issues/241)
- Fix edge types in demos [\#237](https://github.com/stellargraph/stellargraph/issues/237)
- Add docstrings to StellarGraphBase class [\#175](https://github.com/stellargraph/stellargraph/issues/175)
- Make L2-normalisation of the final embeddings in GraphSAGE and HinSAGE optional [\#115](https://github.com/stellargraph/stellargraph/issues/115)
- Check/change the GraphSAGE mapper's behaviour for isolated nodes [\#100](https://github.com/stellargraph/stellargraph/issues/100)
- Added GraphSAGE node embedding extraction and visualisation [\#290](https://github.com/stellargraph/stellargraph/pull/290)

**Fixed bugs:**

- Fixed the bug in running demos when no options given [\#271](https://github.com/stellargraph/stellargraph/issues/271)
- Fixed the bug in LinkSequence that threw an error when no link targets were given [\#273](https://github.com/stellargraph/stellargraph/pull/273)

**Refactoring:**
- Refactored link inference classes to use `edge_embedding_method` instead of `edge_feature_method` [\#327](https://github.com/stellargraph/stellargraph/pull/327)
