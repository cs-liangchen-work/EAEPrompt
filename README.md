# EAEPrompt

## code for paper "Event Argument Extraction with Enriched Prompts"


### 1.运行代码
（同RAMS原始数据集建议评估方式）：
```
nohup python3 -u code_1.py --gold_file dev.jsonlines --pred_file 1.json --ontology_file event_role_multiplicities.txt  --do_all --reuse_gold_format > r_1.txt 2>&1 &
```

### 2.代码说明

- role-prompt:
