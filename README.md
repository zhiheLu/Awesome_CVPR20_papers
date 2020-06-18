# Awsome_CVPR20_papers

# Contents

- [Contents](#contents)
  -[Knowledge Distillation](#knowledge-distillation)
  -[Network Compression](#network-compression)

## Knowledge Distillation

- Revisiting Knowledge Distillation via Label Smoothing Regularization. [[Paper Link]](http://openaccess.thecvf.com/content_CVPR_2020/papers/Yuan_Revisiting_Knowledge_Distillation_via_Label_Smoothing_Regularization_CVPR_2020_paper.pdf) 
  - Main idea: Breaking the original Knowledge Distillation (KD) principle using a strong teacher to teach a student, they instead conduct experiments in two new ways: deploying students to teach teachers and utilizing a poorly trained teacher to teach student. Surprislingly, two setting both gain some improvements. Based on this phenomenon, they rethink KD as a regularization. Through theoretically analysis, they also find that Label Smoothing Regularization (LSR). This is the motivation of this paper. Please find details in the original paper.

## Network Compression

- AdderNet: Do We Really Need Multiplications in Deep Learning? [[Paper Link]](http://openaccess.thecvf.com/content_CVPR_2020/papers/Chen_AdderNet_Do_We_Really_Need_Multiplications_in_Deep_Learning_CVPR_2020_paper.pdf) [[Pytorch]](https://github.com/huawei-noah/AdderNet)
  - Main idea: From the title, we can know that this work is to replace multiplication operations in network with addition operations. How do they do this and how about the performance? Please read the original paper and code.

- Multi-Dimensional Pruning: A Unified Framework for Model Compression. [[Paper Link]](http://openaccess.thecvf.com/content_CVPR_2020/papers/Guo_Multi-Dimensional_Pruning_A_Unified_Framework_for_Model_Compression_CVPR_2020_paper.pdf)
  - Main idea: They first build an over-parameterized network with average-pooling operations and gates. When using it, the gates can select some branches via their importances. Please read paper for details.