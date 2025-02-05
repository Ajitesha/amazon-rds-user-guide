# Analyzing running queries in Oracle<a name="USER_PerfInsights.UsingDashboard.AnalyzeDBLoad.AdditionalMetrics.Oracle"></a>

Amazon RDS for Oracle collects SQL statistics both at the statement and digest level\. At the statement level, the ID column represents the value of `V$SQL.SQL_ID`\. At the digest level, the ID column shows the value of `V$SQL.FORCE_MATCHING_SIGNATURE`\. 

If the ID is `0` at the digest level, Oracle Database has determined that this statement is not suitable for reuse\. In this case, the child SQL statements could belong to different digests\. However, the statements are grouped together under the `digest_text` for the first SQL statement collected\.

**Topics**
+ [Per\-second statistics for Oracle](#USER_PerfInsights.UsingDashboard.AnalyzeDBLoad.AdditionalMetrics.Oracle.per-second)
+ [Per\-call statistics for Oracle](#USER_PerfInsights.UsingDashboard.AnalyzeDBLoad.AdditionalMetrics.Oracle.per-call)
+ [Viewing SQL statistics for Oracle](#USER_PerfInsights.UsingDashboard.AnalyzeDBLoad.AdditionalMetrics.AnalyzingSQLLevel)

## Per\-second statistics for Oracle<a name="USER_PerfInsights.UsingDashboard.AnalyzeDBLoad.AdditionalMetrics.Oracle.per-second"></a>

The following metrics provide per\-second statistics for an Oracle SQL query\.


| Metric | Unit | 
| --- | --- | 
| db\.sql\.stats\.executions\_per\_sec | Number of executions per second | 
| db\.sql\.stats\.elapsed\_time\_per\_sec | Average active executions \(AAE\) | 
| db\.sql\.stats\.rows\_processed\_per\_sec | Rows processed per second | 
| db\.sql\.stats\.buffer\_gets\_per\_sec | Buffer gets per second | 
| db\.sql\.stats\.physical\_read\_requests\_per\_sec | Physical reads per second | 
| db\.sql\.stats\.physical\_write\_requests\_per\_sec | Physical writes per second | 
| db\.sql\.stats\.total\_sharable\_mem\_per\_sec | Total shareable memory per second \(in bytes\)  | 
| db\.sql\.stats\.cpu\_time\_per\_sec | CPU time per second \(in ms\) | 

The following metrics provide per\-call statistics for an Oracle SQL digest query\.


| Metric | Unit | 
| --- | --- | 
| db\.sql\_tokenized\.stats\.executions\_per\_sec | Number of executions per second | 
| db\.sql\_tokenized\.stats\.elapsed\_time\_per\_sec | Average active executions \(AAE\) | 
| db\.sql\_tokenized\.stats\.rows\_processed\_per\_sec | Rows processed per second | 
| db\.sql\_tokenized\.stats\.buffer\_gets\_per\_sec | Buffer gets per second | 
| db\.sql\_tokenized\.stats\.physical\_read\_requests\_per\_sec | Physical reads per second | 
| db\.sql\_tokenized\.stats\.physical\_write\_requests\_per\_sec | Physical writes per second | 
| db\.sql\_tokenized\.stats\.total\_sharable\_mem\_per\_sec | Total shareable memory per second \(in bytes\)  | 
| db\.sql\_tokenized\.stats\.cpu\_time\_per\_sec | CPU time per second \(in ms\) | 

## Per\-call statistics for Oracle<a name="USER_PerfInsights.UsingDashboard.AnalyzeDBLoad.AdditionalMetrics.Oracle.per-call"></a>

The following metrics provide per\-call statistics for an Oracle SQL statement\.


| Metric | Unit | 
| --- | --- | 
| db\.sql\.stats\.elapsed\_time\_per\_exec | Elapsed time per executions \(in ms\)  | 
| db\.sql\.stats\.rows\_processed\_per\_exec | Rows processed per execution | 
| db\.sql\.stats\.buffer\_gets\_per\_exec | Buffer gets per execution | 
| db\.sql\.stats\.physical\_read\_requests\_per\_exec | Physical reads per execution | 
| db\.sql\.stats\.physical\_write\_requests\_per\_exec | Physical writes per execution | 
| db\.sql\.stats\.total\_sharable\_mem\_per\_exec | Total shareable memory per execution \(in bytes\) | 
| db\.sql\.stats\.cpu\_time\_per\_exec | CPU time per execution \(in ms\) | 

The following metrics provide per\-call statistics for an Oracle SQL digest query\.


| Metric | Unit | 
| --- | --- | 
| db\.sql\_tokenized\.stats\.elapsed\_time\_per\_exec | Elapsed time per executions \(in ms\)  | 
| db\.sql\_tokenized\.stats\.rows\_processed\_per\_exec | Rows processed per execution | 
| db\.sql\_tokenized\.stats\.buffer\_gets\_per\_exec | Buffer gets per execution | 
| db\.sql\_tokenized\.stats\.physical\_read\_requests\_per\_exec | Physical reads per execution | 
| db\.sql\_tokenized\.stats\.physical\_write\_requests\_per\_exec | Physical writes per execution | 
| db\.sql\_tokenized\.stats\.total\_sharable\_mem\_per\_exec | Total shareable memory per execution \(in bytes\) | 
| db\.sql\_tokenized\.stats\.cpu\_time\_per\_exec | CPU time per execution \(in ms\) | 

## Viewing SQL statistics for Oracle<a name="USER_PerfInsights.UsingDashboard.AnalyzeDBLoad.AdditionalMetrics.AnalyzingSQLLevel"></a>

The statistics are available in the **Top SQL** tab of the **Database load** chart\.

**To view the SQL statistics**

1. Open the Amazon RDS console at [https://console\.aws\.amazon\.com/rds/](https://console.aws.amazon.com/rds/)\.

1. Go to the Performance Insights dashboard\.

1. Choose the **Top SQL** tab\.

1. Choose a digest query or individual statement\.  
![\[Viewing metrics for running queries\]](http://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/./images/perf_insights_per_sql_sql.png)

1. Choose which statistics to display by choosing the gear icon in the upper\-right corner of the chart\.

   The following screenshot shows the preferences for Oracle DB instances\.  
![\[Preferences for metrics for running queries for Oracle DB instances\]](http://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/./images/perf_insights_per_sql_pref_oracle.png)

   The following screenshot shows the statistics for a SQL statement\.  
![\[Statistics for a SQL statement\]](http://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/./images/perf_insights_per_sql_stats_oracle.png)