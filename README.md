# Awsome_CVPR20_papers

# Contents

- [Contents](#contents)
  - [Knowledge Distillation](#knowledge-distillation)
  - [Network Compression](#network-compression)
  - [Detection](#detection)
  - [Person ReID](#person_reid)
  - [Recognition](#recognition)
  - [Normalization](#normalization)
  - [Multi-task](#multi-task)
  - [Domain Adaptation](#domain-adaptation)
  - [Attention](#attention)
  - [Representation Learning](representation-learning)
  - [Dataset](#dataset)

## Knowledge Distillation

- Revisiting Knowledge Distillation via Label Smoothing Regularization. [[Paper Link]](http://openaccess.thecvf.com/content_CVPR_2020/papers/Yuan_Revisiting_Knowledge_Distillation_via_Label_Smoothing_Regularization_CVPR_2020_paper.pdf)
  - Main idea: Breaking the original Knowledge Distillation (KD) principle using a strong teacher to teach a student, they instead conduct experiments in two new ways: **deploying students to teach teachers and utilizing a poorly trained teacher to teach a student**. Surprisingly, two settings both gain some improvements. Based on this phenomenon, they rethink KD as a regularization. Through theoretically analysis, they also find that Label Smoothing Regularization (LSR) is similar as KD. This is the motivation of this paper. Please find details in the original paper.

- Distilling Cross-Task Knowledge via Relationship Matching. [[Paper Link]](http://openaccess.thecvf.com/content_CVPR_2020/papers/Ye_Distilling_Cross-Task_Knowledge_via_Relationship_Matching_CVPR_2020_paper.pdf) [[Pytorch]](https://github.com/njulus/ReFilled)
  - Main idea: Previous KD methods usually use a teacher to teach a student under the same task. This paper arises the question that if cross-task knowledge can be utilized and proposes a proper solution. See details in the paper and code.

- Search to Distill: Pearls are Everywhere but not the Eyes. [[Paper Link]](http://openaccess.thecvf.com/content_CVPR_2020/papers/Liu_Search_to_Distill_Pearls_Are_Everywhere_but_Not_the_Eyes_CVPR_2020_paper.pdf) 
  - Main idea: From the experimental results, they found that the teacher models prefer paticular students, i.e., one unique student can learn better than others from the same teacher. Based on this, they rethink KD.	

## Network Compression

- AdderNet: Do We Really Need Multiplications in Deep Learning? [[Paper Link]](http://openaccess.thecvf.com/content_CVPR_2020/papers/Chen_AdderNet_Do_We_Really_Need_Multiplications_in_Deep_Learning_CVPR_2020_paper.pdf) [[Pytorch]](https://github.com/huawei-noah/AdderNet)
  - Main idea: From the title, we can know that this work is to replace multiplication operations in network with addition operations. How do they do this and how about the performance? Please read the original paper and code.

- Multi-Dimensional Pruning: A Unified Framework for Model Compression. [[Paper Link]](http://openaccess.thecvf.com/content_CVPR_2020/papers/Guo_Multi-Dimensional_Pruning_A_Unified_Framework_for_Model_Compression_CVPR_2020_paper.pdf)
  - Main idea: They first build an over-parameterized network with average-pooling operations and gates. When using it, the gates can select some branches via their importances. This pipeline is in line with NAS. Please read the paper for details.

## Detection

- Bridging the Gap Between Anchor-Based and Anchor-Free Detection via Adaptive Training Sample Selection. [[Paper Link]](http://openaccess.thecvf.com/content_CVPR_2020/papers/Zhang_Bridging_the_Gap_Between_Anchor-Based_and_Anchor-Free_Detection_via_Adaptive_CVPR_2020_paper.pdf) [[Pytorch]](https://github.com/sfzhang15/ATSS)
  - Main idea: They first point out that the essential difference between anchor-based and anchor-free detection is actually **how to define positive and negative training samples**, which leads to the performance gap between them. Then, an Adaptive Training Sample Selection (ATSS) is proposed to automatically select positive and negative samples according to **statistical characteristics of object**. Is sample selection also important for other tasks and how to do that? Need to think and try.

- Learning to Detect Important People in Unlabelled Images for
Semi-supervised Important People Detection. [[Paper Link]](http://openaccess.thecvf.com/content_CVPR_2020/papers/Hong_Learning_to_Detect_Important_People_in_Unlabelled_Images_for_Semi-Supervised_CVPR_2020_paper.pdf) 
  - Main idea: This is the first work to detect important people in a semi-supervised way. Two large benchmarks are introduced serving for it. Can think if it is worth following.

## Person ReID

- Unsupervised Person Re-identification via Multi-label Classification. [[Paper Link]](http://openaccess.thecvf.com/content_CVPR_2020/papers/Wang_Unsupervised_Person_Re-Identification_via_Multi-Label_Classification_CVPR_2020_paper.pdf)
  - Main idea: This paper formulates unsupervised person ReID as a multi-label classification task to progressively seek true labels. The label prediction comprises **similarity computation and cycle consistency** to ensure the quality of predicted labels. Further, a memory-based multi-label classification loss (MMCL) is introduced. Maybe we can gain some insights for general UDA.

## Recognition

- Don’t Judge an Object by Its Context: Learning to Overcome Contextual Bias. [[Paper Link]](http://openaccess.thecvf.com/content_CVPR_2020/papers/Singh_Dont_Judge_an_Object_by_Its_Context_Learning_to_Overcome_CVPR_2020_paper.pdf) [[Project Page]](http://krsingh.cs.ucdavis.edu/krishna_files/papers/contextbias/index.html)
  - Main idea: Existing models often leverage **co-occurrences** between objects and their context to improve recognition accuracy. However, strongly relying on context risks a model’s generalizability, especially when typical co-occurrence patterns are absent. This work focuses on addressing such contextual biases to improve the robustness of the learnt feature representations. 


## Normalization

- Local Context Normalization: Revisiting Local Normalization. [[Paper Link]](http://openaccess.thecvf.com/content_CVPR_2020/papers/Ortiz_Local_Context_Normalization_Revisiting_Local_Normalization_CVPR_2020_paper.pdf)
  - Main idea: This paper proposed Local Context Normalization (LCN) that outperfroms previous normalization ways, e.g., Batch Normalization (BN), Group Normalization (GN), Instance Normalization (IN), and Layer Normalization (LN), in several tasks.

- Filter Response Normalization Layer: Eliminating Batch Dependence in the
Training of Deep Neural Networks. [[Paper Link]](http://openaccess.thecvf.com/content_CVPR_2020/papers/Singh_Filter_Response_Normalization_Layer_Eliminating_Batch_Dependence_in_the_Training_CVPR_2020_paper.pdf)
  - Main idea: Batch Normalization (BN) uses mini-batch statistics to normalize the activations during training, introducing dependence between mini-batch elements. This dependency can hurt the performance if the mini-batch size is too small, or if the elements are correlated. Several alternatives, such as Batch Renormalization and Group Normalization (GN), have been proposed to address this issue. However, they either do not match the performance of BN for large batches, or still exhibit degradation in performance for smaller batches, or introduce artificial constraints on the model architecture. In this paper **the Filter Response Normalization (FRN) layer** is proposed, a novel combination of a normalization and an activation function, that can be used as a replacement for other normalizations and activations. Experimental results show its superiority.

- An Investigation into the Stochasticity of Batch Whitening. [[Paper Link]](http://openaccess.thecvf.com/content_CVPR_2020/papers/Huang_An_Investigation_Into_the_Stochasticity_of_Batch_Whitening_CVPR_2020_paper.pdf) [[Code]](https://github.com/huangleiBuaa/StochasticityBW)
  - Main idea: In this paper, general batch whitening methods are introduced to replace BN. In addition, the results show the stochasticity of batch whitening operations can benefit the performance. In my opinion, this can be regarded as a way doing augmentation after activation. Please read the paper and code for more.

## Multi-task

- Robust Learning Through Cross-Task Consistency. [[Paper Link]](http://openaccess.thecvf.com/content_CVPR_2020/papers/Zamir_Robust_Learning_Through_Cross-Task_Consistency_CVPR_2020_paper.pdf) [[Project Pape]](https://consistency.epfl.ch/)
  - Main idea: The Cross-Task Consistency is proposed in this work. Please read the paper for more details.

## Domain Adaptation

- Open Compound Domain Adaptation. [[Paper Link]](http://openaccess.thecvf.com/content_CVPR_2020/papers/Liu_Open_Compound_Domain_Adaptation_CVPR_2020_paper.pdf) [[Project Page]](https://liuziwei7.github.io/projects/CompoundDomain.html)
  - Main idea: A new task is introduced in this work. Different from single-source UDA and multi-target UDA, a compound target domain and an unseen target domain are introduced. For this task, several benchmarks are also carefully designed. Please read the paper and code for details.

- Gradually Vanishing Bridge for Adversarial Domain Adaptation. [[Paper Link]](http://openaccess.thecvf.com/content_CVPR_2020/papers/Cui_Gradually_Vanishing_Bridge_for_Adversarial_Domain_Adaptation_CVPR_2020_paper.pdf) [[Pytorch]](https://github.com/cuishuhao/GVB)
  - Main idea: An intermediate domain is introduced between source and target domains to bridge the domain gap. Please read the paper and code for more information.

- Learning to Learn Single Domain Generalization. [[Paper Link]](http://openaccess.thecvf.com/content_CVPR_2020/papers/Qiao_Learning_to_Learn_Single_Domain_Generalization_CVPR_2020_paper.pdf) [[Pytorch]](https://github.com/joffery/M-ADA)
  - Main idea: Instead of using multi-source domains and one target domain, they introduce a new setting, i.e., single-source domain and multi-target domains, to do domain generalization. 

## Attention

- Exploring Self-attention for Image Recognition. [[Paper Link]](http://openaccess.thecvf.com/content_CVPR_2020/papers/Zhao_Exploring_Self-Attention_for_Image_Recognition_CVPR_2020_paper.pdf) [[Project Page]](https://mmcheng.net/scconv/)
  - Main idea: This work investigates the variations of self-attention and proposes two variants: pairwise self-attention and patchwise self-attention. Please read the paper for details.

## Representation Learning

- Towards Backward-Compatible Representation Learning. [[Paper Link]](http://openaccess.thecvf.com/content_CVPR_2020/papers/Shen_Towards_Backward-Compatible_Representation_Learning_CVPR_2020_paper.pdf)
  - Main idea: This work focuses on an industrial and practical problem. Assuming there are millions of gallery features extracted from a previous model but these features can be updated due to the computing cost, how to train a new model with new probe images that can gain a high performance in the image retrieval task. As authors said, this is a problem faced by many companies. For this, they first propose a method to solve it. Please read this paper for details.

- Steering Self-Supervised Feature Learning Beyond Local Pixel Statistics. [[Paper Link]](http://openaccess.thecvf.com/content_CVPR_2020/papers/Jenni_Steering_Self-Supervised_Feature_Learning_Beyond_Local_Pixel_Statistics_CVPR_2020_paper.pdf) [[Project Page]](https://sjenni.github.io/LCI/)
  - Main idea: Unlike previous methods focusing on global statistics, this paper emphsizes the local statistics for self-supervised learning. During training, both global and local transformations are assigned labels.

## Dataset

- FineGym: A Hierarchical Video Dataset for Fine-grained Action Understanding. [[Paper Link]](http://openaccess.thecvf.com/content_CVPR_2020/papers/Shao_FineGym_A_Hierarchical_Video_Dataset_for_Fine-Grained_Action_Understanding_CVPR_2020_paper.pdf) [[Project Page]](https://sdolivia.github.io/FineGym/)
  - Main idea: To take action recognition to a new level, they develop FineGym, a new dataset built on top of gymnastic videos. 