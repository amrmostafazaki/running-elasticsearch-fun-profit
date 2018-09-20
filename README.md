**WIP, covers Elasticsearch 5.5.x**

# Operating Elasticsearch
## for Fun and Profit

---

![](images/readme/image1.jpeg)


## [Fred de Villamil](https://thoughts.t37.net)

---

## [Read online](https://fdv.github.io/running-elasticsearch-fun-profit)

---

## TOC

- [Getting Started with Elasticsearch](001-getting-started.md)
  * [Elasticsearch basic concepts](001-getting-started.md/#elasticsearch-basic-concepts)
  * [What's an Elasticsearch cluster?](001-getting-started.md/#what-s-an-elasticsearch-cluster-)
  * [What's an Elasticsearch index](001-getting-started.md/#what-s-an-elasticsearch-index)
  * [Deploying your first Elasticsearch cluster](001-getting-started.md/#deploying-your-first-elasticsearch-cluster)
    + [Deploying Elasticsearch on Debian](001-getting-started.md/#deploying-elasticsearch-on-debian)
    + [Deploying Elasticsearch on RHEL / CentOS](001-getting-started.md/#deploying-elasticsearch-on-rhel---centos)
  * [First step using Elasticsearch](001-getting-started.md/#first-step-using-elasticsearch)

- [Elasticsearch and the Java Virtual Machine](002-elasticsearch-and-the-jvm.md/#elasticsearch-and-the-java-virtual-machine)
  * [Supported JVM and operating systems / distributions](002-elasticsearch-and-the-jvm.md/#supported-jvm-and-operating-systems---distributions)
    + [Operating system matrix](002-elasticsearch-and-the-jvm.md/#operating-system-matrix)
    + [Java Virtual Machine matrix](002-elasticsearch-and-the-jvm.md/#java-virtual-machine-matrix)
  * [Memory management](002-elasticsearch-and-the-jvm.md/#memory-management)
  * [Garbage collection](002-elasticsearch-and-the-jvm.md/#garbage-collection)
    + [Concurrent Mark & Sweep Garbage Collector](002-elasticsearch-and-the-jvm.md/#concurrent-mark---sweep-garbage-collector)
    + [Garbage First Garbage Collector](002-elasticsearch-and-the-jvm.md/#garbage-first-garbage-collector)

- [Designing the Perfect Elasticsearch Cluster](003-cluster-design.md/#designing-the-perfect-elasticsearch-cluster)
  * [Elasticsearch is elastic, for real](003-cluster-design.md/#elasticsearch-is-elastic--for-real)
  * [Design for failure](003-cluster-design.md/#design-for-failure)
  * [A few things you need to know about Lucene](003-cluster-design.md/#a-few-things-you-need-to-know-about-lucene)
    + [Lucene segments](003-cluster-design.md/#lucene-segments)
    + [Lucene deletes and updates](003-cluster-design.md/#lucene-deletes-and-updates)
  * [Hardware](003-cluster-design.md/#hardware)
    + [CPU](003-cluster-design.md/#cpu)
    + [Memory](003-cluster-design.md/#memory)
    + [Network](003-cluster-design.md/#network)
    + [Storage](003-cluster-design.md/#storage)
  * [Software](003-cluster-design.md/#software)
    + [The Linux (003-cluster-design.md/or FreeBSD) kernel](003-cluster-design.md/#the-linux--or-freebsd--kernel)
    + [The Java Virtual Machine](003-cluster-design.md/#the-java-virtual-machine)
    + [The filesystem](003-cluster-design.md/#the-filesystem)
  * [Designing your indices](003-cluster-design.md/#designing-your-indices)
    + [Sharding](003-cluster-design.md/#sharding)
    + [Replication](003-cluster-design.md/#replication)
  * [Optimising allocation](003-cluster-design.md/#optimising-allocation)
  * [Troubleshooting and scaling](003-cluster-design.md/#troubleshooting-and-scaling)
    + [CPU](003-cluster-design.md/#cpu-1)
    + [Memory](003-cluster-design.md/#memory-1)

- [Design for Event Logging](004-design-event-logging.md/#design-for-event-logging)
  * [Design of an event logging infrastructure cluster](004-design-event-logging.md/#design-of-an-event-logging-infrastructure-cluster)
    + [Throughput: how many events per second (004-design-event-logging.md/eps) are you going to collect?](004-design-event-logging.md/#throughput--how-many-events-per-second--eps--are-you-going-to-collect-)
    + [Retention: how long do you want to keep your data, hot and cold?](004-design-event-logging.md/#retention--how-long-do-you-want-to-keep-your-data--hot-and-cold-)
    + [Size: what is the average size of a collected event?](004-design-event-logging.md/#size--what-is-the-average-size-of-a-collected-event-)
    + [Fault tolerance: can you afford losing your indexed data?](004-design-event-logging.md/#fault-tolerance--can-you-afford-losing-your-indexed-data-)
    + [Queries](004-design-event-logging.md/#queries)
  * [Which hardware do I need?](004-design-event-logging.md/#which-hardware-do-i-need-)
  * [How to design my indices?](004-design-event-logging.md/#how-to-design-my-indices-)
  * [What about some tuning?](004-design-event-logging.md/#what-about-some-tuning-)

- [Operating Daily](005-operating-daily.md/#operating-daily)
  * [Elasticsearch most common operations](005-operating-daily.md/#elasticsearch-most-common-operations)
    + [Mass index deletion with pattern](005-operating-daily.md/#mass-index-deletion-with-pattern)
    + [Mass optimize, indexes with the most deleted docs first](005-operating-daily.md/#mass-optimize--indexes-with-the-most-deleted-docs-first)
    + [Restart a cluster using rack awareness](005-operating-daily.md/#restart-a-cluster-using-rack-awareness)
    + [Optimize your cluster restart](005-operating-daily.md/#optimize-your-cluster-restart)
    + [Remove data nodes from a cluster the safe way](005-operating-daily.md/#remove-data-nodes-from-a-cluster-the-safe-way)
  * [Get useful information about your cluster](005-operating-daily.md/#get-useful-information-about-your-cluster)
    + [Nodes information](005-operating-daily.md/#nodes-information)
    + [Monitor your search queues](005-operating-daily.md/#monitor-your-search-queues)
    + [Indices information](005-operating-daily.md/#indices-information)
    + [Shard allocation information](005-operating-daily.md/#shard-allocation-information)
    + [Recovery information](005-operating-daily.md/#recovery-information)
    + [Segments information (005-operating-daily.md/can be extremely verbose)](005-operating-daily.md/#segments-information--can-be-extremely-verbose-)
    + [Cluster stats](005-operating-daily.md/#cluster-stats)
    + [Nodes stats](005-operating-daily.md/#nodes-stats)
    + [Indice stats](005-operating-daily.md/#indice-stats)
    + [Indice mapping](005-operating-daily.md/#indice-mapping)
    + [Indice settings](005-operating-daily.md/#indice-settings)
    + [Cluster dynamic settings](005-operating-daily.md/#cluster-dynamic-settings)
    + [All the cluster settings (005-operating-daily.md/can be extremely verbose)](005-operating-daily.md/#all-the-cluster-settings--can-be-extremely-verbose-)

- [Monitoring Elasticsearch](006-monitoring-es.md/#monitoring-elasticsearch)
  * [Tools](006-monitoring-es.md/#tools)
  * [Monitoring at the host level](006-monitoring-es.md/#monitoring-at-the-host-level)
  * [Monitoring at the node level](006-monitoring-es.md/#monitoring-at-the-node-level)
  * [Monitoring at the cluster level](006-monitoring-es.md/#monitoring-at-the-cluster-level)
  * [Monitoring at the index level](006-monitoring-es.md/#monitoring-at-the-index-level)

- [Use Cases](007-use-cases.md/#use-cases)
  * [An Advanced Elasticsearch Architecture for High-volume Reindexing](007-use-cases.md/#an-advanced-elasticsearch-architecture-for-high-volume-reindexing)
    + [A glimpse at our infrastructure](007-use-cases.md/#a-glimpse-at-our-infrastructure)
    + [Using Elasticsearch for fun and profit](007-use-cases.md/#using-elasticsearch-for-fun-and-profit)
    + [Conclusion](007-use-cases.md/#conclusion)
  * [How we reindexed 36 billion documents in 5 days within the same Elasticsearch cluster](007-use-cases.md/#how-we-reindexed-36-billion-documents-in-5-days-within-the-same-elasticsearch-cluster)
    + [The "Blackhole" cluster](007-use-cases.md/#the--blackhole--cluster)
    + [Elasticsearch configuration](007-use-cases.md/#elasticsearch-configuration)
    + [Tuning the Java virtual machine](007-use-cases.md/#tuning-the-java-virtual-machine)
    + [Blackhole Initial indexing](007-use-cases.md/#blackhole-initial-indexing)
    + [Blackhole initial migration](007-use-cases.md/#blackhole-initial-migration)
    + [Blackhole reindexing](007-use-cases.md/#blackhole-reindexing)
    + [The reindexing process](007-use-cases.md/#the-reindexing-process)
    + [Logstash configuration](007-use-cases.md/#logstash-configuration)
    + [Reindexing Elasticsearch configuration](007-use-cases.md/#reindexing-elasticsearch-configuration)
    + [Introducing Yoko and Moulinette](007-use-cases.md/#introducing-yoko-and-moulinette)
    + [Reindexing in 5 days](007-use-cases.md/#reindexing-in-5-days)
    + [Conclusion](007-use-cases.md/#conclusion-1)
  * [Migrating a 130TB Cluster from Elasticsearch 2 to 5 in 20 Hours with 0 Downtime and a Rollback Strategy](007-use-cases.md/#migrating-a-130tb-cluster-from-elasticsearch-2-to-5-in-20-hours-with-0-downtime-and-a-rollback-strategy)
    + [Elasticsearch @Synthesio, November 2017](007-use-cases.md/#elasticsearch--synthesio--november-2017)
    + [The Blackhole Cluster](007-use-cases.md/#the-blackhole-cluster)
    + [Migration Strategies: Cluster restart VS Reindex API VS Logstash VS the Fun Way](007-use-cases.md/#migration-strategies--cluster-restart-vs-reindex-api-vs-logstash-vs-the-fun-way)
      - [The Cluster Restart Strategy](007-use-cases.md/#the-cluster-restart-strategy)
      - [The Reindex API Strategy](007-use-cases.md/#the-reindex-api-strategy)
      - [The Logstash Strategy](007-use-cases.md/#the-logstash-strategy)
      - [The Fun Way](007-use-cases.md/#the-fun-way)
    + [Migrating Blackhole for Real](007-use-cases.md/#migrating-blackhole-for-real)
      - [Expanding Blackhole](007-use-cases.md/#expanding-blackhole)
      - [Splitting Blackhole in 2](007-use-cases.md/#splitting-blackhole-in-2)
    + [Conclusion](007-use-cases.md/#conclusion-2)

- [Use Cases: Migrating a Cluster Across the Ocean Without Downtime](008-use-case-migrating-cluster-over-ocean.md)

---

## Styling

This is the Markdown styling used in this book. If you plan to contribute, please use it.

Chapter title:

```markdown
# This is a chapter title

```

Chapter part:

```markdown
---

## A chapter part title is preceded by an horizontal line
```

Chapter subpart:

```markdown
### A level 1 subpart
#### A level 2 subpart
```

Images:

```markdown
![An image should have an alt text](use/a/relative.link)
```

Code:

```markdown
An `inline code block` goes like this
```

Links:

```markdown
[An internal link](has/a/relative.path)
[An external link](https://has.an.absolute/path)
```

Lists

```markdown
Only one line break between a paragraph and

* An
* unordered
* list
	* with
	* subitems

or

1. An
2. Ordered
3. List
	1. With
	2. subitems
```

