模型的标示符存储在`hanlp.pretrained`此包中，按照NLP任务归类

## amr:为了支持抽象意义表示 (AMR) 模型
AMR3_SEQ2SEQ_BART_LARGE:
```AMR3_SEQ2SEQ_BART_LARGE
模型类型：基于Seq2Seq框架的BART大模型，用于AMR 3.0的解析任务。
训练资料：基于AMR 3.0数据集训练。
性能：在Smatch等多个评价指标上表现出色，但需要注意的是，该模型不执行wikification（维基链接预测）任务。
```
AMR3_GRAPH_PRETRAIN_PARSER:
```AMR3_GRAPH_PRETRAIN_PARSER
模型类型：同样是基于BART大模型的Seq2Seq架构，但增加了图预训练步骤。
训练资料：同样基于AMR 3.0数据集，但采用了图形预训练策略。
性能：据官方仓库显示为84.3，而在amr-evaluation-enhanced工具下评估略有下降，依然在多项评价指标上达到较高水平，同样不执行wikification任务。

```

MRP2020_AMR_ENG_ZHO_XLM_BASE:
```MRP2020_AMR_ENG_ZHO_XLM_BASE
模型类型：基于Permutation-invariant Semantic Parser的封装模型，使用了XLM-RoBERTa基础版本作为预训练模型。
训练资料：在MRP2020英语和中文AMR语料库上训练。
性能：在MRP2020竞赛中表现出色，但由于此处仅提供了基础版本，详细性能请参考原始论文。注意该模型在输入时需要提供token（词语）和lemmas（词根，仅对英语有效）。
```

MRP2020_AMR_ZHO_MENGZI_BASE:
```MRP2020_AMR_ZHO_MENGZI_BASE
模型类型：针对中文的Permutation-invariant Semantic Parser，采用了Mengzi BERT基础版本作为预训练模型。
训练资料：在MRP2020中文AMR语料库上训练。
性能：在开发集上表现优秀，提供了详细的各子任务F1得分，但由于测试集未公开，无法得知其在测试集上的性能。
```
AMR3_GRAPH_PRETRAIN_GENERATION：预训练好的大型AMR到文本（AMR2Text）生成模型

## classifiers:文本分类
1. CHNSENTICORP_BERT_BASE_ZH: 中文文本分类模型
2. SST2_ALBERT_BASE_EN: 英文文本分类模型
3. LID_176_FASTTEXT_BASE: FastText语言识别模型（176种语言，）
4. LID_176_FASTTEXT_SMALL：轻量级FastText语言识别模型

## constituency：汉语句法分析
1. CTB9_CON_ELECTRA_SMALL: 基于Electra小型预训练模型(:cite:clark2020electra)的CRF句法分析器，针对CTB9数据集中的主类别进行训练。
2. CTB9_CON_FULL_TAG_ELECTRA_SMALL: 同样基于Electra小型预训练模型的CRF句法分析器，但在这个模型中，它在CTB9数据集上使用了完整的子类别进行训练。
3. CTB9_CON_FULL_TAG_ERNIE_GRAM: 基于ERNIE-GRAM基础版预训练模型(:cite:xiao-etal-2021-ernie)的CRF句法分析器，在CTB9数据集上使用完整子类别进行训练。

## dep：中文依存关系分析
1. CTB5_BIAFFINE_DEP_ZH：基于BiAffine LSTM模型(:cite:dozat:17a)训练的中文依存关系分析器，训练数据集为中国现代汉语树库(CTB5)。
2. CTB7_BIAFFINE_DEP_ZH：基于BiAffine LSTM模型(:cite:dozat:17a)训练的中文依存关系分析器，但使用的数据集更新为CTB7。
3. CTB9_DEP_ELECTRA_SMALL：采用了Electra小型编码器(:cite:clark2020electra)与BiAffine解码器(:cite:dozat:17a)相结合的架构，训练数据集为CTB9的SD330子集。
4. PMT1_DEP_ELECTRA_SMALL：采用Electra小型编码器与BiAffine解码器结构，不过训练数据集改为了北京大学多视角汉语树库(PKU Multi-view Chinese Treebank, PMT) 1.0版本。
5. CTB9_UDC_ELECTRA_SMALL：Electra小型编码器与BiAffine解码器架构，但是训练数据集是基于CTB9转换后的UD420子集。
6. PTB_BIAFFINE_DEP_EN：英文依存句法分析任务的BiAffine LSTM模型(:cite:dozat:17a)，训练数据集为宾夕法尼亚树库(PTB, Penn Treebank)。
 
## eos：语句边界检测
1. UD_CTB_EOS_MUL ：基于EOS模型(:cite:Schweter:Ahmed:2019)的训练模型。

## sts: 语义相似度相关模型
1. STS_ELECTRA_BASE_ZH: 基于ELECTRA架构的预训练模型，专门针对中文句子相似度任务进行训练的模型。
