# Amazon OpenSearch Service

- Vector database that applies topic-based segmentation by isolating content into per-topic indices
- Provides efficient metadata management and rich contextual information for FM interactions
- Provides the fastest query response to support advanced filtering and semantic search across millions of documents

**Reference:** https://docs.aws.amazon.com/opensearch-service/latest/developerguide/what-is.html

---

## Search Vector Algorithms

### Approximate Nearest Neighbor (ANN)

#### Hierarchical Navigable Small World (HNSW)

- Builds a multi-layer graph where vectors are connected to their nearest neighbors
- During search, traverses the graph from coarse to fine layers to find similar vectors efficiently

**Pros:**
- Fast, high-quality, simple
- Great for dynamic data

**Cons:**
- Uses lots of RAM
- Stores more memory because it stores the graph edges
- Slightly slower to build the index initially (graph construction overhead)

#### Inverted File (IVF)

- Clustering-based method that divides vectors into clusters (called buckets) using a technique like k-means
- At search time, only looks in a subset of clusters instead of the whole dataset

**Pros:**
- Lower memory usage than HNSW (no big graph data to store)
- Better for very large datasets
- Good when you don't need extremely high recall or have limited RAM
- Can trade recall for speed and memory

**Cons:**
- Requires training/clustering first
- Search quality depends on cluster quality
- Needs careful tuning of parameters like `nlist` and `nprobe`
