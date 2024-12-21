# EAEPrompt

## code for paper "Event Argument Extraction with Enriched Prompts"


### 1.运行代码
（同RAMS原始数据集建议评估方式）：
```
nohup python3 -u code_1.py --gold_file dev.jsonlines --pred_file 1.json --ontology_file event_role_multiplicities.txt  --do_all --reuse_gold_format > r_1.txt 2>&1 &
```

### 2.代码说明

- role-prompt:


### 3. 损失增强

```
def dice_loss(target, predictive, ep=1e-8):
    t = 0.0
    for i in range(len(target)):
        intersection = 2 * torch.sum(predictive[i] * target[i]) + ep
        union = torch.sum(predictive[i]) + torch.sum(target[i]) + ep
        t += 1 - intersection / union
    loss = t/len(target)
    return loss

loss = weight1 * (loss_func(out_1.cuda(), label_begin.cuda()) + loss_func(out_2.cuda(), label_end.cuda())) + weight2 * dice_loss(target=label.cuda(), predictive=(out_1.softmax(dim=-1).cuda()+out_2.softmax(dim=-1).cuda())/2)
```
