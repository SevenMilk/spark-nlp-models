---
layout: model
title: Relation Extraction Model Clinical
author: John Snow Labs
name: 
class: 
language: 
repository: clinical/models
date: 2020-08-18
tags: [clinical,events,relation,extraction,temporal,en]
article_header:
   type: cover
use_language_switcher: "Python-Scala-Java"
---

{:.h2_title}
## Description 


 {:.h2_title}
## Predicted Entities
Extracts: Temporal relations (BEFORE, AFTER, SIMULTANEOUS, BEGUN_BY, ENDED_BY, DURING, BEFORE_OVERLAP) between clinical events (`ner_events_clinical`) 

{:.btn-box}
<button class="button button-orange" disabled>Live Demo</button><br/>[Open in Colab](https://colab.research.google.com/github/JohnSnowLabs/spark-nlp-workshop/blob/master/tutorials/Certification_Trainings/Healthcare/10.Clinical_Relation_Extraction.ipynb){:.button.button-orange.button-orange-trans.co.button-icon}<br/>[Download](https://s3.amazonaws.com/auxdata.johnsnowlabs.com/clinical/models/re_temporal_events_enriched_clinical_en_2.5.5_2.4_1597775105767.zip){:.button.button-orange.button-orange-trans.arr.button-icon}<br/>

## How to use 
<div class="tabs-box" markdown="1">

{% include programmingLanguageSelectScalaPython.html %}

```python

```

```scala

```
</div>



{:.model-param}
## Model Information
{:.table-model}
|-------------------------|-----------------------------------------|
| Model Name              | re_temporal_events_enriched_clinical    |
| Model Class             | RelationExtractionModel                 |
| Spark Compatibility     | 2.5.5                                   |
| Spark NLP Compatibility | 2.4                                     |
| License                 | Licensed                                |
| Edition                 | Official                                |
| Input Labels            | word_embeddings, chunk, pos, dependency |
| Output Labels           | category                                |
| Language                | en                                      |
| Case Sensitive          | False                                   |
| Upstream Dependencies   | embeddings_clinical                     |





{:.h2_title}
## Data Source
Trained on data gathered and manually annotated by John Snow Labs.

