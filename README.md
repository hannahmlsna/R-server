### Contents

| 1R Server |
| --- |
| 1.1What is R Programming? |
| 1.2Benefits of R |
| 1.3Limitations of R |
| 1.4Microsoft R Family |
| |

1. 1R Server
------
### 1. 1.1 What is R Programming?

R is an open sourced programming language that was built for statistical computing. It excels at data analysis, has built in graphics support, and has friendly treatment of tabular data structures.

R is a tool of choice for data miners, data analysts, and data scientist. The rise of R follows together with the rise of data science in enterprise. Per the TIOBE index, which tracks the popularity of programming languages, R has had an explosion in adoption since 2014. It is now one of the most popular programming languages in the world when it comes to data science and machine learning.

![Image of R popularity](https://cloud.githubusercontent.com/assets/26171849/23569297/5b8c7290-0013-11e7-86e6-87bbd4f0697f.png)

_R&#39;s rise in popularity overtime_

### 1. 1.2 Benefits of R

**Dataset friendly:** Its greatest strength is that it greatly improves efficiency of development time. As you do not have to formulate loops nearly quite as often in any programming language. You can call a ```mean()``` or a ```sum``` function on the entirety of a column of a dataset without having to build a nested loop.

**Easy to learn:** R feels very natural for someone used to Excel or SQL since R treats data as rows and columns rather than individual variables or data structures to be looped over. Also, since R is a higher-level programming language like Python or JavaScript it is much easier to pick up. Since a lot of the more mundane tasks have been abstracted away, like garbage collection, variable typing, formulating many loops, or handling many exemptions.

**Large Community:** for an open sourced technology to become useful it must have a large community that helps improve and make the technology better. R has gained enough following to receive a critical mass for an open sourced technology. Thus, practitioners of R will have the benefit a well hydrated support community such as StackOverflow and other public writings. R also has more than ten thousand free and open sourced packages on [CRAN](https://cran.r-project.org/). CRAN is the community that curates and distributes R packages. The number of R packages on CRAN have risen exponentially over the years.

![Image of R packages](https://cloud.githubusercontent.com/assets/26171849/23569352/b397b3b4-0013-11e7-9ff4-bacc291740f4.png)

### 1. 1.3 Limitations of R

As much of a force and a movement that open sourced R has been, the programming language itself lacks the power and efficiency that other programming languages possess. R has always had constraints around scaling out to big data. The four biggest constraints of R are listed below:

- **Single Core** : R only runs on a single core. Normally computer programs that utilize other languages can break a task into chunks and have it be executed on parallel on another core, greatly speeding up the operation or computation. For example, if you had to traversing 200 decision trees of a decision forest model, and you had four cores. Each core would split the load of all the trees and the job would run 4 times faster. With R, each of the 200 trees would take their turn sequentially through a single core, ignoring any cores that may wish to help. As data grows in width and length, this parallelism is crucial to creating models in a timely manner. It also makes it so open source R cannot be utilized during a high-performance compute instance. Or simple use cases where you may simply just wish to rent a 32-core virtual machine from the cloud to speed up the job since 31 of those cores would be useless to R.
- **Sequential Processing:** even within a single core, a computation can be parallelized by utilizing multiple threads. R must process everything sequentially within a single thread within a single core.
- **In-memory compute:** R must see the entirety of a file and have it be read into memory (RAM) for it to be processed. It lacks the ability to process things as a stream of a file. What this means is that you are severely bottlenecked by the size of how much memory you have on your machine. On top of which, the R data frame tends to bloat up files by 3 times. So, users with 8 GBs of ram can only hope to work on files around 1.4 GB in size. Users can perform a quick fix to this problem by simply renting a machine with much larger memory. However even that would have its limits since the VM with the largest RAM that one can currently rent from Azure has 448 GB of RAM. Hardly practical for big data scenarios.
- **Cannot be distributed:** R cannot even be distributed within a single computer let alone across multiple computers. However, the current trend in solving big data is not to scale up but to scale wide. You must use distributed computing frameworks like Hadoop or Spark, where you get a cluster of computers to parallelized a task because the task or data has outstripped the resources of a single machine.

What happens when you expand beyond a couple gigabytes of data? You packed up your data and you used something else; Python, Java, or Mahout to name a few. Now it&#39;s possible to stick with R throughout your production analysis all the way to deployment, regardless of the data size, even in a distributed Hadoop or Spark environment. Introducing Microsoft R Server.

### 1. 1.4 Microsoft R Family

Microsoft offers four product lines to support R by unlocking its limits and increasing its scope. The Microsoft R family has four products line offerings: SQL Server R, Microsoft R Server, Microsoft R, and Microsoft R Open.

![Image of Microsoft R](https://cloud.githubusercontent.com/assets/26171849/23569667/3f184cf4-0015-11e7-9d71-3ac362522b27.png)

Microsoft R Server delivers enterprise class performance and scalability for your R-based applications with libraries that allow you to write once and deploy across multiple platforms with minimal effort, whether on-premises or in the cloud.

By using and extending open source R, Microsoft R Server is fully compatible with R scripts, functions and CRAN packages, to analyze data at enterprise scale. It also also addresses the in-memory limitations of open source R by adding parallel and chunked processing of data in Microsoft R Server, enabling users to run analytics on data much bigger than what fits in main memory. And since R Server is built on top of Microsoft R Open, you can use any open source R packages to build your analytics.
