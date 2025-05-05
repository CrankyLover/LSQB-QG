# LSQB-QG

LSQB-QG is a benchmark designed for multi-query oriented incremental graph query, which is an extension of [LSQB](https://github.com/ldbc/lsqb) benchmark.

## Dataset

As we extend LSQB benchmark, the dataset we adopted is naturally [LDBC-SNB](https://github.com/ldbc) dataset, which contains 9 vertex label and 28 edge label by duplicating all vertices whose label is `post` and `comment` into  `message` vertex and its corresponding edges.

## Metric

As we focus on the system performance faced with concurrent multiple query graphs, we have following five metrics to evaluate system performance:
- **Elapsed Time**: The time taken to finish all queries of all updated edges.
- **P50, P90, P99 Latency**: We define the **execution time** for each query graph and each edge is the time that finishes this query minus the arrival time of the updated edge. We collect all the execution times and sort them to get P50, P90, P99 Latency.
- **Average Latency**: The average time of all execution times for each query for each edge.

## Workload

We extend the workloads of LSQB Q1-Q6, each of which is a specific pattern designed for subgraph matching without complex operator like aggregation and filter. Each of these queries is augmented with 10 semantically similar variants, all of which can be naturally interpreted through natural language descriptions, forming LSQB-QG1 to QG6. Each query group contains 11 queries intotal. Crucially,these extended queries simulate real-world scenarios: some exhibit high occurrence frequency in dynamic graphs,while some demonstrate low occurrence frequency, collectively reflecting the heterogeneous query intensity observed in practical systems.

![QG1](Figures/Q1.png)
![QG2](Figures/Q2.png)
![QG3](Figures/Q3.png)
![QG4](Figures/Q4.png)
![QG5](Figures/Q5.png)
![QG6](Figures/Q6.png)


