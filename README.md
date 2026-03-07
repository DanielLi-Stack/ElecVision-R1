# ElecVision-R1: A Multimodal LLM-Based Framework for Image Anomaly Detection and Quality Diagnosis in Power Systems
Abstract: Substations are crucial components in power transmission networks, playing a vital role in ensuring system stability and safety. In recent years, intelligent inspection technologies have achieved notable progress in image recognition, anomaly detection, and multimodal modeling. However, significant challenges remain in real-world industrial settings: the scarcity of domain-specific data limits robust adaptation, complex diagnostic tasks demand explicit multi-step reasoning, and effective decision-making requires integrating structured regulatory knowledge.
</p>

To address these issues, we introduce ElecInsp-QA, a large-scale multimodal dataset for power grid inspection that contains 126,401 annotated images, paired question–answer knowledge bases, and official regulatory documents. Building on this foundation, we propose ElecVision-R1, a multimodal framework that integrates both Group Relative Policy Optimization (GRPO) and Graph-based RAG retrieval and reasoning. GRPO equips the system with structured diagnostic reasoning processes, while Graph-based RAG enables contextualized knowledge retrieval and question answering in addition to visual anomaly detection.
</p>

Validated through  benchmark experiments, ElecVision-R1 demonstrates superior performance over existing baselines, delivering interpretable diagnostics and actionable decision support. The system has been stably deployed in a provincial state-owned enterprise in China, where its effectiveness and practical value have been formally recognized by the hosting organization. Taken together, these results suggest that reinforcement-learning–assisted, knowledge-grounded multimodal systems can improve the reliability and automation of industrial inspection.
</p>



[**Paper**]() | [**Project Page**]() | [**Model Weights**]() | [**Huggingface Demo**]() |


*Figure 1) Comparative overview and the proposed system. (a) Conventional data-driven pipeline. (b) Instruction-tuned VLM pipeline. (c) ElecVision-R1: a zero/few-shot agent integrating GRPO-based policy optimization and Graph-based RAG retrieval-and-reasoning, enabling step-by-step diagnosis for power-equipment inspection and reliability assessment.*
![img](assets/img (2).png)

*Figure 2) Schematic diagram of the reference segmentation dataset.*
![img](assets/img(6).png)

*Figure 3) The pipeline of SAAF. Given the input image and text query, the multimodal LLM (e.g, LLaVA ) generates text output. The last-layer embedding for the <SEG> token is then decoded into the segmentation mask via the decoder..*
![img](assets/img(7).png)

*Figure 4) Segmentation results of SAAF on different datasets.*
![img](assets/img(8).png)

*Figure 5) SAAF performs wall and window segmentation based on semantic guidance.*
![img](assets/img(1).png)

*Figure 6) SAAF performs wall and window segmentation based on semantic guidance.*
![img](assets/img(9).png)

*Figure 7) The pipeline of SAAF. Given the input image and text query, the multimodal LLM (e.g, LLaVA ) generates text output. The last-layer embedding for the <SEG> token is then decoded into the segmentation mask via the decoder..*
![img](assets/img(3).png)

*Figure 8) Segmentation results of SAAF on different datasets.*
![img](assets/img(4).png)

*Figure 9) SAAF performs wall and window segmentation based on semantic guidance.*
![img](assets/img(5).png)


## Dataset

*Realistic Image_completed.*
![img](sample/001.jpg)

*Realistic Image_partial.*
![img](sample/002.jpg)

*Perspective Image.*
![img](sample/003.jpg)

*Render Image.*
![img](sample/004.jpg)

*CAD Image.*
![img](sample/005.jpg)

*Pen drawing Image.*
![img](sample/006.jpg)

*Illustration Image.*
![img](sample/007.jpg)

*Watercolor Image.*
![img](sample/008.jpg)

*Book Image.*
![img](sample/009.jpg)

*Digital Model Image.*
![img](sample/010.jpg)

*Historical Document Image.*
![img](sample/011.jpg)

## TODO List

- [x] Release part of Segment-Any-Architecture-Facade dataset. 
- [ ] Release Segment-Any-Architecture-Facade inference code and pretrain weights.
- [ ] Upload Segment-Any-Architecture-Facade training dataset.
- [ ] Release Segment-Any-Architecture-Facade code.



## Inference

```
python Segment_Any_Architecture_Facade_Sample.py --dataset ArchiMetricsNet --batch_size 32  --color_configuration 0 --model_path ckpts/exp/model10000.pt --num_samples 64
```
## Train

```
python Segment_Any_Architecture_Facade_Train.py --dataset ArchiMetricsNet --batch_size 32  --color_configuration 0 
