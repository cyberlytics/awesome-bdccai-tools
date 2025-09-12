[//]: # (Author: Christoph P. Neumann)
[//]: # (Title: Awesome Big Data und Cloud-Computing für KI)
[//]: # (Language: de-DE)
[//]: # (Licence: CC BY 4.0)
[//]: # (Kurztitel: Werkzeuge » BDCC/AI)
[//]: # (Lemma: tools-bdccai)

# Awesome Big Data und Cloud-Computing für KI

[![Awesome](https://cdn.rawgit.com/sindresorhus/awesome/d7305f38d29fed78fa85652e3a63e154dd8e8829/media/badge.svg)](https://github.com/sindresorhus/awesome)
[![Made With Love](https://img.shields.io/badge/Made%20With-Love-pink.svg)](https://github.com/chetanraj/awesome-github-badges)
[![Donate via PayPal](https://img.shields.io/badge/Donate-PayPal-blue?logo=paypal)](https://www.paypal.com/donate/?hosted_button_id=QTDJ2JA58ZM9L)
[![Support on Ko‑fi](https://img.shields.io/badge/Donate-ko--fi-%23FF5E5B?logo=ko-fi&logoColor=white)](https://ko-fi.com/cyberlytics)
[![Buy Me A Coffee!](https://img.shields.io/badge/Donate-buymeacoffee-%23FFDD00?logo=buymeacoffee)](https://www.buymeacoffee.com/cyberpetaneuron)

Beim titelgebenden „Big Data und Cloud-Computing für KI“ handelt es sich um mein Lehrgebiet. Dies ist eine reine Tool-Sammlung. Wenn Sie kostenlose Lernmaterialen suchen, dann sind diese Teil meiner Schwesterseite [Digitaler Ressourcen-Pool](https://github.com/cyberlytics/awesome-basics). Es gibt zusätzlich weitere Schwesterseiten von mir im Kontext Informatik/KI: [Werkzeuge » Abschlussarbeiten](https://github.com/cyberlytics/awesome-thesis-tools) und [Werkzeuge » Software-Engineering](https://github.com/cyberlytics/awesome-software-engineering-tools).

Hinweise:

- Die Werkzeuge sind im Zweifelsfall für Studierende und private Nutzung, weniger für Unternehmen oder Freelancer (wegen der Lizenzbedingungen/EULA)
- Entstanden an der [OTH Amberg-Weiden](https://www.oth-aw.de/cpn), welche für ein paar Einträge entsprechend den Kontext bildet.
- Die kostenlosen Werkzeuge sind nicht immer Best-in-Class im Vergleich zu kostenpflichtigen/„(€)“ Alternativen, dennoch bleiben kostenpflichtige Angebote hier meist Out-of-Scope
- Ein Windows-zentrischer Ersteindruck durch die Chocolatey-Referenzen kann leicht täuschen, denn die kostenlosen oder quelloffenen Tools gibt es i.d.R. auch für Linux oder macOS mittels snap/flatpak/brew/etc.
- Empfehlung zu [Chocolatey](https://chocolatey.org/install): **choco feature enable -n useRememberedArgumentsForUpgrades**

**Table of Contents**

<!-- toc -->

- [Datenbanksysteme](#datenbanksysteme)
- [Datenbankwerkzeuge](#datenbankwerkzeuge)
- [Datenvisualisierung](#datenvisualisierung)
- [Data Science](#data-science)
- [Big Data](#big-data)
- [Moderne Web-Anwendungsentwicklung](#moderne-web-anwendungsentwicklung)
- [Mobile Apps](#mobile-apps)
- [Semantic Web / Knowledge Representation](#semantic-web--knowledge-representation)
- [Verteilte Systeme](#verteilte-systeme)
- [Cloud-Computing](#cloud-computing)
- [DevOps](#devops)
- [Operations Research (OR) / Optimization](#operations-research-or--optimization)
- [ML / AI](#ml--ai)
- [Low-Code / No-Code](#low-code--no-code)
- [Edge / Fog / IoT](#edge--fog--iot)
- [dApps](#dapps)
- [Security](#security)
  - [Professional Security](#professional-security)
  - [LLM-Security](#llm-security)
  - [Personal Security](#personal-security)
- [Privacy](#privacy)
  - [Professional Privacy](#professional-privacy)
  - [Personal Privacy](#personal-privacy)
- [Appendix: More Free Student Stuff](#appendix-more-free-student-stuff)
- [Footer](#footer)
  - [Future Work](#future-work)
  - [Contribute](#contribute)
  - [Backers](#backers)
  - [License](#license)

<!-- tocstop -->

## Datenbanksysteme

- **[EXASOL](https://www.exasol.com/product-overview/)**: In-Memory-basiertes MPP-fähiges ACID-konformes RDBMS für analytische Workloads
	- Dialekt: Standardkonformes ISO SQL + hochgradig Oracle-kompatibel
	- Als [Community Edition](https://www.exasol.com/en/download/community-edition-download/) kostenlos als VM Image für bis zu 200 GB Rohdaten, mit Default Port 8563
	- Als [Docker Container](https://github.com/exasol/docker-db), allerdings derzeit nur unter Linux
	- Exasol ist der langjährige Testsieger im [TPC-H Benchmark](https://www.tpc.org/tpch/results/tpch_last_ten_results5.asp) für DWH-Systeme (suite of business oriented ad-hoc decision support queries and concurrent data modifications)
- **[DuckDB](https://duckdb.org/)**: “SQLite for analytics“ / In-Memory-basiertes In-Process-fähiges ACID-konformes RDBMS für analytische Workloads
	- Dialekt: PostgreSQL
	- Technisch nicht auf Augenhöhe mit einer Single-Node EXASOL Community Edition
	- Sweet Spot: [Embeddable](https://duckdb.org/why_duckdb) in analytische Anwendungen („runs anywhere“), insb. für [Python und Pandas](https://motherduck.com/blog/six-reasons-duckdb-slaps/)
- Volltextsuche
	- **[Elastic](https://www.elastic.co/)** bzw. ELK-Stack \[via **[Docker](https://www.elastic.co/guide/en/elasticsearch/reference/current/docker.html)** oder **choco install elasticsearch** sowie **choco install kibana**\]: im Kern eine verteilte Volltext-Suchmaschine, basierend auf Lucene; aber auch als skalierbares NoSQL-System verwendbar
	- **[typesense](https://typesense.org)**: Typo-tolerante Suchmaschine, optimiert für niedrige Latenzzeiten und hohe Suchleistung
- Klassische Open-Source RDBMS:
	- **[MySQL](https://www.mysql.com/)** \[**choco install mysql** sowie **choco install mysql.workbench**\], mit Default Port 3306
	- **[MariaDB](https://mariadb.org/)** \[**docker run -d -p 3306:3306 -e MYSQL_ROOT_PASSWORD=geheim mariadb:latest**\] sowie [Maria **Galera**](https://mariadb.com/kb/en/galera-cluster/) = Multi-Master-Cluster
	- **[PostgreSQL](https://www.postgresql.org/)** \[**choco install postgresql --params '"/Password:geheim /Port:5432"' --params-global**\]
	- **[SQLite](https://www.sqlite.org/)** \[**choco install sqlite** sowie **choco install sqlite.shell** und ggf. **choco install sqlite-studio.portable**\]
- Klassische kommerzielle RDBMS:
	- [**Oracle** Database Free](https://www.oracle.com/database/technologies/appdev/xe.html) (formerly: eXpress Edition) \[**docker run -d -p 1521:1521 -e ORACLE_PASSWORD=geheim gvenzl/oracle-free**\]
		- Weitere [Oracle Docker Images](https://github.com/oracle/docker-images)
	- [Microsoft **SQL Server** Express](https://www.microsoft.com/en-us/sql-server/sql-server-downloads) \[**choco install sql-server-express** sowie **choco install sql-server-management-studio**\] ggf. noch statischen Port 1433 konfigurieren
	- [IBM **Db2** Community Edition](https://www.ibm.com/de-de/products/db2-database/developers) \[via [Docker](https://hub.docker.com/r/ibmcom/db2)\]
- Datenbanksysteme für PWAs: **[CouchDB](https://couchdb.apache.org/)** (online) + **[PouchDB](https://pouchdb.com/)** (offline+sync)
- **[BaseX](https://basex.org/download/)**: XML DBMS und XQuery Engine
- Graph-Datenbanksysteme
	- **[Neo4j](https://neo4j.com/download-neo4j-now/)** \[**choco install neo4j-community**\]: [Cypher](https://neo4j.com/developer/cypher/) Anfragesprache (Further Reading: [Neo4j GraphAcademy](https://neo4j.com/graphacademy/online-training/))
	- **[ArangoDB](https://www.arangodb.com/)** \[[via Docker](https://www.arangodb.com/docs/3.9/deployment-single-instance-manual-start.html#manual-start-in-docker)\]: [AQL](https://www.arangodb.com/docs/stable/aql/) Anfragesprache (Further Reading: [ArangoDB University](https://university.arangodb.com/))
- RDF Databases / SPARQL-fähige Triple Stores? siehe unten im Abschnitt „[Moderne Web-Anwendungsentwicklung](#moderne-web-anwendungsentwicklung)“ zu Semantic Web / Linked Open Data
- DBaaS:
	- **[bit.io](https://bit.io/)**: kostenloses 10GB Postgres Datenbanksystem in der Cloud (Datensätze für Postgres bspw. von [morenoh149](https://github.com/morenoh149/postgresDBSamples/tree/master/chinook-1.4))
	- [**OCI Cloud** Free Tier](https://www.oracle.com/cloud/free/): bis zu zwei kostenlose Oracle DB-Instanzen, je 20GB, verschieden Typen, bspw. Exadata oder NoSQL
	- **[dbfiddle](https://dbfiddle.uk/)**: Browser-basierter SQL-Datenbank-Playground (diverse Datenbanksysteme)
	- **[MongoDB Atlas](https://www.mongodb.com/pricing)**: Cloud-Variante des klassischen NoSQL-Systems (The „M“ in MEAN and MERN) – kostenlos für 512MB
	- **[Couchbase Capella](https://www.couchbase.com/products/capella/)**
	- **[neo4j AuraDB](https://neo4j.com/product/auradb/)**
	- [**CockroachDB** SQL-Playground](https://www.cockroachlabs.com/docs/tutorials/sql-playground.html): Cloud-Variante des NewSQL-Datenbanksystems (s. unten)
- RDBMS Research Prototypes:
	- **[LeanStore](https://dbis1.GitHub.io/)**: high-performance OLTP storage engine optimized for many-core CPUs and NVMe SSDs (Prof. Viktor Leis)
	- **[HyPer](https://hyper-db.de)**: main-memory-based relational DBMS for mixed OLTP and OLAP workloads (aquired by Tableau)
	- **[Umbra](https://umbra-db.com/#features)**: a disk-based system with in-memory performance
	- **[Peloton](https://pelotondb.io/)**: self-driving main-memory-based relational DBMS for mixed OLTP and OLAP workloads

## Datenbankwerkzeuge

- **[Beekeeper](https://www.beekeeperstudio.io/)** \[**choco install beekeeper-studio.portable**\]: Advanced SQL Editor
	- Alternativen: [**DBeaver** Community Edition](https://dbeaver.io/) \[**choco install dbeaver**\] mit [Open-Source Hintergrund](https://github.com/dbeaver/dbeaver), **[DbVisualizer](https://www.dbvis.com/pricing/)** \[**choco install db-visualizer**\], etc.
- (€:) **[DataGrip](https://www.jetbrains.com/datagrip/)**, kostenlos über die [Free Educational Licenses](https://www.jetbrains.com/community/education/#students) für Studierende
- **[DbGate](https://dbgate.org)** \[**choco install dbgate.portable**\]: Open-Source Cross-Plattform SQL Editor, inkl. NoSQL-Unterstützung und starkem JSON-Viewer
- **[DbSchema](https://dbschema.com/)** [Community Edition](https://dbschema.com/): SQL Editor, Schema Reverse Engineering and Visualization
	- (Pro Version: Schema Management and Database Change Management)
- **[SchemaCrawler](https://www.schemacrawler.com/)** \[**choco install schemacrawler**\]: Open-Source Database Schema Discovery and Comprehension Tool; generates Schema Diagrams
- **[SchemaSpy](https://schemaspy.org/)**: Schema Reverse Engineering and Visualization for Schema Documentation
- **[Flyway](https://flywaydb.org/)** [Community Edition](https://flywaydb.org/): Database Change Management
	- Alternative: **[Liquibase](https://www.liquibase.org/)** \[**choco install liquibase**\] sowie **[Squitch](https://sqitch.org/)**
- **[Navicat Data Modeler](https://www.navicat.com/en/products/navicat-data-modeler)**, kostenlos als [Navicat Data Modeler Essentials 3](https://www.navicat.com/en/download/navicat-data-modeler-essentials);
	- Navicat unterscheidet sehr schön konzeptionelle, logische und physische Modellierung
	- Leider ist auch bei Navicat für die konzeptionelle Modellierung die Entity/Relationship-Umsetzung unbrauchbar
- Data Engineering / Data Integration
	- «Open Source / Desktop» **[Talend Open Studio](https://www.talend.com/lp/open-studio-for-data-integration/)**
	- «Open Source / Web» **[Airbyte](https://docs.airbyte.com/quickstart/deploy-airbyte/)**
	- «Geheimtipp(€€€)» **[Ab Initio](https://www.abinitio.com/)** (obwohl es nicht im Gartner [Magic Quadrant for Data Integration Tools](https://pages.matillion.com/rs/992-UIW-731/images/Gartner-MQ-2022-Quadrant.png) auftaucht)
	- Open-Source-Alternativen: vgl. [Artikel von Atlan](https://atlan.com/open-source-etl-tools/) (Kandidaten: Singer, dbt, PipelineWise, Meltano, Pentaho)
- Data Quality
	- «Open Source» **[Talend Open Studio for Data Quality](https://sourceforge.net/projects/talendprofiler/)** | [**Soda** Core](https://github.com/sodadata/soda-core)
	- «Empfehlung(€€€)» **[Collibra](https://www.collibra.com/)** (im Visionary-Quadrant des Gartner [Magic Quadrant for Data Quality Solutions](https://www.datactics.com/wp-content/uploads/2022/11/figure1.png) 2022)
- Data Governance / Metadata Management (früher: [Data Catalog](https://atlan.com/what-is-a-data-catalog/))
	- «Open Source» vgl. [Artikel von Atlan](https://atlan.com/open-source-data-catalog-tools/) (Kandidaten: Apache Atlas, Amundsen Lyft, LinkedIn DataHub, Netflix Metacat, OpenMetadata)
	- «Empfehlung(€€€)» **[Collibra](https://www.collibra.com/)** (im Leader-Quadrant des Gartner [Magic Quadrant for Metadata Management Solutions](https://1.bp.blogspot.com/-kzKwIT9505s/W3LU5bmJl-I/AAAAAAAAD0o/YIfEOTIEo18MolX569Dw6U7RDof4JVlawCLcBGAs/s1600/GartenerMetadata.png) 2018)
	- Forschungsdatenmanagement? vgl. Schwesterseite [Dozenten-Werkzeuge](https://www.oth-aw.de/neumann/tools-faculty/#forschungsdatenmanagement)
- Data Lineage
	- Gudusoft **[SQLFlow](https://sqlflow.gudusoft.com/#/)**: SQL Visualisierung ein oder mehrerer SQL Befehle, kostenlos, in der Cloud
	- «Open Source» vgl. [Artikel von Atlan](https://atlan.com/open-source-data-lineage-tools/) (Kandidaten: Tokern, Egeria, Pachyderm, OpenLineage, TrueDat)
	- Nennenswert: Wird auch von **[Collibra](https://www.collibra.com/)** abgedeckt (Data Lineage fällt aus Sicht von Gartner in den [Magic Quadrant for Data Quality Solutions](https://www.datactics.com/wp-content/uploads/2022/11/figure1.png), Collibra ist ggf. hier nicht Best-in-Class aber wegen Collibras Überlappung mit DQ und MDM attraktiv)
- **[CleverCSV](https://github.com/alan-turing-institute/CleverCSV)**: Generiere Python-Code für CSV-Imports, zzgl. Bibliotheksfunktionen für Data Cleaning
- **[WinPure Clean & Match](https://winpure.com/products/compare-clean-match/)**: Data Cleaning / Data Quality; kostenlose Community Lizenz
	- Alternativen: Open-Source **[OpenRefine](https://openrefine.org/)** \[**choco install openrefine**\] ehem. Google |\
		[Alteryx **Trifacta**](https://www.trifacta.com/): Ebenfalls Data Cleaning / Data Quality; mit universitärem Hintergrund aber heute kommerziell; es gibt allerdings eine [Educational License](https://www.trifacta.com/edu-license/)
- **[DataVault Builder](https://datavault-builder.com/)** als [Educational Edition](https://datavault-builder.com/pricing/)
- **[RelaX](https://dbis-uibk.GitHub.io/relax/)**: calculates any relational algebra statement like ( σ a > 42 ( A ) ) ⋈ ( π a,b ( B ) ) on a set of relations
- Functional Dependencies:
	- **[Functional Dependency Calculator](http://www.schirmeier.com/horst/scripts/functional-dependencies.php)**
	- **[Talend Open Studio for Data Quality](https://sourceforge.net/projects/talendprofiler/)**: [Detecting anomalies in columns (Functional Dependency Analysis)](https://help.talend.com/r/en-US/8.0/studio-user-guide-open-studio-for-data-quality/detecting-anomalies-in-columns-functional-dependency-analysis)
- Weiterführende Quellen: [Awesome Database Tools](https://github.com/mgramin/awesome-db-tools) | [Awesome Open-Source Data Engineering](https://github.com/gunnarmorling/awesome-opensource-data-engineering) (ähnliche [Liste mit kommerziellen Optionen](https://github.com/igorbarinov/awesome-data-engineering))

## Datenvisualisierung

Datenexploration und Visualisierung:

- BI Tools / Dashboarding-Werkzeuge
	- **[Tableau](https://www.tableau.com/products/desktop)** \[**choco install tableau-desktop**\]
		- Tableau ist [kostenlos für Studierende](https://www.tableau.com/academic/students)
	- Microsoft **[PowerBI](https://app.powerbi.com)** (für Studierende ggf. Teil von kostenlosen Software-Bundles)
	- Google [Looker](https://cloud.google.com/looker)
	- [Qlik Sense](https://www.qlik.com/products/qlik-sense)
		- Qlik Sense ist [kostenlos für Studierende](https://www.qlik.com/company/academic-program) (Verifikation per proxi.id)
	- [Eclipse **BIRT**](https://download.eclipse.org/birt/) \[**choco install eclipse** zzgl. BIRT-Installation\]
	- [**KNOWAGE** Community Edition](https://www.knowage-suite.com/site/licensing/community-edition/) (formerly: SpagoBI)
	- **[DataWrapper](https://www.datawrapper.de/)**
	- **[Exploratory Desktop](https://www.exploratory.io/)**
		- Exploratory ist [kostenlos für Studierende](https://www.exploratory.io/pricing)
	- **[Metabase](https://www.metabase.com/)** als [Open Source Edition](https://www.metabase.com/start/oss/) \[**docker run -d -p 3000:3000 --name metabase metabase/metabase**\]
	- **[Panel](https://panel.holoviz.org/)** (graphisches Dashboarding-Werkzeug basierend auf HoloViz, s. unten)
	- **[Seal Report](https://github.com/ariacom/Seal-Report)**
	- [Zoho Analytics](https://www.zoho.com/analytics/)
- Bibliotheken
	- **[HoloViz](https://holoviz.org/)**: Bibliotheken zur Datenvisualisierung in Python
	- [Plotly Dash](https://plotly.com/dash/) als [Dash Open Source](https://dash.plotly.com/)
- Weiterführende Quellen:
	- BI-Tools: [Awesome Business Intelligence](https://github.com/thenaturalist/awesome-business-intelligence)
	- Bibliotheken: [Awesome DataViz](https://github.com/hal9ai/awesome-dataviz) | [Awesome Data Visualization](https://github.com/alpers/awesome-data-visualization)

## Data Science

- **[KNIME](https://www.knime.com/)** \[**choco install knime**\]
- **[RapidMiner](https://rapidminer.com/platform/)** for Academics mit [Educational License Program](https://rapidminer.com/platform/educational/) \[**choco install rapidminer**\]
	- (im Kern ist [RapidMiner Studio auch Open Source](https://github.com/rapidminer/rapidminer-studio))
- Interactive Computing / Notebooks
	- [**Juyter** Docker Stacks](https://jupyter-docker-stacks.readthedocs.io/en/latest/index.html) \[**docker run -p 8888:8888 jupyter/scipy-notebook**\]
		- **[binder](https://mybinder.org/)**: das Cloud-Bindeglied zwischen Jupyter und Ihren git-gehosteten Notebook-Dateien (Obacht: Wenn in den USA die Leute aufstehen, dann geht der globally-shared Infrastruktur von binder ggf. die Puste aus, daher ggf. nicht ausreichend zuverlässig für Lehrveranstaltungen oder Konferenz-Demos)
	- **[CoCalc](https://cocalc.com/)**: Collaborative Computation and Data Science
		- Unterstützt auch **[SageMath](https://www.sagemath.org/)** Worksheets, SageMath ist eine Open Source Alternative zu Matlab und Mathematica
	- **[SQL Notebook](https://sqlnotebook.com/)** \[**choco install sqlnotebook**\]
		- Alternative: **[Tad](https://www.tadviewer.com/)** \[**choco install tad**\]
	- [Google **Collab**](https://colab.research.google.com/) Notebook
- Visualisierungen:
	- [VersaTiles](https://versatiles.org/): Geodaten
	- Weiterführende Referenzen: [Awesome Dataviz](https://github.com/hal9ai/awesome-dataviz), [Awesome Geospatial](https://github.com/sacridini/Awesome-Geospatial), [Awesome Big Data » Data Visualization](https://github.com/oxnr/awesome-bigdata?tab=readme-ov-file#data-visualization)
- Datensets
	- Genartive KI / LLM: **[Laion Open Dataset](https://laion.ai/)**,**[OpenWebText](https://skylion007.github.io/OpenWebTextCorpus/)**, **[CommonCrawl](https://commoncrawl.org/)** und **[The Pile](https://pile.eleuther.ai/)**
	- Sammlungen: [**kaggle** Datasets](https://www.kaggle.com/datasets) ⭐ | **[Open Data on AWS](https://registry.opendata.aws/)** | **[Awesome Public Datasets](https://github.com/awesomedata/awesome-public-datasets)** ⭐
	- Kuratiert: [**100 interesting data sets** for statistics](https://rs.io/100-interesting-data-sets-for-statistics/) | [**Springboard**: free public data sets for your data science project](https://www.springboard.com/blog/data-science/free-public-data-sets-data-science-project/)
	- Semantic Web: **[DBpedia](https://wiki.dbpedia.org/develop)**
	- Ökonomie: **[Worldbank Open Data](https://data.worldbank.org/)**
	- Zeichnungen: [**Quick Draw!** The Data](https://quickdraw.withgoogle.com/data) (Montagsmaler-ähnlich; bspw. [Ameisen](https://quickdraw.withgoogle.com/data/ant))
	- COVID: **[CORD-19](https://www.kaggle.com/allen-institute-for-ai/CORD-19-research-challenge)**, [**EDC** Datensets](https://www.ecdc.europa.eu/en/covid-19/data)
	- Programmierung: **[The Stack](https://huggingface.co/datasets/bigcode/the-stack)** | für SQL: [vgl. NSQL-Listing](https://www.numbersstation.ai/post/introducing-nsql-open-source-sql-copilot-foundation-models)
- **[Rucio](https://rucio.cern.ch/)** \[via Docker\]: Scientific Data Management
- Weiterführende Quellen: [Awesome Data Science](https://github.com/academic/awesome-datascience) | [Awesome Data Science Software in Python](https://project-awesome.org/krzjoa/awesome-python-data-science)

## Big Data

- [Big Data Landscape](https://mattturck.com/bigdata2017/) (bis 2017) von Matt Turck sowie seine [MAD Landscapes](https://mattturck.com/category/big-data/) (= Machine Learning, AI & Data) 
- Archetype **Petabyte**-scale Frameworks (insb. analytische Workloads): [Apache **Hadoop**](https://hadoop.apache.org/) (Two-Phase MapReduce, batch mode, „active Archive“), inkl. dessen Erweiterung durch [Apache **Spark**](https://spark.apache.org/) (RDD, iterative algorithms, In-Memory)
	- Playground: Pre-Built VM [Oracle Big Data Lite Virtual Machine](https://www.oracle.com/downloads/developer-vm/community-downloads.html) (BDLite) and [Samples](https://github.com/oracle/big-data-lite)
	- Hadoop on Windows:
		- Docker? [HowTo: Big Data Europe](https://cjlise.github.io/hadoop-spark/Setup-Hadoop-Cluster/)
		- Installation? [HowTo: Hadoop 3.x](https://github.com/ruslanmv/How-to-install-Hadoop-on-Windows)
	- Spark on Windows:
		- Terminological overview: Scala-variant = Spark-shell / Python-variant = PySpark
		- Docker? [Spark Shell](https://hub.docker.com/r/apache/spark/) \[`docker run -it apache/spark /opt/spark/bin/spark-shell`\]
			- On Windows with a scala file and data in a local directory:
				```batchfile
				@echo off
				cd /d "%~dp0"
				docker run -it -v %CD%:/app -v %CD%:/data -p 4040:4040 --name sparkshell apache/spark:scala bash -c "ls -al /data; /opt/spark/bin/spark-shell -i /app/%~n0.scala"
				pause
				```
			- [HowTo: Spark as part of jupyter](https://towardsdatascience.com/apache-spark-on-windows-a-docker-approach-4dd05d8a7147) \[docker run -p 8888:8888 -e JUPYTER_ENABLE_LAB=yes --name pyspark jupyter/pyspark-notebook\] or [HowTo: Spark Cluster](https://medium.com/@MarinAgli1/setting-up-a-spark-standalone-cluster-on-docker-in-layman-terms-8cbdc9fdd14b)
		- Installation? [HowTo: Spark on Hadoop 3.x](https://medium.com/@ansabiqbal/setting-up-apache-spark-pyspark-on-windows-11-machine-e16b7382624a) or [HowTo: Spark on Hadoop 2.x](https://www.knowledgehut.com/blog/big-data/how-to-install-apache-spark-on-windows)
- **NoSQL:** DB-Engines Rankings [Key/Value-Stores](https://db-engines.com/de/ranking/key-value+store) | [Document-Stores](https://db-engines.com/de/ranking/document+store) | [Wide-Column-Stores](https://db-engines.com/de/ranking/wide+column+store)
	- **MongoDB** \[choco install mongodb.install \] plus IDE/GUI: [Compass](https://www.mongodb.com/products/tools/compass) \[choco install mongodb-compass\] or [Studio 3T](https://studio3t.com/download/) \[choco install studio3t\]
	- **Cassandra**: unter Windows per DataStax Desktop! (benötigt WSL2 und Docker Deskop)
				1. Installer: https://downloads.datastax.com » Reiter "Tools" » Liste "DataStax Desktop" » Package "Windows" » Button "Download"! (ggf. Shortcut-URL: https://downloads.datastax.com/#desktop)
		2. Installieren Sie DataStax Desktop.
		3. Starten Sie DataStax Desktop und installieren Sie Cassandra.
		4. Nachdem in DataStax Desktop alle vier Installationsschritte grün sind:
			- Klicken Sie in DataStax Desktop oben bei den Symbolen auf das "Stacks" Symbol.
			- Klicken Sie dann unten bei	"Apache Cassandra" auf den Pfeil nach unten "Show hidden layers", so dass Sie einen Bereich "CQL Shell" sehen, mit einem Button "Launch CQL Shell". Klicken Sie diesen!
		- Alternative: [ScyllaDB](https://www.scylladb.com/) a drop-in replacement for Cassandra, providing the same CQL interface and drivers \[docker run --name scylla -d scylladb/scylla\]
	- **Redis** \[choco install redis\]
	- **Couchbase** Server: [Community Edition (CE)](https://developer.couchbase.com/tutorial-getting-started-with-couchbase-ce) \[docker run -itd --name couchbase-server -p 8091-8094:8091-8094 -p 11210:11210 couchbase:community\]
	- **neo4j**: [Desktop](https://neo4j.com/deployment-center/?desktop-gdb) or [Graph Database Self-Managed » Community](https://neo4j.com/deployment-center/?gdb-selfmanaged)
- Scalable **OLAP: [EXASOL](https://www.exasol.com/product-overview/)** (→ s.oben!): Closed-Source MPP-fähiges und In-Memory-basiertes ACID-konformes RDBMS (MPP-DBMS; OLAP workloads); für analytische Anwendungen wie BI/DWH, DSS und Data Science; sehr hohe SQL-Standard-Kompatibilität und hohe Oracle-SQL-Dialekt-Kompatibilität
	- Alternative: (€) **[Snowflake](https://www.snowflake.com/pricing/)** als Cloud-native DWaaS
- Scalable **OLTP: [CockroachDB](https://www.cockroachlabs.com/product/)** \[via [Docker](https://www.cockroachlabs.com/docs/v22.1/install-cockroachdb-windows)\]: Open-Source NewSQL; **PostgreSQL**-compatible; built on a transactional and strongly-consistent key-value store
	- Alternative: **[YugabyteDB](https://www.yugabyte.com/)** \[via [Docker](https://docs.yugabyte.com/preview/quick-start/docker/)\]: Open-source NewSQL; **PostgreSQL**-compatible
- Scalable **HTAP:** [PingCAP **TiDB**](https://github.com/pingcap/tidb): \[via [Quick Start Guide](https://hub.docker.com/r/pingcap/tidb)\]: Open-source NewSQL (OLTP/HTAP workloads); **MySQL**-compatible; built on a transactional key-value store
- λ/Lambda-Architektur (Nathan Marz) „**separate** batch vs. speed layer“: klassisch bspw. basierend auf [Apache **Hadoop**](https://hadoop.apache.org/) + [Apache **Storm**](https://storm.apache.org/)
	- vgl. auch [Twitter/𝕏 **Summingbird**](https://github.com/twitter/summingbird)
- ϰ/Kappa-Architektur (Jay Kreps) „**unified** batch-&speed-layer“: bspw. basierend auf [Apache **Flink**](https://flink.apache.org/)
	- (Flink hat seinen Urspruch in [Stratosphere](http://stratosphere.eu), einem Projekt dreier deutscher Hochschulen, u.a. von [Prof. Dr. Volker Markl](https://www.bifold.berlin/people/prof-dr-volker-markl.html))
	- Kappa-Architekturen können auch basieren auf [**Kafka** Streams](https://kafka.apache.org/documentation/streams/), Spark Streaming, Kinesis Data Streams, etc. pp.
- [Apache **Druid**](https://druid.apache.org/): Time Series Database; real-time (i.e., sub-second) analytics database, with separation of ingest compute and query compute
	- Alternative: [**InfluxDB** Open Source](https://portal.influxdata.com/downloads/): Time Series Database; developed for operations monitoring and focuses on real-time (i.e., sub-second) analytics of IoT Data; core component of the [TICK stack](https://www.influxdata.com/time-series-platform/)
- SIEM:
	- [**Splunk** Free](https://docs.splunk.com/Documentation/Splunk/latest/Admin/MoreaboutSplunkFree) (500MB pro Tag)
	- Cloud: **[Matano](https://www.matano.dev/)**, eine „open source security lake platform for AWS“
- Log-Analysen:
	- **[Elastic](https://www.elastic.co/)** bzw. ELK-Stack, insbesondere L = **[Logstash](https://www.elastic.co/logstash/)** \[u.a. via **[Docker](https://www.elastic.co/guide/en/elasticsearch/reference/current/docker.html)**\], Elastic ist im Kern eine verteilte Volltext-Suchmaschine, basierend auf Lucene
	- Cloud: **[logz.io](https://logz.io/pricing/)** (1GB pro Tag)
- GPU-Computing:
	- **[OpenCL](https://www.khronos.org/opencl/)** (Open Computing Language): Standardschnittstelle für paralleles Rechnen mit aufgaben- und/oder datenbasierter Parallelität, als HW-Plattform-Abstraktion für CPUs, GPUs, DSPs, FGPAs, usw.
		- Java: [JOCL](http://www.jocl.org/) = Java bindings for OpenCL | [Lightweight Java Game Library](https://www.lwjgl.org/) (LWJGL) = Java-Abstraktion für OpenGL, OpenAL, OpenCL und OpenVR
- Weiterführende Quellen: [Awesome Big Data #1](https://github.com/newTendermint/awesome-bigdata) | [Hadoop Ecosystem Table](https://hadoopecosystemtable.GitHub.io/) | [Awesome Big Data #2](https://github.com/oxnr/awesome-bigdata)

## Moderne Web-Anwendungsentwicklung

- **[BuildWith](https://builtwith.com/)**: Find out what websites are built with
- **Watch-Lists** (Projects): **[OpenJS](https://openjsf.org/projects/)**, **[CNCF](https://www.cncf.io/projects/)**, [State of JS](https://stateofjs.com/), [DB-Engines](https://db-engines.com/en/ranking), [ThoughtWorks **Technology Radar**](https://www.thoughtworks.com/radar)
- **Starter-Kits/Blueprints** (Frontend/Backend/Full-Stack):
	- Java-zentrisch: **[JHipster](https://start.jhipster.tech/)** ([TechStack-Docu](https://www.jhipster.tech/tech-stack/)) | [**Spring** Initializr](https://start.spring.io/)
	- Any Lang: [CodebaseShow » **RealWorld**](https://codebase.show/projects/realworld) ⭐ \[[GitHub-Repo](https://github.com/gothinkster/realworld)\] | [**JHipster** Non-Java-Blueprints](https://www.jhipster.tech/modules/official-blueprints/)
	- JS-zentrisch: [**Meteor**.js](https://www.meteor.com), **[refine](https://github.com/refinedev/refine)**, [SaaS Starterkit](https://github.com/Saas-Starter-Kit/Saas-Kit-prisma) (Next.js)
	- Docker-zentrisch: [Awesome-LocalStack](https://www.awesome-testing.com/2025/03/comprehensive-local-testing-stack) ([github](https://github.com/slawekradzyminski/awesome-localstack))
- **[Svelte](https://svelte.dev)** (Client-side) sowie **[SvelteKit](https://kit.svelte.dev)** (Server-side): Newcommer Web-Framework und Alternative zu Angular/React/Vue
- **[TS Play](https://www.typescriptlang.org/play)**: Online TypeScript Editor/Playground
- Die [üblichen Verdächtigen](https://insights.stackoverflow.com/survey/2021#section-most-loved-dreaded-and-wanted-web-frameworks) (Client-side):
	- JS/TS: **[Svelte](https://svelte.dev)** | **[Vue](https://vuejs.org/)** | **[Preact](https://preactjs.com/)**| [React](https://reactjs.org/) | [Aurelia 2](https://github.com/aurelia/aurelia) | [Angular](https://angular.io/)
	- Java: [Vaadin](https://vaadin.com/)
	- C#: [ASP.NET Core](https://docs.microsoft.com/en-us/aspnet/core/blazor/?view=aspnetcore-6.0) [Blazor](https://docs.microsoft.com/en-us/aspnet/core/blazor/?view=aspnetcore-6.0)[Py](https://pyscript.net)[: PyScript](https://pyscript.net)
	- Erlang/Exlixir: [Phoenix](https://phoenixframework.org/)
- Micro Frontends: Webartikel [11 **Micro Frontends Frameworks** You Should Know](https://itnext.io/11-micro-frontends-frameworks-you-should-know-b66913b9cd20)
- Die [üblichen Verdächtigen](https://www.techempower.com/benchmarks/) (Server-side):
	- Java: **[Micronaut](https://micronaut.io/)** \[CLI: choco install micronaut\] | [Spring Boot](https://start.spring.io/) \[choco install spring-boot-cli\] insbesondere mit [Spring WebFlux](https://docs.spring.io/spring-framework/docs/current/reference/html/web-reactive.html) + [Netty](https://netty.io/)
	- C#: **[ASP.NET Core](https://github.com/dotnet/aspnetcore)** \[choco install dotnet-aspnetruntime\]
	- JS/TS: **[SvelteKit](https://kit.svelte.dev)** sowie [Next.js](https://nextjs.org/) | **[Nuxt](https://nuxtjs.org/)** | [Marko](https://markojs.com/)/Fluurt sowie [Node.js](https://nodejs.org/) \[choco install Node.js\] + Express
	- Py: **[FastAPI](https://insights.stackoverflow.com/survey/2021#section-most-loved-dreaded-and-wanted-web-frameworks)** | [Flask](https://flask.palletsprojects.com/)
	- Ruby: [RoR](https://rubyonrails.org/)
	- PHP: [Laravel](https://laravel.com/)
- Spezial-Kontext SAP:
	- SAP **[OpenUI5](https://openui5.org/)** (Basis für **[SAPUI5](https://ui5.sap.com)**)
	- Free Tier: SAP [Business Technology Platform (**BTP**)](https://www.sap.com/products/technology-platform/trial.html) für „Individuals“
	- SAP **[Fiori](https://www.sap.com/products/technology-platform/fiori.html)** (basiert auf SAPUI5)
	- [AppGyver](https://www.appgyver.com/) / SAP **[Build Apps](https://www.sap.com/products/technology-platform/no-code-app-builder/get-started.html)** (Low-Code-Plattform; technisch losgelöst von OpenUI5/SAPUI5)
- Spezial-Kontext WebAssembly:
	- **[wasmtime](https://wasmtime.dev)**: fast and secure runtime for WebAssembly
- Markdown Tools: vgl. [Awesome **Markdown**](https://github.com/mundimark/awesome-markdown)
- Tools for Web Programmer:
	- Browserkompatibilität: **[Can I use](https://caniuse.com/)**
	- Generatoren: **[favic-o-matic](https://favicomatic.com/)** favicon Generator, [**.htaccess**](https://www.htaccessredirect.net/) Generator, **[JQueryForm](https://www.jqueryform.com/)** Form Builder, [Flexy Boxes](https://the-echoplex.net/flexyboxes/)
	- [HTML **Cleaner**](https://html-cleaner.com/) (auch für [CSS](https://html-cleaner.com/css/) und [JS](https://html-cleaner.com/js/)) sowie HTML Beautifier **[DirtyMarkup](https://www.10bestdesign.com/dirtymarkup/)**
	- URLs: [URL-Decoder](https://www.urldecoder.org/)
	- [List of (free) **Public APIs**](https://github.com/public-apis/public-apis)
	- Markdown Editoren: **[Obsidian](https://obsidian.md/)** \[**choco install obsidian**\] (Verzeichnis als Vault öffnen…)
		- Hilfreich: **[ObisdianShell](https://github.com/Chaoses-Ib/ObsidianShell)** (Associate Markdown files with Obsidian)
		- Nennenswerte Plugins: [MK's Guide **Empfehlungsliste**](https://www.mksguide.com/best-obsidian-plugins/), [obsidian-**advanced-uri**](https://github.com/Vinzent03/obsidian-advanced-uri), [obsidian-**languagetool**-plugin](https://github.com/Clemens-E/obsidian-languagetool-plugin)
		- Historischer Hinweis: Typora nicht mehr kostenlos nach 0.11.18
- Tools für PWAs:
	- Build and Publish: [PWABuilder](https://www.pwabuilder.com/)
	- Icon Generator: [miTT PWA Asset Generator](https://mittl-medien.de/pwa-asset-generator)
- Tools for Web Designers:
	- Kostenlose Icons/Stock-Fotos/Illustrationen: vgl. Abschnitt **[Bildmaterialien](https://github.com/cyberlytics/awesome-thesis-tools#bildmaterialien)** auf meiner Abschlussarbeiten-Schwesterseite
	- Werkzeuglisten von speckyboy: [Tools for Web Designers #1](https://speckyboy.com/tiny-little-tools-web-design/), [Tools for Web Designers #2](https://speckyboy.com/tiny-little-web-based-tools-web-designers/), [CSS-Tools](https://speckyboy.com/free-tools-apps-css/)
	- Usage-Statistiken: [W³Techs](https://w3techs.com/technologies/) (bspw. [PHP-Versions](https://w3techs.com/technologies/details/pl-php), [Wordpress-Versions](https://w3techs.com/technologies/details/cm-wordpress), uvm.)
	- [**Lorem-Ipsum**-Generatoren](https://loremipsum.io/ultimate-list-of-lorem-ipsum-generators/)
	- Deutsch:
		- **[neuroflash](https://app.neuro-flash.com/)**: KI-gestützte Textgenerierung, kann Deutsch, stilistisch das was man „SEO-optimiert“ nennt (kostenlose 2000 Wörter)
	- Englisch:
		- [AI writing assistants](https://www.google.com/search?q=ai+text+generator): OpenAI **[ChatGPT](https://openai.com/blog/chatgpt/)** („Write a UX brief“, „Write a tagline for my tech gadget landing page“, „Write a user flow for a login page, mobile-first“, „Give me some ideas for a …“ und weitere: [ChatGPT-**Cheatsheet**](https://www.kdnuggets.com/publications/sheets/ChatGPT_Cheatsheet_Costa.pdf)) aber auch ältere Werkzeuge wie bspw. [rytr.me](https://rytr.me) (kostenlose 10K Zeichen), [copy.ai](https://www.copy.ai/) (kostenlose 2000 Wörter) oder [simplified](https://simplified.com/pricing) (kostenlose 3000 Wörter)
	- Werkzeugsammlung **[FutureTools](https://www.futuretools.io)**
	- Weiterführende Quellen: [Awesome Generative AI](https://github.com/steven2358/awesome-generative-ai)
- User Experience (UX):
	- [**WebGazer**.js](https://webgazer.cs.brown.edu/): eye tracking library that uses common webcams to infer the eye-gaze locations of web visitors on a page in real time
- Video Conferencing:
	- STUN/TURN:
		- Cloud: **[Metered](https://www.metered.ca/)**
		- Self-Hosted: **[coturn](https://github.com/coturn/coturn)**
	- Weiterführende Quellen: [Awesome Real Time Communications](https://github.com/rtckit/awesome-rtc)
- Hosting:
	- bspw. **[Heroku](https://www.heroku.com/pricing)** („Free and Hobby“), Google **[Firebase Hosting](https://firebase.google.com/pricing)** („Spark Plan“) oder Amazon **[AWS](https://aws.amazon.com/de/free/)** („Free Tier“)
	- Kostenpflichtig (€): bspw. **[Hetzner](https://www.hetzner.com/de/cloud)** im bayerischen Gunzenhausen
	- (Kostenlose Angebote auch bei den Cloud-Marktführern für jamstack (s. oben): Vercel, Netlify, u.a.)
- SEO:
	- Google [Search Console (GSC)](https://search.google.com/search-console/) | Google [Trends](https://trends.google.com/trends/)
	- The Hoth [Google Rank Checker](https://www.thehoth.com/search-engine-rankings/)
	- RankWatch [Website Analyzer](https://www.rankwatch.com/tools/web-analyzer.html) + RankWatch [Backlink Checker](https://www.rankwatch.com/backlinks/)
	- Weiterführende Quellen: [Awesome Search Engine Optimization](https://github.com/marcobiedermann/search-engine-optimization) | ahrefs [Free SEO Tools](https://ahrefs.com/blog/free-seo-tools/) | buffer [Free SEO Tools](https://buffer.com/library/free-seo-tools/) | [Awesome Marketing](https://github.com/marketingtoolslist/awesome-marketing)
- Ausgewählte fortgeschrittene Bausteine
	- **[KrakenD](https://www.krakend.io/)**: Open Source API Gateway (with [KrakenD Designer](https://designer.krakend.io))
	- **[Quarkus](https://quarkus.io/)** \[CLI: **choco install quarkus**\] Kubernetes-native Java Stack
- Web to Desktop frameworks:
	- = Cross-Plattform, aber primär Windows/Linux/MacOS und nicht notwendigerweise Mobile/Android/iOS
	- Electron: [Wikipedia](https://en.wikipedia.org/wiki/Electron_(software_framework)) | [github](https://github.com/electron/electron)
		- Showcase: [electron.js Showcase](https://www.electronjs.org/apps)
		- Build/Scaffold: [Electron Forge](https://www.electronforge.io/), [electron.js Fiddle](https://www.electronjs.org/fiddle)
	- Wichtige Electron-Alternative:
		- **[neutralinojs](https://neutralino.js.org/)** ⭐
			- [Vergleich mit Electron](https://github.com/neutralinojs/evaluation)
			- Schlanker, schneller **UND** Option auf Android/iOS-Deployment!
	- Mit komplexeren Backends:
		- Mit Node.js: [NodeGui](https://github.com/nodegui/nodegui) mit den Varianten [React NodeGUI](https://github.com/nodegui/react-nodegui), [Vue NodeGUI](https://github.com/nodegui/vue-nodegui), [Svelte NodeGUI](https://github.com/nodegui/svelte-nodegui)
		- Mit Rust: [Tauri](https://tauri.app/)
		- Mit Go: [Wail](https://github.com/wailsapp/wails)
	- Weiterführende Referenz: [Web to Desktop Framework Comparison](https://github.com/Elanis/web-to-desktop-framework-comparison)
- Weiterführende Quellen: [Awesome Webdesign](https://project-awesome.org/nicolesaidy/awesome-web-design) | [Frontend Development](https://github.com/dypsilon/frontend-dev-bookmarks/blob/master/TOTALLY-GIGANTIC-FILE.md) | [Awesome Microservices](https://github.com/mfornos/awesome-microservices) | [Awesome CRDT](https://github.com/alangibson/awesome-crdt)

## Mobile Apps

- Android/Kotlin: **[Android Studio](https://developer.android.com/studio)** \[**choco install androidstudio**\]
- iOS/Swift: [JetBrains **AppCode**](https://www.jetbrains.com/objc/), kostenlos über JetBrains [Free Educational Licenses](https://www.jetbrains.com/community/education/#students)
- Cross-Plattform
	- JS/TS: **[Ionic](https://ionicframework.com/)** | [React Native](https://reactnative.dev/)
	- Dart: [Flutter](https://flutter.dev/)
	- Electron-inspirierte Frameworks:
		- **[Tauri](https://tauri.app/)**
		- **[neutralinojs](https://neutralino.js.org/)
		- Low-Code: Konvertiere eine Webseite in eine mobile App: bspw. **[Median](https://median.co/)** (früher: GoNative)
- Tools für Mobile Apps:
	- App Icon Resizer: **[MakeAppIcon](https://makeappicon.com/)**
- App Performance Monitoring (und mehr): **[Instabug](https://www.instabug.com/)**
- In-App Purchases / Monetarisierung: [Adapty](https://adapty.io/) als Low-Code Plattform und SDK um In-App Subscriptions einfach in Mobile Apps zu integrieren

## Semantic Web / Knowledge Representation

- **[Protégé Desktop](https://protege.stanford.edu/software.php#desktop-protege)**: open source Ontology Editor (inkl. [Getting Started](https://protegeproject.GitHub.io/protege/getting-started/))
	- Cloud-Variante: **[WebProtégé](http://webprotege.stanford.edu/)**
- **[Schema.org](https://schema.org/docs/developers.html)** | [**YAGO** Graph](https://yago-knowledge.org/graph/) | [SparQL on **YAGO**](http://www.yago-knowledge.org/sparql) | [SparQL on **Wikidata**](https://query.wikidata.org/) | [SparQL on **DBpedia**](https://dbpedia.org/sparql) | [**prefix**.cc](https://prefix.cc/)
- [OpenLink **Virtuoso**](https://virtuoso.openlinksw.com/) als [Open-Source Edition (VOS)](http://vos.openlinksw.com/owiki/wiki/VOS/VOSDownload) \[via [Docker](https://hub.docker.com/r/openlink/virtuoso-opensource-7)\]: SPARQL- und SQL-fähiges Multi-Modell-Datenbanksystem / RDF Database
- [Apache **Jena**](https://jena.apache.org/): open source Java SPARQL-fähiger Triple Store / RDF Database
- [Ontotext **GraphDB**](https://www.ontotext.com/products/graphdb/): SPARQL-fähiger Triple Store / RDF Database \[with OWL reasoning, forward-chaining\]
- Weiterführende Quellen: [Awesome Semantic Web](https://github.com/semantalytics/awesome-semantic-web), [Awesome Knowledge Graph](https://github.com/totogo/awesome-knowledge-graph), [Awesome Linked Data](https://github.com/nandana/awesome-linkeddata)

## Verteilte Systeme

- **[parallel-ssh](https://github.com/ParallelSSH/parallel-ssh)** \[pip install parallel-ssh\]: asynchronous parallel SSH client library
- **[RabbitMQ](https://www.rabbitmq.com)** \[choco install rabbitmq\]: open-source message broker, Push-based approach (based on Erlang)
- [Apache **Kafka**](https://kafka.apache.org/): open-source pub/sub event streaming, Pull-based approach (open-sourced by LinkedIn in 2011, based on Java/Scala)
- **[Akka](https://akka.io)**: Actor Model on the JVM (Java/Scala)
	- [Akka.NET](https://getakka.net/): Akka-based Actor Model for C# and F# (see also [petabridge.cmd](https://cmd.petabridge.com) \[choco install petabridge-cmd\])
- **[ZeroMQ](https://zeromq.org/)**: open-source universal messaging library
	- [NetMQ](https://github.com/zeromq/netmq): .NET Standard port / Native C#
- **[Datomic](https://www.datomic.com/)**: Datalog-Implementierung von [Rich Hickey](https://github.com/tallesl/Rich-Hickey-fanclub), dabei architekturell interessant weil Distributed, Transactional und Immutable
- [Conflict-free Replicated Data Types (**CRDT**)](https://crdt.tech/implementations): z.B. [SyncedStore](https://syncedstore.org/docs/) | [Fluid Framework](https://fluidframework.com/)
- Weiterführende Quellen: [Awesome Distributed System Projects](https://github.com/roma-glushko/awesome-distributed-system-projects) | [Awesome CRDT](https://github.com/alangibson/awesome-crdt)
- (Insbesondere dieser Abschnitt überlappt sich mit anderen Abschnitten, daher ist er rein additiv zu verstehen.)

## Cloud-Computing

- [Cloud Native Landscape](https://landscape.cncf.io)
- Kostenlose Cloud Kontingente: [AWS Free Tier](https://aws.amazon.com/free/), [Azure Free Tier](https://azure.microsoft.com/pricing/free-services), [Google Cloud Free Tier](https://cloud.google.com/free/)
	- Nur für Studierende: [Azure for Students](https://azure.microsoft.com/free/students/), [Heroku for Students](https://www.heroku.com/students), [MongoDB for Students](https://www.mongodb.com/students), GitHub Pages via [GitHub Student Developer Pack](https://education.github.com/pack)
- Cloud Marktfüher: [Amazon **AWS**](https://aws.amazon.com/free/), [Microsoft **Azure**](https://azure.microsoft.com/pricing/free-services/), [**Google** Cloud](https://cloud.google.com/free), [**Alibaba** Cloud](https://www.alibabacloud.com/free), [**IBM** Cloud](https://www.ibm.com/cloud/free), [**Tencent** Cloud](https://www.tencentcloud.com/campaign/freetier), [Oracle **OCI**](https://www.oracle.com/cloud/free/), Heroku (no free tier anymore \*sigh\*), **[DigitalOcean](https://www.digitalocean.com/pricing/app-platform)**, [**SAP** BTP](https://www.sap.com/products/technology-platform/trial.html)
	- jamstack: **[Vercel](https://vercel.com/pricing)** (ehem. ZEIT), **[Netlify](https://www.netlify.com/pricing/)**, [GitHub **Pages**](https://pages.github.com/), **[Stormkit](https://www.stormkit.io)**, [Google **Firebase**](https://firebase.google.com/pricing), [AWS **Amplify**](https://aws.amazon.com/amplify/), [Azure **Static Web Apps**](https://azure.microsoft.com/products/app-service/static/) \[**[Awesome JAMstack](https://github.com/automata/awesome-jamstack)**\]
- Empfohlene Docker-Alternative: **[podman](https://docs.podman.io/en/latest/)** (u.a. daemonless; optional: rootless; v.a. Linux aber auch erste [Windows-Gehversuche](https://github.com/containers/podman/blob/main/docs/tutorials/podman-for-windows.md)) sowie ggf. [buildah](https://buildah.io/) direkt
	- Weitere Alternativen: OpenStack [KataContainers](https://katacontainers.io/), AWS [Firecracker](https://firecracker-microvm.GitHub.io/), google [gVisor](https://gvisor.dev/) (und historisch: CoreOS [rkt](https://github.com/rkt/rkt), später per [CNCF archived](https://www.cncf.io/archived-projects/))
	- OpenShift Stack ab v4: [CRI-O](https://cri-o.io/), [podman](https://docs.podman.io/en/latest/), [buildah](https://buildah.io/)
- Docker-Werkzeuge:
	- **[Play with Docker](https://labs.play-with-docker.com/)**: kostenlose Browser-basierte Docker-Umgebung
	- **[hadolint](https://github.com/hadolint/hadolint)**: linter für Dockerfiles \[**docker run --rm -i hadolint/hadolint \< Dockerfile**\]
	- (Es gibt noch eine Lücke: Gibt es einen guten [.](https://codefresh.io/blog/not-ignore-dockerignore-2/)[dockerignore](https://codefresh.io/blog/not-ignore-dockerignore-2/)-Generator!?)
	- **[Divio](https://www.divio.com/pricing/)** | **[Northflank](https://northflank.com/pricing)** | **[mogenius](https://mogenius.com/pricing)**: kostenlose Deployments für Docker-basierte Proof-of-Concept WebApps
	- Letzte Version bspw. von [Alpine](https://endoflife.date/alpine)? Bspw. mittels [**endoflife**.date](https://endoflife.date/) (EOL)
	- Nennswert: [dockur](https://github.com/dockur), bspw. [Windows in Docker](https://github.com/dockur/windows), [MacOS in Docker](https://github.com/dockur/macos))
- Container Registry:
	- DockerHub ➔ **docker.io**/username/appname:tagname
	- Git Hub **GHCR** ➔ **ghcr.io**/username/appname:tagname
	- Red Hat **[Quay](https://quay.io/)** ➔ **quay.io**/username/appname:tagname
	- Eigene Registry-Installation \[docker run … [docker.io/registry:2](https://www.docker.com/blog/how-to-use-your-own-registry-2/)\] ➔ **localhost:5000**/username/appname:tagname
	- (zzgl. diejenigen von Amazon, Microsoft, …)
- Kubernetes:
	- Browser
		- **[Play with K8s](https://labs.play-with-k8s.com/)**: kostenlose Browser-basierte Kubernetes-Umgebung
		- [**OpenShift** Playground](https://www.redhat.com/en/interactive-labs/openshift): kostenlose Browser-basierte OpenShift-Umgebung
	- Lokale Entwickler-Installation
		- Rancher **[k3d](https://k3d.io)** \[**choco install k3d**\]: Runs Rancher Lab’s minimal k3s Kubernetes distribution via docker
		- Rancher **[k3s](https://k3s.io)**: Lightweight Kubernetes, bspw. über [k3sup](https://github.com/alexellis/k3sup) \[**choco install k3sup**\]
		- **[Rancher Desktop](https://rancherdesktop.io/)** \[**choco install rancher-desktop**\]: Runs Kubernetes and container management on your desktop
	- Personal K8s / Cookbooks / Awesome Selfhosted
		- [Funky Penguin's Geek Cookbook](https://geek-cookbook.funkypenguin.co.nz/)
	- Enterprise Installation
		- Red Hat **[OKD](https://www.okd.io/)** (OpenShift-basiert)
		- Rancher **[RKE1](https://rke.docs.rancher.com/)** (Pure-Container-basiert, über [RancherOS](https://github.com/rancher/os), mit Docker als Container Engine) \[**choco install rke**\]
		- Rancher **[RKE2](https://rancher.com/products/rke)** (Combines RKE1 and K3s; embedded container runtime is containerd)
- KI-gestütztes Kubernetes-Management:
	- **[K8sGPT](https://k8sgpt.ai)**: tool for scanning your kubernetes clusters, diagnosing and triaging issues in simple English
- **[Arkade](https://get-arkade.dev/)**: Open Source [Marketplace](https://github.com/alexellis/arkade#catalog-of-apps) for Kubernetes
- **[Portainer](https://www.portainer.io/)** Community Edition: Open Source Container Management for Personal Use
- **[cAdvisor](https://github.com/google/cadvisor)**: understand the resource usage and performance characteristics of containers
- Kube-nativ MicroService Frameworks
	- Java:
		- **[Quarkus](https://quarkus.io/get-started/)** \[CLI: **choco install quarkus**\]
		- **[Micronaut](https://micronaut.io/)** \[CLI: **choco install micronaut**\]
- Serverless:
	- **[Val Town](https://www.val.town/)**: run code instantly
	- [Apache **OpenWhisk**](https://openwhisk.apache.org/): Open Source Serverless Cloud Platform
	- **[Knative](https://knative.dev/)**: Google-sponsored Open Source Serverless Cloud Platform
	- Scale to Zero:
		- **[OpenFaaS](https://www.openfaas.com/)**-based [Scale to Zero](https://docs.openfaas.com/openfaas-pro/scale-to-zero/)
		- WSO2 **[Cellery](https://github.com/wso2/cellery)**: Scale to Zero with Kubernetes-based [Knative](https://knative.dev/)
		- **[KEDA](https://keda.sh)**: Scale to Zero with Kubernetes-based Event-Driven Autoscaler
	- Geringe [Cold-Start](https://betterdev.blog/aws-lambda-performance-optimization/#cold_starts)-Zeiten:
		- **DO**: Rust \[**choco install rustup.install**\], Zig \[**choco install zig**\], WASM \[**choco install wasmedge**\]
			- Sowie JavaScript/Node.js \[**choco install Node.js**\] v.a. wg. kleiner Lambda bundle size durch Tree-Shaking
			- Und auch Python \[**choco install python**\] mit erstaunlich geringen Cold-Start-Zeiten
		- **DONT**: Java, C# (und Vorsicht vor naivem Einsatz von Docker)
- Green Cloud:
	- **[Kepler](https://github.com/sustainable-computing-io/kepler)** (=Kubernetes Efficient Power Level Exporter): energiebezogene Systemstatistiken, als Prometheus-Metriken exportierbar
- Weiterführende Quellen: [Nubenetes](https://nubenetes.com/) / [Nubenetes Other](https://nubenetes.com/other-awesome-lists/) | [Awesome Sysadmin](https://github.com/awesome-foss/awesome-sysadmin) | [Awesome Chaos Engineering](https://github.com/dastergon/awesome-chaos-engineering) | [Awesome AWS](https://github.com/donnemartin/awesome-aws) | [Awesome Serverless](https://github.com/anaibol/awesome-serverless) | [Awesome Lambda Essentials](https://github.com/danteata/awesome-aws-lambda) | [Awesome Lambda Layers](https://github.com/mthenw/awesome-layers)
- Post-Mortems: **[Kubernetes Failure Stories](https://k8s.af/)**

## DevOps

\[Hier: Cloud-Native! Traditionellere DevOps Ergänzungen: vgl. Schwesterseite [SWE » DevOps](https://github.com/cyberlytics/awesome-software-engineering-tools#devops) (!) \]

- **Continuous Integration** / **Continuous Delivery** (CI/CD)
	- [Jenkins X](https://jenkins-x.io/): GitOps based Tekton pipelines
		- Related Book: [The DevOps 2.6 Toolkit: Jenkins X Cloud-Native Kubernetes-First Continuous Delivery](https://github.com/vfarcic/devops26)
	- Cloud-native: **[Spinnaker](https://spinnaker.io)** (auch: GitLab, fluxcd, codefresh, Argo CD, …)
	- Weiterführende Referenzen: [Awesome CI](https://github.com/ligurio/awesome-ci), **[Awesome CI and CD](https://github.com/cicdops/awesome-ciandcd)**
- Cloud Automation
	- Google **[Cloud Operations Sandbox](https://cloud-ops-sandbox.dev)**
- Kubernetes Deployment (with Package Manager, Dependencies, …):
	- **[Helm](https://helm.sh)**: Helm Charts help you define, install, and upgrade even the most complex Kubernetes application
	- **[Acorn](https://www.acorn.io)**: Containerized application packaging framework that simplifies deployment on Kubernetes
- **HashiCorp** Stack:
	- **[Vagrant](https://www.vagrantup.com/)** «Build&Test» \[**choco install vagrant**\] & **[Vagrant Cloud Box](https://app.vagrantup.com/boxes/search)**
	- **[Packer](https://www.packer.io/)** «Package» \[**choco install packer**\]
	- **[TerraForm](https://www.terraform.io/)** «Unified Provision» \[choco **install terraform**\]
	- **[Vault](https://www.vaultproject.io/)** «Secure» \[**choco install vault**\]
	- **[Consul](https://www.consul.io/)** «Connect&Maintain» & **[Consul Tools](https://www.consul.io/docs/download-tools)**
	- **[Nomad](https://www.nomadproject.io/)** «Orchestrate&Run» \[**choco install nomad**\]
	- **[Waypoint](https://www.waypointproject.io/)** «Unified Deploy»
- Open-Source-Alternativen für HashiCorp:
	- **[OpenTofu](https://opentofu.org/)**: drop-in replacement for Terraform
- **[Resilience4j](https://github.com/resilience4j/resilience4j)**: lightweight fault tolerance library inspired by Netflix Hystrix
- Software-Artifact Repository \[Cloud\]:
	- [JFrog **Artifactory**](https://jfrog.com/artifactory/) (free: 2GB, 5 Users): 
	- (Traditionelle Varianten auf der [SWE-Schwesterseite](https://github.com/cyberlytics/awesome-software-engineering-tools#devops))
- Cloud Monitoring:
	- [OpenTelemetry](https://opentelemetry.io/): Instrumentation and data pipeline, i.e., unified collection for traces, metrics, logs
	- [Prometheus](https://prometheus.io/): Metrics collection and querying
	- [Jaeger](https://www.jaegertracing.io/): Distributed Tracing
- Chaos Engineering:
	- Netflix **[Chaos Monkey](https://github.com/netflix/chaosmonkey)** (retired: [Simian Army](https://github.com/Netflix/SimianArmy)), insbesondere mittels [Spinnaker](https://spinnaker.io) (Continuous Delivery) u.a. für [Kubernetes](https://kubernetes.io) (Orchestrierung/Komposition)
	- **[Pumba](https://github.com/alexei-led/pumba)**: chaos testing tool for Docker
	- Chaos für Arme unter Windows (Netzwerk-only): **[clumsy](https://github.com/jagt/clumsy)** \[**choco install clumsy**\]
- Weiterführende Quellen:
	- [Awesome SRE Tools](https://github.com/SquadcastHub/awesome-sre-tools), [Awesome Chaos Engineering](https://github.com/dastergon/awesome-chaos-engineering)
	- (Traditionellere Quellen auf der [SWE-Schwesterseite](https://github.com/cyberlytics/awesome-software-engineering-tools#devops))

## Operations Research (OR) / Optimization

- Überblick/Werkzeuge-Einstieg
	- Werkzeuge: Newsletter **[OPTIMA 103](http://www.mathopt.org/Optima-Issues/optima103.pdf)** der Mathematical Optimization Society
	- Benchmarks: **[for Optimization Software](https://plato.asu.edu/bench.html)**
- Solver für Lineare Programmierung
	- Open Source: **[CBC](https://github.com/coin-or/Cbc)**, **[YALMIP](http://users.isy.liu.se/johanl/yalmip/)**, **[GLPK](http://www.gnu.org/software/glpk/glpk.html)**, COIN-OR CLP/**[CBC](https://github.com/coin-or/Cbc)**, **[HiGHS](https://highs.dev/)**, **[SCIP](https://www.scipopt.org/)**
	- Kommerziell: **[CPLEX](https://www.ibm.com/support/knowledgecenter/SSSA5P_12.10.0/ilog.odms.cplex.help/cplex_KC_home.html)**, **[Gurobi](http://www.gurobi.com/)**, **[XPRESS-MP](http://www.fico.com/en/products/fico-xpress-optimization-suite/)**, **[MOSEK](https://www.mosek.com/)**
- Modelers
	- **[Pulp](https://pypi.org/project/PuLP/)** (python modeling interface), **[Pyomo](http://www.pyomo.org/documentation)**, **[CMPL](https://projects.coin-or.org/Cmpl)**, …
- Convex Optimization
	- **[CVXOPT](http://cvxopt.org/)** (für Python: **[CVXPY](https://www.cvxpy.org/)**), …
- Optimization Frameworks
	- Google **[OR-Tools](https://developers.google.com/optimization)**, **[OptaPlanner](https://www.optaplanner.org/)** (CP Solver), **[COIN-OR](https://www.coin-or.org/)**, **[HiGHS](https://www.maths.ed.ac.uk/hall/HiGHS/)**, **[UG](https://ug.zib.de/)**, **[GEKKO](https://gekko.readthedocs.io/en/latest/)**

## ML / AI

- In-Database Processing (ML)
	- **[PostgresML](https://postgresml.org/)**
	- [Apache **Flink ML**](https://nightlies.apache.org/flink/flink-ml-docs-stable/)
	- **[Exasol UDF](https://docs.exasol.com/db/latest/database_concepts/udf_scripts.htm)** (u.a. [Python-Classification](https://docs.Exasol.com/advanced_analytics/python_classification_example.htm)-Beispiel)
	- [Amazon **Redshift ML**](https://aws.amazon.com/de/redshift/features/redshift-ml/)
	- [Google **BigQuery ML**](https://cloud.google.com/bigquery-ml/docs/introduction)
	- **[MindsDB](https://mindsdb.com/)**
- ML-Extension to DBMS
	- [**SQLFlow**.org](https://sql-machine-learning.GitHub.io/)
- LLMs
	- Modelle:
		- Open Source: Webartikel [6 Best **Open-Source LLMs** to Watch Out For in 2024](https://www.techopedia.com/6-best-open-source-llms-to-watch-out-for-in-2024)
	- Dev:
		- Java: **[Spring AI](https://docs.spring.io/spring-ai/reference/)**, **[LongChain4j](https://github.com/langchain4j/langchain4j)**
	- Chatbots: [**perplexity**.ai](https://www.perplexity.ai/) (mit „Focus: Academic“)
		- Alternativen: OpenAI [ChatGPT](https://openai.com/blog/chatgpt/), [HuggingChat](https://huggingface.co/chat/), [Andi](https://andisearch.com), Microsoft [Bing](https://bing.com/new), Google [Bard](https://bard.google.com/)
	- AI-enabled Browser: Perplexity [Comet](https://comet.perplexity.ai/), [Sigma](https://www.sigmabrowser.com/), [Fellou](https://fellou.ai/), Arc [Max](https://arc.net/max), Opera [Aria](https://www.opera.com/de/features/aria), Microsoft Edge+Copilot
		- Mac-only: [Dia](https://www.diabrowser.com/)
	- Multi-modale KI: Google **[Gemini](https://deepmind.google/technologies/gemini/)**
	- Lokale LLMs / Offline:
		* **[Msty](https://msty.app/)** ⭐
		* **[Witsy](https://witsyai.com/)** \[**choco install witsy**\]
		* **[Xorbits Inference](https://github.com/xorbitsai/inference)** ([OpenAI-equivalent API](https://inference.readthedocs.io/en/stable/user_guide/client_api.html) at http://localhost:9997/v1)
		* [**Jan**.ai](https://jan.ai/download) (OpenAI-equivalent API at https://localhost:1337)
		* **[LM Studio](https://lmstudio.ai/)** \[**choco install lm-studio**\]
		* **[Open WebUI](https://github.com/open-webui/open-webui)**
		* [OpenLLM](https://github.com/bentoml/OpenLLM) (pip install openllm; chat UI at http://localhost:3000/chat)
	- Lokales Text-to-Image:
		- AUTOMATIC1111 [stable-diffusin-webui](https://github.com/AUTOMATIC1111/stable-diffusion-webui)
		- [Fooocus](https://github.com/lllyasviel/Fooocus)
		- [CompyUI](https://github.com/comfyanonymous/ComfyUI) ([Tutorial](https://stable-diffusion-art.com/comfyui/))
	- IT-Security for LLMs:
		- Hintergrundwissen: [OWASP Top-10 for LLMs](https://genai.owasp.org/llm-top-10/)
		- [LLM Guard](https://github.com/jujumilk3/leaked-system-prompts)
	- Weiterführende Quellen: [Awesome LLM](https://github.com/Hannibal046/Awesome-LLM)
- ML-Plattformen
	- Desktop/Self-Hosting:
		- **[IBM Watson Studio Desktop](https://www.ibm.com/account/reg/de-de/signup?formid=urx-19947)**
		- **[ClearML](https://github.com/allegroai/clearml)**: Open-Source ML Plattform (Cloud | Self-Hosted)
		- **[MLflow](https://mlflow.org/)**: Open-Source ML Plattform (Self-Hosted)
	- Cloud:
		- Kostenlose Angebote bei allen Cloud-Marktführern:\
			**[AWS ML](https://aws.amazon.com/de/free/machine-learning/)** und insb. **[AWS SageMaker](https://aws.amazon.com/de/sagemaker/pricing/)**, **[Azure ML](https://azure.microsoft.com/services/machine-learning/)**, [**Google** GCP AI & **ML**](https://cloud.google.com/products/ai), …
		- **[ClearML](https://app.clear.ml/)**, wie oben bei Desktop bereits aufgeführt, auch mit einem Free-Tier-Angebot in der Cloud
		- (€€€): **[Dataiku](https://www.dataiku.com/product/get-started/)**, u.a. [in Kombination mit Snowflake](https://www.dataiku.com/partners/snowflake/)
- MLOps-bezogen:
	- (Die ganzen ML-Frameworks wie AWS SageMaker, IBM Watson, ClearML, MLflow haben auch alle integrierte MLops-Funktionalitäten, …)
	- [Iterative **Studio**](https://studio.iterative.ai/): Collaboration for Machine Learning Teams
	- [Iterative](https://dvc.org/) **[DVC](https://dvc.org/)**: Open-source Version Control System for Machine Learning Projects
	- **[Sacred](https://github.com/IDSIA/sacred)**: A tool to help you configure, organize, log and reproduce experiments
	- [Apache **Marvin-AI**](https://marvin.apache.org/): Open-Source MLOps Plattform
- LLMOps / LLM-Plattform / Agentic AI:
	- **[Dify](https://dify.ai/)**: build, deploy, and manage AI-powered applications
	- [Coze](https://www.coze.com/): build chatbots and automated virtual assistants
	- Void, TabbyML, GitHub Copilot and Claude Code.
- Text Processing
	- [PyPDF2](https://pypi.org/project/PyPDF2/): convert simple, text-based PDF files into text readable by Python
	- **[spaCy](https://spacy.io/)**: free, open-source library for advanced Natural Language Processing (NLP) in Python
	- **[nltk](https://www.nltk.org/)**: suite of text processing libraries for classification, tokenization, stemming, tagging, parsing, and semantic reasoning
	- **[doccano](https://github.com/doccano/doccano)**: open source text annotation tool for humans (text classification, sequence labeling and sequence to sequence tasks)
	- Weiterführende Quellen: [Awesome NLP](https://github.com/keon/awesome-nlp) | [Awesome Deep Learning for NLP](https://github.com/brianspiering/awesome-dl4nlp) | [Awesome Sentiment Analysis](https://github.com/laugustyniak/awesome-sentiment-analysis)
- ML-Quality:
	- **[Giskard](https://www.giskard.ai)**: Qualitätssicherungsmöglichkeiten mit Schwerpunkt auf Erklärbarkeit und Fairness
- KI-zentrischer Benchmark für Smartphone-HW: [AI-Benchmark](https://ai-benchmark.com/)
- KI Repos: bspw. **[Hugging Face](https://huggingface.co/)**
- Robotik:
	- Weiterführende Quellen: [Awesome Robotics Libraries](https://github.com/jslee02/awesome-robotics-libraries) | [Awesome Robotics](https://github.com/kiloreux/awesome-robotics)
- Akademisch / State of the Art
	- Repository **[Papers with Code](https://paperswithcode.com/sota)**
- Industrielle Forschung
	- Nennenswerte internationale **KI Labs**: **[OpenAI](https://en.wikipedia.org/wiki/OpenAI)** (z.B. [GTP-3](https://openai.com/blog/openai-api/), [DALL·E](https://openai.com/dall-e-2/), [ChatGPT](https://chat.openai.com/)), Alphabet **[DeepMind](https://en.wikipedia.org/wiki/DeepMind)** (z.B. [AlphaGo](https://www.deepmind.com/research/highlighted-research/alphago)), **[Google AI](https://www.ai.google/)** ([TensorFlow](https://www.tensorflow.org/), [LaMDA](https://blog.google/technology/ai/lamda/), [Imagen](https://imagen.research.google/)), Facebook Artificial Intelligence Research (FAIR) = **[Meta AI](https://www.wikiwand.com/en/Meta_AI)** (z.B. [PyTorch](https://pytorch.org/)), **[Tesla AI](https://www.tesla.com/AI)** (z.B. [autopilot](https://www.tesla.com/autopilot)), **[Ueber AI](http://uber.ai/)** (z.B. [Pyro](https://pyro.ai/))
	- Nennenswerte kleine Labs (KI-Bildgeneratoren): [**stability**.ai](https://stability.ai/) ([Stable Diffusion](https://github.com/CompVis/stable-diffusion)), **[Midjourney](https://www.midjourney.com/)** ([Midjourney Bot](https://docs.midjourney.com/docs/midjourney-discord)), **[Craiyon](https://www.craiyon.com/)** (früher: DALL-E Mini), **[artbreeder](https://www.artbreeder.com/)**
- Weiterführende Quellen: [Awesome AI](https://github.com/amusi/awesome-ai-awesomeness) | [Awesome Deep Learning](https://github.com/ChristosChristofidis/awesome-deep-learning) | [Awesome AI-ML-DL](https://github.com/neomatrix369/awesome-ai-ml-dl) | [MLOps.toys](https://mlops.toys/) | [Awesome MLOps](https://github.com/kelvins/awesome-mlops) (and [references](https://ml-ops.org/content/references.html)) | [Awesome Software Engineering for Machine Learning](https://github.com/SE-ML/awesome-seml)

## Low-Code / No-Code

- Visual Software Development:
	- **[OutSystems](https://www.outsystems.com/pricing-and-editions/)**: Low-Code Application Building
	- **[Amplication](https://amplication.com/)**: Auto-generates an app based on TypeScript and Node.js (NestJS, Prisma, REST & GraphQL API, React Admin UI)
- Visual Workflow Builder: [n8n](https://docs.n8n.io/hosting/)
- Visual Database: [APITable](https://github.com/apitable/apitable) (WSL2: curl https://apitable.github.io/install.sh | bash)
- Visual ML:
	- **[DataRobots](https://www.datarobot.com/)**: Low-Code ML; mit einem „[Academic Program](https://www.datarobot.com/education/academic-support-program/)“
	- (€:) [Amazon **SageMaker**](https://aws.amazon.com/de/sagemaker/), allerdings [2 Monate kostenlose Kontingente](https://aws.amazon.com/de/sagemaker/pricing/)
	- Manche zählen **[KNIME](https://www.knime.com/)** \[**choco install knime**\] auch als Low-Code ML Werkzeug
- Spezial-Kontext SAP:
	- SAP **[Build Apps](https://www.sap.com/products/technology-platform/no-code-app-builder/get-started.html)** (ehem. [AppGyver](https://www.appgyver.com); technisch losgelöst von OpenUI5/SAPUI5)
- Weiterführende Quellen: [Awesome low-code](https://github.com/antdimot/awesome-lowcode) | [Awesome Nocode / Lowcode](https://github.com/valentin-vogel/awesome-nocode-lowcode) | [Mapping the no-code AI landscape](https://levity.ai/blog/no-code-ai-map)


## Edge / Fog / IoT

- Cloud Marktführer: [Amazon **IoT Greengrass**](https://aws.amazon.com/greengrass/) | [Microsoft **IoT Edge**](https://azure.microsoft.com/en-in/services/iot-edge/) | [Google **Cloud IoT**](https://cloud.google.com/solutions/iot/)
	- Nennenswert: [NVIDIA **EGX**](https://www.nvidia.com/en-us/data-center/products/egx-edge-computing/)
- **[balenaEtcher](https://www.balena.io/etcher/)** \[**choco install etcher**\]: Flash OS images to SD cards & USB drives (u.a. für Raspberry Pi)
- **[balenaCloud](https://www.balena.io/cloud)**: IoT Flotten-Management, u.a. für Raspberry Pi
- **[EdgeX](https://www.edgexfoundry.org/)**: open source IoT Edge platform, with edge intelligence (AI/ML)
	- Alternative: **[OpenRemote](https://github.com/openremote/openremote)**
- **[Eclipse IoT Projects](https://iot.eclipse.org/projects/)**: sehr viele Projekte, neben dem weitverbreiteten [Mosquitto](https://projects.eclipse.org/projects/iot.mosquitto) (MQTT) auch [Cyclone DDS](https://projects.eclipse.org/projects/iot.cyclonedds) uvm.
- **[Eclipse Automotive Projects](https://projects.eclipse.org/projects/automotive)**: bspw. software-defined vehicle (SDV) mittels **[Eclipse Leda](https://projects.eclipse.org/projects/automotive.leda)**
- **[Yocto Project](https://www.yoctoproject.org/)** (YT): create custom Linux-based systems / custom embedded Linux distributions
- Cloud-native IoT:
	- **[ThingsBoard](https://thingsboard.io/)** (Open Source)
- Weiterführende Quellen: [Awesome IoT & Hybrid](https://project-awesome.org/weblancaster/awesome-IoT-hybrid) | [Awesome Edge Computing](https://github.com/qijianpeng/awesome-edge-computing)

## dApps

- **[Substrate](https://substrate.io)**: Blockchain Framework, for multichains, designed to seamlessly connect to [Polkadot](https://polkadot.network)
- **[HardHat](https://hardhat.org)**: Ethereum development environment
- **[LBRY](https://lbry.com/)**: blockchain-based file-sharing, social networks and video platform („open, free, and fair network for digital content“)
- **[DappRadar](https://dappradar.com/rankings)**: Discover popular decentralized Apps
- Weiterführende Quellen: [Awesome dApps](https://github.com/jasonwalsh/awesome-dapps) | [Awesome web3](https://github.com/ahmet/awesome-web3)

## Security

### Professional Security

- **2FA /** RFC 6238? **[Authy](https://authy.com/)** \[**choco install authy-desktop**\] als One-Time Password (OTP) Authenticator
- **[OpenSSL](https://www.openssl.org/)** \[**choco install openssl.light --ignore-dependencies**\]: Open Source toolkit for SSL/TLS
- **[KeyStore Explorer](https://keystore-explorer.org/)** \[**choco install keystore-explorer.portable**\]: handle various X.509 certificates and KeyStore types (PKCS#12, BKS, UBER, JKS, JCEKS)
- **[Certify the Web](https://certifytheweb.com/)** \[**choco install certifytheweb --ignore-dependencies**\]: Easily manage SSL/TLS certificates from letsencrypt.org and other ACME Certificate Authorities
- User Authentication Platforms: [Überblicksartikel zu **Auth0** sowie **Firebase** Alternativen](https://geekflare.com/user-authentication-platforms/)
- **[Wireshark](https://www.wireshark.org/)** \[**choco install wireshark**\]: Open Source Network Packet Analysis
- **[nmap](https://nmap.org/)** \[**choco install nmap**\]: Open Source Network Scanning and Auditing
- **[Password4j](https://password4j.com)**: fluent cryptographic Java library for passwords
- Passwort-Listen: [**SecList**-Sammlung](https://github.com/danielmiessler/SecLists) | [**SkullSecurity**-Sammlung](https://www.skullsecurity.org/wiki/Passwords) | [**haveibeenowned**-Downloader](https://github.com/HaveIBeenPwned/PwnedPasswordsDownloader) | [weitere…](https://blog.g0tmi1k.com/2011/06/dictionaries-wordlists/)
- **[Hack the Box](https://www.hackthebox.com/)**: kostenloser Cloud-basierter Hacking Playground
- Tenable [**Nessus** Essentials](https://www.tenable.com/products/nessus/nessus-essentials) (kostenlos für 16 IPs): Vulnerability Assessment im Netzwerk
	- Sowie für Studierende und Dozenten die Option: [Tenable Essentials for Education](https://www.tenable.com/tenable-for-education)
	- Alternative: [OpenVAS](https://openvas.org)
- [Security Technical Implementation Guides (**STIGs**)](https://public.cyber.mil/stigs/): a configuration standard consisting of security requirements for a specific product
	- [SCC SCAP-Automation-Tool](https://public.cyber.mil/stigs/scap/) \[**choco install scap-compliance-checker**\], sowie STIG-Dateien 1) für [automatisierte Ausführung (SCAP)](https://public.cyber.mil/stigs/scap/) und 2) [manuelle Ausführung (Document Library)](https://public.cyber.mil/stigs/downloads/) sowie [STIG Viewer](https://public.cyber.mil/stigs/srg-stig-tools/) \[**choco install stigviewer**\]
- Threat Modeling: OWASP **[Threat Dragon](https://owasp.org/www-project-threat-dragon/)** | Microsoft [Threat Modelling Tool (**TMT**)](https://aka.ms/threatmodelingtool)
- [**BurpSuite** Community Edition](https://portswigger.net/burp/communitydownload) \[**choco install burp-suite-free-edition**\]: web security testing
- **[Nikto2](https://cirt.net/Nikto2)**: Open source suite for comprehensive tests against web servers
- **[Puma Scan](https://github.com/pumasecurity/puma-scan)**: secure code analysis tool for .NET Core projects
- **[Security Code Scan](https://security-code-scan.GitHub.io/)**: Detects various security vulnerability patterns in .NET Core projects
- **[Docker Bench Security](https://github.com/docker/docker-bench-security)**: script that checks for dozens of common best-practices
- **[ScoutSuite](https://github.com/nccgroup/ScoutSuite)**: multi-cloud security-auditing tool
- **[snyk](https://app.snyk.io/)** (formerly DeepCode): find and fix vulnerabilities in code and containers
- **[Trivy](https://github.com/aquasecurity/trivy)**: Versatile Security Scanner (i.a., Container)
- git-Hygiene (git Secrets Scanning)? vgl. Abschnitt [git](https://github.com/cyberlytics/awesome-software-engineering-tools#git) auf der SWE-Schwesterseite (**[TruffleHog](https://github.com/trufflesecurity/trufflehog)**, **[Gitleaks](https://github.com/gitleaks/gitleaks)**, **[GitGuardian](https://www.gitguardian.com/)** , [**BFG** Repo-Cleaner](https://rtyley.GitHub.io/bfg-repo-cleaner/), etc.)
- Chaos Engineering? vgl. Abschnitt [DevOps](https://github.com/cyberlytics/awesome-software-engineering-tools#devops) auf der SWE-Schwesterseite (**[Pumba](https://github.com/alexei-led/pumba)**, Netflix **[Chaos Monkey](https://github.com/netflix/chaosmonkey)** / [Simian Army](https://github.com/Netflix/SimianArmy), etc.)
- Anti-SQL-Injection: **[sqlmap](https://github.com/sqlmapproject/sqlmap)**
- **[Autopsy](https://www.autopsy.com/)** \[**choco install autopsy**\]: Forensik-Werkzeug, als GUI für [The Sleuth Kit](https://www.sleuthkit.org/sleuthkit/)
- [Mobile Verification Toolkit (**MVT**)](https://github.com/mvt-project/mvt): Mobile Forensics Tool (für iOS und Android)
	- Kostenlose Alternativen: [Oxygen Forensic Viewer](https://www.oxygen-forensic.com/de/products/free-viewer)
	- Kommerzielle Alternativen: [OpenText EnCase](https://security.opentext.com/encase-forensic), [SFP Pro](https://www.salvationdata.com/business-list-page/smartphone-forensic-system-professional/), […](https://www.computerwoche.de/a/tools-fuer-die-mobile-forensik)
- Weiterführende Quellen: [Awesome Cybersecurity Blueteam](https://github.com/fabacab/awesome-cybersecurity-blueteam) | [Awesome Security](https://github.com/sbilly/awesome-security) | [Awesome Web Security](https://project-awesome.org/qazbnm456/awesome-web-security) | [Awesome Security Hardening](https://github.com/decalage2/awesome-security-hardening) | [Awesome Embedded and IoT Security](https://project-awesome.org/fkie-cad/awesome-embedded-and-iot-security) | [Awesome Forensics](https://github.com/cugu/awesome-forensics) | [Awesome Incident Response](https://github.com/meirwah/awesome-incident-response)
- **DevSecOps**:
	- Static Code Analysis Tool: [Checkov](https://github.com/bridgecrewio/checkov)
	- Container Security: vgl. [Awesome Container Security](https://github.com/kai5263499/awesome-container-security); ausgewähltes Beispiel: Sysdig [Falco](https://sysdig.com/opensource/falco/)
	- Compliance: [OpenSCAP](https://www.open-scap.org)
	- Compliance as Code: Chef [InSpec](https://www.chef.io/products/chef-inspec)
	- Forensics: [Volatility](https://github.com/volatilityfoundation/volatility) | [GRR Rapid Response](https://github.com/google/grr)
	- Weiterführende Quellen: [Awesome DevSecOps](https://project-awesome.org/TaptuIT/awesome-devsecops) | [Awesome Container Security](https://github.com/kai5263499/awesome-container-security) | [Kubernetes Security](https://kubernetes-security.info/) | [Open Source Tools for AWS Security](https://github.com/toniblyx/my-arsenal-of-aws-security-tools)

### LLM-Security
- [OWASP AI Exchange](https://owaspai.org/)
- [rebuff](https://github.com/protectai/rebuff): protect AI applications from prompt injection
- [Guardrails AI](https://www.guardrailsai.com/)

### Personal Security

- Passwort-Generator: **[XKPasswd](https://xkpasswd.net/s/)**, integriert in [**KeePass** 2](https://keepass.info/download.html) \[choco install keepass\], etc. pp.
	- Password Cards: [**PasswordCard**.org](https://www.passwordcard.org/) | [Password Cards by Savernova](https://www.savernova.com/en/solutions/secure-password-card/cards) | [Password Cards by helight.com](https://password-cards.helight.dev/)
- Passwortlisten-Selbstcheck:
	- Kontinuierliches Monitoring: Troy Hunt **[Have I Been Pwned](https://haveibeenpwned.com/)**, Firefox **[Monitor](https://monitor.mozilla.org/)**
	- Report: Hasso-Plattner-Institut **[HPI Identity Checker](https://sec.hpi.de/ilc/)** (einmal pro Tag)
	- Querying: **[search.0t.rocks](https://search.0t.rocks/)**, [**breachdirectory**.org](https://breachdirectory.org/), (€: [DeHashed](https://www.dehashed.com/), [snusbase.com](https://snusbase.com/), und andere)
- Anti-Virus: Mehrere [**kostenlose Anti-Virus**-Möglichkeiten](https://www.safetydetectives.com/blog/best-really-free-antivirus-for-windows/), u.a. [**Panda** Free Antivirus](https://www.pandasecurity.com/security-promotion/?reg=DE&campaign=free2007C) \[**choco install pandafreeantivirus**\]
- Hardening
	- **[0patch](https://0patch.com)** \[choco install 0patch\]: micropatches to fix software vulnerabilities in various, even closed source products
	- **[HardeningKitty](https://github.com/0x6d69636b/windows_hardening/)**: supports guidelines from Microsoft, CIS Benchmarks, DoD STIG and BSI SiSyPHuS Win10
	- **[hardentools](https://github.com/securitywithoutborders/hardentools)** \[**choco install hardentools**\]: collection of simple utilities designed to disable a number of "features" exposed by Microsoft Windows
	- [Windows-Optimize-Harden-Debloat Script](https://simeononsecurity.com/github/windows-optimize-harden-debloat/) \[**iwr -useb 'https://simeononsecurity.com/scripts/windowsoptimizeandharden.ps1'|iex**\]
	- Firefox: [FireFox-Privacy-Script](https://github.com/simeononsecurity/FireFox-Privacy-Script), [FireFox-STIG-Script](https://github.com/simeononsecurity/FireFox-STIG-Script), [ffprofile](https://ffprofile.com/), [privacytools.io](https://www.privacytools.io/browsers/#about_config), [SimeonOnSecurity: Plugin Recommendations](https://simeononsecurity.ch/recommendations/browser_plugins/)
- **[Portmaster](https://safing.io/download/)** \[**choco install portmaster**\]: open-source application that puts you back in charge over all your computer's network connections
- **PGP** / GnuPG? **[gpg4win](https://www.gpg4win.org/)** \[**choco install gpg4win**\], v.a. [Kleopatra](https://apps.kde.org/de/kleopatra/) sowie [GnuPG](https://gnupg.org/), [GpgEX](https://www.openhub.net/p/gpgex), [GPA](https://www.gnupg.org/related_software/gpa/index.html), [GpgOL](https://gpg4win.org/doc/en/gpg4win-compendium_33.html)
	- E-Mail Encryption: [openpgp.org Übersicht](https://www.openpgp.org/software/)
- DNS: Malware-filtering
	- **[Quad9](https://quad9.net)**: Schweizer DNS-Provider, exzellentes Malware-filtering
	- **[Mullvad](https://mullvad.net/de/help/dns-over-https-and-dns-over-tls/)**: schwedischer VPN-Provider mit diversen DNS-Varianten
	- **[Control D](https://controld.com/free-dns)**: amerikanischer DNS-Provider; Obacht wegen Anforderungen der US-Administration
	- (Die No-Logging und Anti-Ads/Trackers DNS Server sind unten bei Privacy)
	- Weiterführende Referenzen: Privacy Handbuch [DNS-Server](https://www.privacy-handbuch.de/handbuch_93d.htm)
- Dezentralized E2E-encrypted Instant Messaging?
	- **[XMPP](https://xmpp.org)** (aka [Jabber](http://www.jabber.org)): [Software-Liste](https://xmpp.org/software/), insbesondere **[Conversations](https://play.google.com/store/apps/details?id=eu.siacs.conversations)** (Android-Client) und **[wiuwiu](https://wiuwiu.de/)** ([Web-Client](https://social.wiuwiu.de/) und Hosting)
	- ([Matrix](https://matrix.org)? Software-Liste u.a. für [Clients](https://matrix.org/clients/) und [Hosting](https://matrix.org/hosting/) => Better-than-WhatsApp but still with several severe [Data Privacy problems / GDPR problems](https://github.com/libremonde-org/paper-research-privacy-matrix.org) => Vector [status blog](https://www.matrix.org/blog/2019/09/27/privacy-improvements-in-synapse-1-4-and-riot-1-4))
- Checker:
	- **[IsLegitSite](https://www.islegitsite.com/)** oder **[ScamAdvisor](https://www.scamadviser.com/)**: Plausibilisieren Sie, ob eine Website legal ist oder ein Betrug, überprüfen Sie den Ruf der Website
- Betriebssysteme
	- Desktop: **[Qubes OS](https://www.qubes-os.org/)** / [HardenedBSD](https://hardenedbsd.org/content/easy-feature-comparison)
	- Android: **[GrapheneOS](https://grapheneos.org/)**
- Sandboxes:
	- Mail Attachments: **[Dangerzone](https://dangerzone.rocks/)** (inspiriert von [Qubes OS trusted PDF](https://blog.invisiblethings.org/2013/02/21/converting-untrusted-pdfs-into-trusted.html))
	- Generische Anwendungen: [**Sandboxie** Plus](https://github.com/sandboxie-plus/Sandboxie) \[**choco install sandboxie-plus.install**\], Microsoft **[Windows Sandbox](https://learn.microsoft.com/windows/security/threat-protection/windows-sandbox/windows-sandbox-overview)**, \[**Enable-WindowsOptionalFeature -FeatureName "Containers-DisposableClientVM" -All -Online**\]
- Mobiltelefon vs. Custom Firmware
	- **[mAid](https://maid.binbash.rocks/dl.html)** (= Manage Android): Linux Distribution zur Wartung von Mobiltelefonen (früher bekannt als „FWUL“ = „Forget Windows Use Linux“), u.a. für [adb und fastboot](https://wiki.lineageos.org/adb_fastboot_guide)

## Privacy

### Professional Privacy

- **[Anonimatron](https://realrolfje.GitHub.io/anonimatron/)**: Open-Source Data Anonymization
- **[DataBunker](https://github.com/securitybunker/databunker)**: Open-Source Data Protection Platform
	- Alternative: (€) bspw. [Protegrity](https://www.protegrity.com/)
- [**Kodex** Community Edition](https://github.com/kiprotect/kodex): Open-Source Toolkit for Privacy and Security Engineering
- Privacy vs. Machine Learning:
	- **[TensorFlow Privacy](https://github.com/tensorflow/privacy)**
- Weiterführende Quellen: [Awesome Privacy Engineering](https://github.com/mplspunk/awesome-privacy-engineering) | [Awesome GDPR](https://github.com/bakke92/awesome-gdpr) #1 | [Awesome GDPR](https://github.com/erichard/awesome-gdpr) #2

### Personal Privacy

- Digital Footprint
	- Open-Source Intelligence (OSINT): [Awesome OSINT](https://github.com/jivoi/awesome-osint)
	- **[Have I been Pwned?](https://haveibeenpwned.com/)** ⭐: Check if your email or phone is in a data breach
	- **[Have I been Trained?](https://haveibeentrained.com/)** ⭐: Check if a picture is in an AI model
	- Discover: "Username used on which plattform?"
		- Cloud (free): [WhatsMyName Web](https://whatsmyname.app/), [Namech_k](https://namechk.com/namechk-plugin-search-results/) » Check Usernames
		- Cloud (€): [sherlockeye.io](https://www.sherlockeye.io/) (very goode UI/UX)
		- Desktop: **[blackbird](https://github.com/p1ngul1n0/blackbird)** ⭐, [sherlock](https://github.com/sherlock-project/sherlock)
		- Web/Self-Hosted: [WhatsMyName](https://github.com/WebBreacher/WhatsMyName)
		- Generic "Delete Account"-URL-Lists: [justdeleteaccount](https://www.justdeleteaccount.com/) ([github](https://github.com/mueller-lukas/justdeleteaccount_com)), US-zentrisch: [accountkiller](https://www.accountkiller.com/en/popular)
	- Discover: "E-Mail used on which plattform?" (i.a., using the forgotten password function)
		- Cloud (€): [sherlockeye.io](https://www.sherlockeye.io/)
		- Desktop: [Holehe](https://github.com/megadose/holehe) ⭐ \[**pip install holehe**\], [blackbird](https://github.com/p1ngul1n0/blackbird)
	- Data Privacy Management / DSGVO-Anfragen und -Löschantrag
		- Open Source: [Data Requests Generator](https://www.datarequests.org/generator/) ([Open Source](https://www.datarequests.org/open-source/))
		- Juristisch: [Privacy ReClaim](https://www.privacyreclaim.com/)
		- Abo: (€) [Mine](https://www.saymine.com/mineapp)
		- Anti-Data-Broker (€): **[Incogni](https://incogni.com/)** ⭐, [DeleteMe](https://joindeleteme.com/), [IDX Consumer Protection](https://www.idx.us/privacy-identity-protection) (iOS-only: [Kanary](https://www.thekanary.com/))
- Windows Prisvacy Hardening
	- **[WPD](https://wpd.app/)**: Windows Privacy Dashboard ⭐ \[choco install wpd\], einfache Deaktivierung der Windows-Telemetrie, Verwendende Level "Standard"
	- **[toptout](https://github.com/beatcracker/toptout)**: Anti-Telemetry für eine Unzahl an Applikationen und Diensten, jenseits von Windows-per-se
		```powershell
		Invoke-WebRequest -Uri "https://raw.githubusercontent.com/beatcracker/toptout/master/examples/toptout_pwsh.ps1" -OutFile "toptout_pwsh.ps1"
		.\toptout_pwsh.ps1 -Env -Exec -ShowLog
		```
	- **[privacy.sexy](https://privacy.sexy/)** ⭐: per CMD-Script-Ausführung, Verwendende Level "Standard"
		- Für Fortgeschrittene: **[W10Privacy](https://www.w10privacy.de/)** \[choco install w10privacy\]
- Mobile Phone Privacy Hardening
	- Android: [Techlore Video](https://www.youtube.com/watch?v=dMWEym0KPcA)
		- To be considered: [GrapheneOS](https://grapheneos.org/), [CalyxOS](https://calyxos.org/)
	- Apple: [The Ultimate iOS Hardening Guide](https://github.com/iAnonymous3000/iOS-Hardening-Guide) | [Techlore Video](https://www.youtube.com/watch?v=d2bJVKcIEg0)
- Windows Privacy Cleansing
	- **[PrivaZer](https://privazer.com/)** \[**choco install privazer.install**\]: Free PC cleaner & Privacy tool that cleans unwanted traces
- Web Privacy Protection
	- Anti-Tracker:
		- Browser: **[Privacy Badger](https://privacybadger.org/)**
		- Router: **[eBlocker](https://eblocker.org/)**
		- DNS: siehe folgenden Abschnitt DNS » Anti-Ads/Trackers
	- **[Tor Browser](https://www.torproject.org/download/)** \[**choco install tor-browser**\]: explore the internet with privacy
- DNS: Orthogonale Aspekte 1) Verschlüsseltes DNS, 2) No-Logging und 3) Anti-Ads/Trackers
	- Performance-Kontrolle: [DNSPerf](https://www.dnsperf.com/#!dns-resolvers)
	- Verschlüsseltes DNS:
		- Übersicht per [DNS Privacy Project](https://dnsprivacy.org/public_resolvers/)
	- No-Logging:
		- Privacy Handbuch [DNS-Server](https://www.privacy-handbuch.de/handbuch_93d.htm)
	- Anti-Ads/Trackers:
		- Ausgewähltes Szenario: 1) Handys, aber insbesondere 2) für Smart TVs und IoT-Geräte, dann DNS auf Router-Ebene, immer dann wenn keine eBlocker Trusted Root-CA installierbar ist
		- **[AdGuard DNS](https://adguard-dns.io/)**: DNS-Provider mit Sitz auf Zypern und v.a. westeuropäischen DNS-Servern
		- **[Mullvad](https://mullvad.net/de/help/dns-over-https-and-dns-over-tls/)**: schwedischer VPN-Provider mit diversen DNS-Varianten
		- **[Control D](https://controld.com/free-dns)**: amerikanischer DNS-Provider; Obacht wegen Anforderungen der US-Administration
	- (Die Anti-Malware DNS Server sind oben bei Security)
	- Nennenswert: Mit einem "keine Daten verkaufen" Privacy Statement
		- **[Cloudflare](https://1.1.1.1/de/)**: extrem hohe Geschwindigkeit; aber trotzdem aus Privacy-Sicht fragwürdig: Obacht vor Anforderungen der US-Administration
- Dienst-Alternativen:
	- Google Search » **[MetaGer](https://metager.org)**
	- YouTube » **[Invidious](https://invidious.io/)**, [PeerTube](https://joinpeertube.org/), [Odysee](https://odysee.com/)
	- Twitter/𝕏 » **[Nitter](https://nitter.net/)**, [Mastodon](https://joinmastodon.org/), [Misskey](https://misskey-hub.net/)
	- Reddit » **[Teddit](https://teddit.net/)**, [Lemmy](https://github.com/LemmyNet/lemmy)
	- Instagram » [Pixelfed](https://pixelfed.org/)
	- Facebook » [Diaspora](https://diasporafoundation.org/), [Friendica](https://friendi.ca/)
	- Spotify/Soundcloud » **[last.fm](https://www.last.fm/)**, [Funkwhale](https://funkwhale.audio/)
	- Disqus » [Cusdis](https://cusdis.com/)
	- Weiterführende Quelle: [Awesome Alternatives](https://github.com/LinuxCafeFederation/awesome-alternatives/)
- Policy-Checker:
	- [**tosdr**.org](https://tosdr.org/): Terms of Service Didn't Read
		- **[AGB Check-Tool](https://www.konsumentenschutz.ch/agb-check/)**: Prüfen Sie, ob Ihre AGB nachteilige Klauseln enthalten
	- **[Privacy Policy Checker](https://gdprwise.eu/policy-checker/)**: Prüft eine Website-Datenschutzrichtlinie auf Übereinstimmung mit der GDPR-Verordnung
- E-Mail Accounts (GMail-Exit/M365-Exit):
	- Empfehlungen: **[Tutanota](https://tutanota.com/)** (aus Hannover, kostenlose 1GB), **[Proton](https://proton.me/mail)** (aus der Schweiz, kostenlose 1GB)
		- Migration (kostenlos): Cloud-Dienst [OVH Mail Migrator](https://omm.ovh.net/)
		- Migration (€): [imapsync](https://imapsync.lamiral.info/) als [CLI-Tool](https://github.com/imapsync/imapsync) oder als [Cloud-Dienst](https://imapsync.lamiral.info/X/)
		- Backups (kostenlos): CLI [OfflineIMAP](https://github.com/OfflineIMAP/offlineimap3)
		- Backups (€): [Shoviv IMAP Email Backup and Restore](https://www.shoviv.com/imap-backup-and-restore.html) sowie [Advik Email Backup Wizard](https://www.adviksoft.com/email/backup.html) (Obacht: Advik mit Maschinen-gebundener Lizenz!)
		- Backups ([Linux-only](https://www.linux-magazin.de/ausgaben/2011/05/bitparade/)): [archivemail](https://archivemail.sourceforge.net/), [archiveopteryx](https://archiveopteryx.org/)
		- (Windows: [lokaler Dovecot IMAP-Server](https://doc.dovecot.org/main/installation/docker.html) per pwsh? `docker run -v "${PWD}:/srv/vmail" -p 143:31143 -p 993:31993 dovecot/dovecot:latest`)
	- Anonyme Einweg-Mail / 10-Minute-Mail: **[temp-mail.io](https://temp-mail.io/de)** (Browser-Ext., u.a. [Opera](https://addons.opera.com/extensions/details/temp-mail/)), [temp-mail.org](https://temp-mail.org/de/), (Browser-Ext., u.a. [Opera](https://addons.opera.com/extensions/details/temp-mail-disposable-temporary-email/)), [FakesMail](https://fakesmail.com/de) (Browser-Ext., u.a. [Opera](https://fakesmail.com/de)), [tempr.email](https://tempr.email/) (aus DE, aber ohne Browser-Integration), [uvm.](https://praxistipps.chip.de/wegwerf-email-adressen-diese-anbieter-gibts_1674)
	- E-Mail-Forwarder: **[ManyMe](https://manyme.com/)** (ohne Browser-Integration), [TrashMail](https://trashmail.com/) (Browser-Ext., u.a. [Opera](https://addons.opera.com/extensions/details/trashmailcom-create-disposable-address/)), etc. pp.
- Auto-Unsubscribe Newsletter: **[unsubscribe-gmail](https://github.com/labnol/unsubscribe-gmail)**, **[hatchet](https://github.com/AnalogJ/hatchet)**
	- (Im Kontext eines Gmail-Accounts benötigen praktisch alle Werkzeuge, außer unsubscribe-gmail, eine aktive [2FA](https://myaccount.google.com/security) des Gmail-Kontos)
	- Kostenbehaftete aber empfehlenswerte Alternative (€): **[Leave Me Alone](https://leavemealone.app/)**
	- Kostenlose Alternativen, aber diese Werkzeuge selbst sind DSGVO-problematisch (Dienstleister kriegt Zugang zum Konto und erhebt Statistiken, welche vermarktet werden): [Unroll.me](https://unroll.me/), [Cleanfox](https://www.cleanfox.io/) \[Eigentlich ist nur deren Namen zu kennen wichtig, dadurch kann man per MetaGer-Suche nach ­­­Alternativen zu Unroll.me suchen und dann so etwas wie Leave Me Alone finden…\]­
- Free Space Cleaner
	- **[sdelete](https://docs.microsoft.com/en-us/sysinternals/downloads/sdelete)** \[**choco install sdelete --version=1.61.0.20160210**\]: Sicheres Löschen von Dateien
		- (ich empfehle die Version 1.61; aber Obacht: die Parameter-Semantik hat sich zur 2.0 geändert, in 1.61 wird „-c“ für „zero free space“ verwendet bspw. „sdelete -c C: -nobanner“)
	- (auch Teil der [PrivaZer](https://privazer.com/)-Funktionalität, s. oben)
	- (auch das seit Windows 10 integrierte Werkzeug cipher unterstützt das mit der \/w: Option)
- **[ExifTool](https://exiftool.org/)** \[**choco install exiftool**\]: reading, writing and editing meta information (many [supported file types](https://exiftool.org/#supported))
- **[BatchPurifier](https://www.digitalconfidence.com/BatchPurifier.html)**: kostenpflichtiges aber wertvolles Werkzeug zur Metadaten-Tiefenreinigung („Sanitize“) von Büro- und Multimedia-Dateien
	- Auch für den persönlichen Gebrauch (~$19), ABER VORSICHT: "The number of computers on which you may activate this software may not exceed the number of computer licenses that you have purchased. Once a license is activated, it's tied to the specific computer and cannot be transferred to another. Regardless of the circumstances." (Also muss man bei einem Hardware-Wechsel seines PCs eine neue Lizenz kaufen; preislich auch privat machbar, aber seien Sie vorsensibilisiert, denn dieses Modell sind End-User nicht gewöhnt.)
- Weiterführende Quellen: [Privacy Tools](http://www.privacytools.io/) | [Awesome Privacy](https://github.com/pluja/awesome-privacy) #1 | [Awesome Privacy](https://github.com/paulaime/awesome-privacy) #2 | [Awesome Privacy](https://github.com/KevinColemanInc/awesome-privacy) #3

## Appendix: More Free Student Stuff

- [GitHub Student Developer Pack](https://education.github.com/pack)
- [discount-for-student-dev](https://github.com/AchoArnold/discount-for-student-dev)
- [A-to-Z-Resources-for-Students](https://github.com/dipakkr/A-to-Z-Resources-for-Students)

## Footer

### Future Work

I plan to translate this awesome list from German into English at some point.

### Contribute

What did I miss? Anything you recommend?

Contributions are most welcome, please adhere to the contribution guidelines and ensure your pull request adheres to the following guidelines:

- Make an individual pull request for each suggestion.
- Keep descriptions short and simple.
- Check your spelling and grammar.
- Make sure your text editor is set to remove trailing whitespace.
- Try to make your Pull request and title as descriptive as possible.
- New categories or improvements to the existing categorization are welcome.

Thank you for your suggestions!

### Backers

Thank you to all our supporters! 🙏

_Please, consider supporting my work as a lot of effort takes place to generate this list! Thanks a lot._

[![Donate via PayPal](https://img.shields.io/badge/Donate-PayPal-0070BA?style=for-the-badge&logo=paypal&logoColor=white)](https://www.paypal.com/donate/?hosted_button_id=QTDJ2JA58ZM9L)

[![Support on Ko‑fi](https://img.shields.io/badge/Support-Ko–fi-F16061?style=for-the-badge&logo=ko-fi&logoColor=white)](https://ko-fi.com/cyberlytics)

[![Buy Me A Coffee!](https://img.shields.io/badge/buy_me_a_coffee-FFDD00?style=for-the-badge&logo=buy-me-a-coffee&logoColor=black)](https://www.buymeacoffee.com/cyberpetaneuron)

### License

[![Creative Commons License](http://i.creativecommons.org/l/by/4.0/88x31.png)](http://creativecommons.org/licenses/by/4.0/)

This work is licensed under Creative Commons [CC BY 4.0](http://creativecommons.org/licenses/by/4.0/) .
