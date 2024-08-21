# Data understanding

The data understanding phase involves four steps, including the collection of initial data, the description of data, the exploration of data, and the verification of data quality.

# Data collection (or acquisition)

Here a data analyst acquires the necessary data, including loading and integrating this data if necessary.
The analyst should make sure to report problems encountered and his or her solutions to aid with future replications of the project.
For instance, data may have to be collected from several different sources, and some of these sources may have a long lag time.
It is helpful to know this in advance to avoid potential delays.

- The analyst then proceeds to increase familiarity with the data,
- to identify data quality problems, to discover initial insights into the data,
- or to detect interesting subsets to form hypotheses about hidden information.

Still today, this is one of the most important steps for many companies:

- «Data is the new oil of the Digital Economy»
- Indeed, there are several disciplines focusing on data (Data Science, Data Mining, Big data, ...)
- However, acquiring data is a time-consuming, investment and knowledge-intensive process
- In Europe (but now in many areas of the world), there can be problems related to privacy
    - When is it “right” to protect privacy? When does it become a limit?

## Public Datasets

We can get data mainly in two ways:

1. By using publicly available data (datasets or databases) → someone collected them for us!
    - They can be free or for a fee
    - The quality of the data made available must be checked
1. By acquiring a new set of data, but why?
    - It is not certain that public data well represent the problem we want to solve
    - We want to acquire specific data and thus generate specific expertise for the company (know-how)
    - We are forced to acquire data that due to their sensitive nature would not otherwise be available (privacy issues)
    - The company we work for already has a data collection process that we can use

Many universities publicly release their datasets:

- There are no requirements related to profit or non-disclosure agreement (NDA)
  - It is a consolidated practice in the world of research
  - It is the basis of the scientific method, in particular for the reproducibility of the results obtained
  - I release my data so that others can conduct my own experiments, verifying my results and perhaps proposing better solutions!
  - Examples:
    - https://www.image-net.org/ 

Other platforms make datasets available for competitions:

- Kaggle: https://www.kaggle.com/datasets 
- https://medium.datadriveninvestor.com/kaggle-data-science-platform-alternatives-for-competitions-and-research-cbe051596e62 

## Acquisition of a new dataset

Acquiring a new dataset is usually a costly process!

- Investment of time and money for:
  - Programming or learning to use an acquisition tool
  - Handling of large amounts of data
  - Testing to find any bugs that could compromise the success of the acquisition (and we often notice them at the end of the process)
  - Acquire new hardware for data collection and storage

- It is necessary to carefully consider whether it is appropriate to acquire a new dataset.
  - Considerations not only in engineering, but also in management and economics.
  - Future needs must be foreseen in advance.

## Data Collection: Case Study in Precision Agriculture

:::: {.columns}
::: {.column width="60%"}

> Brown spot of European pear
>
> - A company wants to track the spreading of Brown spot of European pear in Emilia Romagna.
> - Brown spots are caused by a fungus (Stemphylium vesicarium) damaging pear fruits and causing economy loss for producers.
> - Also, the company wants to find out if there are environmental factors related to the spreading of such fungus.

How would you address this problem?
:::
::: {.column width="40%"}
![](https://agricoltura.regione.emilia-romagna.it/fitosanitario/temi/avversita/schede/avversita-per-nome/immagini-e-documenti/maculatura-bruna-del-pero/sui-frutti-l2019area-necrotica-si-circonda-spesso-di-alone-rossastro)
:::
::::

---

> The company prepares a questionnaire on paper with around 100 questions, and one of the employees moves across Emilia-Romagna to ask questions to the farmers and collect their answers. 

In your opinion, what are the pros/cons of this solution?

---

> Once the employee has collected almost 100 questionnairs, the company company ask us to apply machine learning techniques to understand which environmental conditions could be related to the spreading of the fungus.

If you were the analyst, what would you do?

---

> To us, it is impossible to apply machine learning techniques to data un paper.
> We prepared a Google Form where answers could be digitalized.
> 
> The employee would take ~1 month to return us the digitalized questionnaires.
> 
> Issue #1: some answers where inconsistent with the provided options.
>
> Issue #2: what about open questions?
>
> Issue #3: what about the trustworthiness of the data? E.g., there are some pesticides/fertilizers whose application is constrained by the Italian/European laws. Can we trust the answers to these questions?
>
> Issue #4: we have a dataset of 100 features (assuming for simplicity that each question can be simply turned into an attribute), and a dataset of 100 data.

Outcome?

- This project was missing a proper plan (business+data understanding), and turned out to be a failure for the company.
- Even if we apply ML techniques to the data, the result we get are not statistically relevant.

## Data Annotation

NB: acquiring a new dataset does not mean acquiring only new data!

Indeed, one of the most relevant aspects is the annotation of the data

- The specific annotation is usually called “label” and is the (semantic) content of the data.
- The label depends on the problem we want to solve and can be numerical or categorical
- Examples:
  - A person's height prediction → data: joint lengths, label: height (cm)
  - Pedestrian Detection → data: images, label: presence of a pedestrian (yes/no)
  - Pedestrian Localization → data: images, label: position of the pedestrain (x, y, w, h)
  - Audio classification numbers → data: audio sequences, label: number («five»)

A single data is therefore defined as annotated if it is associated with a label

- Data collected without correct and timely annotation is often useless
- However, it is also possible to “extract knowledge” from un-annotated data through, for instance, clustering

## Data Annotation Process

The data annotation process can take place in several ways:

- *Manual*: each data is manually annotated
  - Long and expensive process
  - The quality of the annotations is usually controllable and high
  - This is not always an applicable process (for example, is it possible to annotate a dataset with 1M of images?)
- *Automatic*: each data is automatically annotated, using specific tools
  - It is based on particular a priori knowledge (for example, all images acquired in a dog shelter depict dogs).
  - The quality of the annotations is not always easily controlled
- *Third parties*: all data is noted by a third party
  - Free of charge: this is the case, for example, in which users barter the free use of some platform with the transfer of their annotated data (for example, photos uploaded - to Facebook accompanied by information regarding the content, the position of the face, or scene acquired).
  - Paid: there are platforms where is possible to purchase annotation time from third parties (often from “developing countries”). Example: Amazon Mechanical Turk

## Amazon Mechanical Turk

[Amazon Mechanical Turk](https://www.mturk.com/)

![image](https://github.com/user-attachments/assets/4b272c03-7fca-4338-a112-02859d5cfe70)


## Different Ways of Learning

:::: {.columns}

::: {.column width="60%"}

We define different types of learning depending on data annotation:

- Annotated data → Supervised Learning
  - One of the most studied types that allows to obtain the best results

- Not annotated data → Unsupervised Learning
  - The results that can be obtained are usually worse than the previous case

- Partially annotated data → Semi-Supervised Learning

Specific algorithms correspond to each of these areas

- The best performances are usually obtained with supervised trained algorithms
- In this course, we will mainly work on fully annotated data → Supervised Learning

:::
::: {.column width="40%"}

![image](https://github.com/user-attachments/assets/50c6092b-43cd-4dbe-95c1-c0d9494803e6)

![image](https://github.com/user-attachments/assets/e6d4832d-902c-49c3-8c62-a1948517bb7e)

:::
::::

## Open and Closed Sets

Last aspect to be defined relating to data annotation: do we know all annotations?

Closed Set: it is assumed that the pattern to be classified belongs to one of the known classes.

- The most common case in machine learning benchmarks
- Ideal condition, but not always suitable for real-world systems

Open Set: the patterns to be classified can belong to none of known classes. 

- More realistic condition, but more challenging
- Example: classify all fruits into {pears, bananas}

Two possible solutions to the open set problem:

- An additional fictitious class is added to the classes (“the rest of the world”, “unknown”) and the so-called “negative examples” are added to the training set.
- You allow the system not to assign the pattern. To this end, a threshold is defined and the pattern is assigned to the most likely class only when the probability is higher than the threshold.

## Common problems in Data Acquisition

Companies usually face common problems: 

- The business process produces huge amounts of data
  - It is almost impossible to acquire all the data
  - Also, physical limitations when the data stream is bigger that the storing capacity
  - Usually, it is necessary to choose which ones to store
- Sometimes companies have a lot of “old” data in their databases or information systems: 
  - They don't know what to do with it
  - Data re-collection on existing data (since data must be clean or something similar)
- In many business processes it is unclear understanding:
  - Which data is possible to collect (also due to privacy issues)
  - Which data is (really) useful for the business

## Common Probles on Data Collection

The business process produces huge amounts of data

- It is almost impossible to acquire all the data
- Also, physical limitations when the data stream is bigger that the storing capacity
- Usually, it is necessary to choose which ones to store

Sometimes companies have a lot of “old” data in their databases or information systems: 

- They don't know what to do with it
- Data re-collection on existing data (since data must be clean or something similar)

In many business processes it is unclear understanding:

- Which data is possible to collect (also due to privacy issues)
- Which data is (really) useful for the business

# Describe the Data

During this step, the data analyst examines the “gross” or “surface” properties of the acquired data and reports on the results, examining issues such as the format of the data, the quantity of the data, the number of records and fields in each table, the identities of the fields, and any other surface features of the data.

- The key question to ask is: Does the data acquired satisfy the relevant requirements?
  - For instance, if age is an important field and the data does not reflect the entire age range, it may be wise to collect a different set of data.
- This step also provides a basic understanding of the data on which subsequent steps will build.

# Explore the Data

This task tackles the data mining questions, which can be addressed using querying, visualization, and reporting.

- For instance, a data analyst may query the data to discover the types of products that purchasers in a particular income group usually buy.
- Or the analyst may run a visualization analysis to uncover potential fraud patterns.
- The data analyst should then create a data exploration report that outlines first findings, or an initial hypothesis, and the potential impact on the remainder of the project

# Verify Data Quality

At this point, the analyst examines the quality of the data, addressing questions such as:

- Is the data complete? Missing values often occur, particularly if the data was collected across long periods of time.
- Some common items to check include: missing attributes and blank fields;
- whether all possible values are represented;
- the plausibility of values;
- the spelling of values;
- and whether attributes with different values have similar meanings (e.g., low fat, diet).

The data analyst also should review any attributes that may give answers that conflict with common sense (e.g., teenagers with high income).