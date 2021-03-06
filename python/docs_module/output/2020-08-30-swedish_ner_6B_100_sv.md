---
layout: model
title: 
author: John Snow Labs
name: swedish_ner_6B_100
class: NerDLModel
language: sv
repository: public/models
date: 30/08/2020
tags: [ner]
article_header:
   type: cover
use_language_switcher: "Python-Scala-Java"
---

{:.h2_title}
## Description 




{:.btn-box}
<button class="button button-orange" disabled>Live Demo</button><br/><button class="button button-orange" disabled>Open in Colab</button><br/>[Download](https://s3.amazonaws.com/auxdata.johnsnowlabs.com/public/models/swedish_ner_6B_100_sv_2.6.0_2.4_1598810268071.zip){:.button.button-orange.button-orange-trans.arr.button-icon}<br/>

## How to use 
<div class="tabs-box" markdown="1">

{% include programmingLanguageSelectScalaPython.html %}

```python

    embeddings = WordEmbeddingsModel.pretrained(glove_100d, lang=en)
    embeddings.setInputCols(["sentence", 'token'])
    embeddings.setOutputCol("embeddings")

    ner = NerDLModel.pretrained(swedish_ner_6B_100, lang=sv)
    ner.setInputCols(["sentence", "token", "embeddings"])
    ner.setOutputCol("ner")

    ner_converter = NerConverter()
    ner_converter.setInputCols(["sentence", "token", "ner"])
    ner_converter.setOutputCol("ner_chunk")
                      
    pipeline = Pipeline(stages=[ documentAssembler, 
                                    sentenceDetector,
                                    tokenizer,
                                    embeddings,
                                    ner,
                                    ner_converter
                                     ])
    
    pipeline_model = pipeline.fit(spark.createDataFrame([['']]).toDF("text"))
    lmodel = LightPipeline(pipeline_model)
    
    result = lmodel.fullAnnotate("Mona Lisa är en oljemålning från 1500-talet skapad av Leonardo. Det hålls på Louvren i Paris.")[0]
    
```

```scala

```
</div>

{:.h2_title}
## Results
```bash
+-------------+---------+-------+----------+
| ner_chunk   |   begin |   end | entity   |
+=============+=========+=======+==========+
| Mona Lisa   |       0 |     8 | PER      |
+-------------+---------+-------+----------+
| Leonardo    |      54 |    61 | PER      |
+-------------+---------+-------+----------+
| Louvren     |      77 |    83 | ORG      |
+-------------+---------+-------+----------+
| Paris       |      87 |    91 | LOC      |
+-------------+---------+-------+----------+
```

{:.model-param}
## Model Information

{:.table-model}
|-------------------------|--------------------|
| Model Name              | swedish_ner_6B_100 |
| Model Class             | NerDLModel         |
| Spark Compatibility     | 2.6.0              |
| Spark NLP Compatibility | 2.4                |
| License                 | open source        |
| Edition                 | public             |
| Input Labels            |                    |
| Output Labels           |                    |
| Language                | sv                 |
| Dimension               |                    |
| Case Sensitive          |                    |
| Upstream Dependencies   | glove_100d         |




{:.h2_title}
## Data Source



