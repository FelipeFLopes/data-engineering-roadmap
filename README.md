# The Data Engineering Roadmap

> A self-directed path from fundamentals to senior-level data engineering — with the resources, datasets, and projects to actually practice each stage.

Most roadmaps are checklists of tools. Tools change every few years; the judgment underneath them doesn't. This one leads with fundamentals and treats each tool as a way to *practice* a concept — paired with the best learning sources, a fitting dataset, and a concrete project for every stage.

<img width="1000" height="702" alt="preview" src="https://github.com/user-attachments/assets/28d286e5-76fe-41d7-871e-dfc29337b464" />

---

## Guiding principles

- **Fundamentals over tools.** A senior engineer who understands modeling, distributed systems, and tradeoffs can pick up any new tool in weeks. The reverse isn't true.
- **Concept first, tool second.** Learn *why* before *how*. Concepts transfer between stacks; syntax doesn't.
- **Build one project and extend it.** Integration is where understanding forms. Keep a single end-to-end project and grow it through every stage.
- **Stress-test on synthetic, validate on real.** Synthetic data gives control; real data surfaces what you didn't anticipate.

---

## The roadmap

### 00 · Cross-cutting *(run throughout)*
- Build **one** end-to-end project and keep extending it.
- Read the two anchor books (below) early and revisit them.
- Resist tool-chasing — invest in principles that outlast any stack.

### 01 · Foundations
- Advanced **SQL**: window functions, CTEs, set operations, and reading query plans.
- **Python as engineering**: modules, packaging, virtual environments, tests, Git, CI/CD.
- Systems basics and **OLTP vs OLAP**: indexes, partitioning, storage formats.
- 🔨 *Build:* a tested CSV→Postgres loader, then dissect its plans with `EXPLAIN ANALYZE`.

### 02 · Data Modeling & Warehousing
- **Dimensional modeling**: star schemas, facts & dimensions, slowly changing dimensions.
- Normalization vs denormalization — and when each fits.
- Hands-on with a cloud warehouse (Snowflake / BigQuery / Databricks).
- 🔨 *Build:* model raw e-commerce data into a star schema with an SCD Type 2.

### 03 · Pipelines, Orchestration & Transformation
- **ETL vs ELT** and why the field shifted toward ELT.
- An orchestrator (Airflow / Dagster / Prefect): idempotency, backfills, late & failed data.
- **dbt** for modular, tested, version-controlled transforms.
- 🔨 *Build:* a scheduled ingest→warehouse→dbt pipeline; prove a backfill re-runs without double-counting.

### 04 · Distributed Systems & Big Data
- Distributed concepts: **shuffle**, data skew, CAP tradeoffs.
- **Spark** as the concrete vehicle.
- Open formats: Parquet, and lakehouse table formats (Iceberg / Delta / Hudi).
- 🔨 *Build:* a Spark job into Iceberg with smart partitioning; induce data skew, then fix it.

### 05 · Streaming & Real-time
- **Kafka** and the event-driven mindset.
- A stream processor (Flink / Spark Structured Streaming / Kafka Streams): windowing & watermarks.
- Judgment: **when *not* to stream**.
- 🔨 *Build:* events → Kafka → processor → sink, handling out-of-order and late events.

### 06 · Cloud, Infrastructure & Operations
- One cloud, deep (AWS / GCP / Azure).
- Infrastructure as code (**Terraform**); Docker, plus enough Kubernetes to be dangerous.
- Monitoring, alerting, security & access, and **cost management**.
- 🔨 *Build:* provision the whole stack in Terraform; do a cost teardown at 100× the data.

### 07 · Quality, Governance & the Senior Layer
- Data quality & observability: testing, anomaly detection, **lineage**.
- Governance & privacy: PII handling, GDPR/CCPA, cataloging.
- **Architecture & design**: build-vs-buy, scale, tradeoffs, cost; communication, design docs, mentoring.
- 🔨 *Build:* quality gates that fail the run on bad data; then write a design doc and get it reviewed.

---

## Main learning sources

### Anchor books (the durable core)
- **Fundamentals of Data Engineering** — Joe Reis & Matt Housley *(the lifecycle; design over tools)*
- **Designing Data-Intensive Applications**, 2nd ed. — Martin Kleppmann & Chris Riccomini *(the internals)*
- **The Data Warehouse Toolkit** — Ralph Kimball *(dimensional modeling)*
- Deep dives: *Data Pipelines with Apache Airflow*, *Spark: The Definitive Guide* / *Learning Spark*, *Kafka: The Definitive Guide*, *Streaming Systems*, *Fluent Python*

### Free courses
- [Data Engineering Zoomcamp](https://github.com/DataTalksClub/data-engineering-zoomcamp) — DataTalksClub *(end-to-end; the best free scaffold project)*
- [CMU 15-445 Database Systems](https://15445.courses.cs.cmu.edu) — Andy Pavlo *(internals, with the BusTub build-it-yourself projects)*
- [dbt Fundamentals](https://docs.getdbt.com) · [Confluent Developer](https://developer.confluent.io/courses/) · [HashiCorp Learn Terraform](https://developer.hashicorp.com/terraform/tutorials)

### Practice platforms & free tiers
- SQL drills: [DataLemur](https://datalemur.com), [StrataScratch](https://stratascratch.com), [pgexercises](https://pgexercises.com)
- Warehouses: [BigQuery sandbox](https://cloud.google.com/bigquery/docs/sandbox), [Databricks Free Edition](https://www.databricks.com/learn/free-edition)
- Local infra: [LocalStack](https://localstack.cloud), [Redpanda](https://redpanda.com), [DuckDB](https://duckdb.org)

### Datasets by use
- **Modeling / batch:** [Olist Brazilian E-Commerce](https://www.kaggle.com/datasets/olistbr/brazilian-ecommerce), [IMDb](https://developer.imdb.com/non-commercial-datasets/), [MovieLens](https://grouplens.org/datasets/movielens/), [Stack Exchange dump](https://archive.org/details/stackexchange), TPC-H/DS
- **Pipelines / CDC:** [NYC TLC trip data](https://www.nyc.gov/site/tlc/about/tlc-trip-record-data.page), [Pagila](https://github.com/devrimgunduz/pagila)
- **Streaming:** [Bluesky Jetstream](https://docs.bsky.app/docs/advanced-guides/firehose), [GDELT 2.0](https://www.gdeltproject.org), [USGS earthquakes](https://earthquake.usgs.gov/earthquakes/feed/)
- **Big data:** [Common Crawl](https://commoncrawl.org), [GH Archive](https://www.gharchive.org), [Backblaze Drive Stats](https://www.backblaze.com/cloud-storage/resources/hard-drive-test-data)

### Communities
- [dbt Community Slack](https://www.getdbt.com/community) · [Locally Optimistic](https://locallyoptimistic.com)

---

*Roadmap and tooling assembled as a personal learning system. Adapt freely.*
