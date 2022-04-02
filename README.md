# Personalized-FedAvg

This repos is the implementation of [Improving Federated Learning Personalization via Model Agnostic Meta Learning](https://arxiv.org/abs/1909.12488). 

Thanks to the heavy dependency of [FedLab](https://github.com/SMILELab-FL/FedLab) and [FedLab-benchmarks](https://github.com/SMILELab-FL/FedLab-benchmarks), my code has already been pulled to https://github.com/SMILELab-FL/FedLab-benchmarks/tree/master/fedlab_benchmarks/perfedavg. this repo is only for displaying `README` and as the interface for the people who interested in this algorithm implementation 😄.



## Further reading

- Reptile: [On First-Order Meta-Learning Algorithms](https://arxiv.org/abs/1803.02999)
- MAML: [Model-Agnostic Meta-Learning for Fast Adaptation of Deep Networks](https://arxiv.org/abs/1703.03400)
- LEAF: [LEAF: A Benchmark for Federated Settings](https://arxiv.org/pdf/1812.01097.pdf)

## Requirements

- torch
- fedlab
- tqdm
- pickle
- pillow

## Performance

Evaluation result after fine-tuned is shown below. 

Communication round: `500`

Fine-tune: outer loop: `100`; inner loop: `10`

Personalization round: `5`

| FedAvg local training epochs (5 clients) | Initial loss | Initial Acc | Personalized loss | Personalized Acc |
| ---------------------------------------- | ------------ | ----------- | ----------------- | ---------------- |
| 20                                       | 2.3022       | 79.35%      | 1.5766            | 84.86%           |
| 10                                       | 1.8387       | 80.53%      | 1.1231            | 87.22%           |
| 5                                        | 1.4899       | **83.19%**  | 0.9809            | **88.97%**       |
| 2                                        | 1.4613       | 81.70%      | 0.9359            | 88.49%           |

| FedAvg local training epochs (20 clients) | Initial loss | Initial Acc | Personalized loss | Personalized Acc |
| ----------------------------------------- | ------------ | ----------- | ----------------- | ---------------- |
| 20                                        | 2.2398       | 82.40%      | 0.9756            | 90.29%           |
| 10                                        | 1.6560       | **83.23**%  | 0.8488            | 90.72%           |
| 5                                         | 1.5485       | 81.48%      | 0.7452            | **90.77**%       |
| 2                                         | 1.2707       | 82.48%      | 0.7139            | 90.48%           |

Experiment result from [paper](https://arxiv.org/abs/1909.12488) is shown below

![image-20220326202529457](paper_exp_res.png)



