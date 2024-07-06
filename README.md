![image](https://github.com/qiaosun22/AwesomeText2Video/assets/136222260/21cc67ac-29d1-4f30-8159-5aa04c708faf)# Models
## Unconditional Models
### Previous Foundation Works on Image Generation
- DALL-E

- IMAGEN

- Stable Diffusion


## Conditional Models
### Paradigm 1: cross-attention based conditioning
#### Semantic Layouts to Images
- **GraphDreamer: Compositional 3D Scene Synthesis from Scene Graphs**[link](https://openaccess.thecvf.com/content/CVPR2024/papers/Gao_GraphDreamer_Compositional_3D_Scene_Synthesis_from_Scene_Graphs_CVPR_2024_paper.pdf)  _Accepted by_ CVPR_2024
  ![image](https://github.com/qiaosun22/AwesomeText2Video/assets/136222260/0f94bc24-a1bf-4c02-b693-22a450d15c08)
  ![image](https://github.com/qiaosun22/AwesomeText2Video/assets/136222260/86b8bca0-640c-4993-a3e1-49488e9b6a12)

- **SceneGenie: Scene Graph Guided Diffusion Models for Image Synthesis** [link](https://openaccess.thecvf.com/content/ICCV2023W/SG2RL/papers/Farshad_SceneGenie_Scene_Graph_Guided_Diffusion_Models_for_Image_Synthesis_ICCVW_2023_paper.pdf) _Accepted by_ CVPR_2023
  ![image](https://github.com/qiaosun22/AwesomeText2Video/assets/136222260/33126716-a316-4023-99cf-d573a1439491)

- **High-Resolution Image Synthesis with Latent Diffusion Models** [link](https://arxiv.org/pdf/2112.10752)  _arxiv last updated_ Apr 2022
  - By introducing cross-attention based conditioning into LDMs, it opens them up for various conditioning modalities previously unexplored for diffusion models.
  ![image](https://github.com/qiaosun22/AwesomeText2Video/assets/136222260/7a9124fa-2041-4416-9afe-5ec64552d04a)

- **Semantic Image Manipulation Using Scene Graphs** [link](https://openaccess.thecvf.com/content_CVPR_2020/papers/Dhamo_Semantic_Image_Manipulation_Using_Scene_Graphs_CVPR_2020_paper.pdf) _Accepted by_ CVPR_2020
  ![image](https://github.com/qiaosun22/AwesomeText2Video/assets/136222260/ca4015ee-c397-4927-8fd8-4a7b823450bb)
  ![image](https://github.com/qiaosun22/AwesomeText2Video/assets/136222260/39688953-1de2-46df-a9c9-34d11a2b73f8)


- **Semantic image manipulation using scene graphs** [link](https://openaccess.thecvf.com/content_cvpr_2018/papers/Johnson_Image_Generation_From_CVPR_2018_paper.pdf) _Accepted by_ CVPR_2018
  ![image](https://github.com/qiaosun22/AwesomeText2Video/assets/136222260/530c3192-f8e3-4a5e-98e6-6c2124f19286)
  ![image](https://github.com/qiaosun22/AwesomeText2Video/assets/136222260/406be6cf-8e75-43fa-9a5b-f45f648a4a3b)
  ![image](https://github.com/qiaosun22/AwesomeText2Video/assets/136222260/4d0c0ea3-2806-43b5-834a-7714aba2db36)





  
- ControlNet

- GLIGEN
### Tuning-free
- **AnimateDiff: Animate Your Personalized Text-to-Image Diffusion Models without Specific Tuning** [link](https://arxiv.org/abs/2307.04725) _arxiv last updated_ Jul 2023, _Accepted by_ ICLR 2024 (spotlight)
  - Module Innovations:
    1. Domain Adpater: enhance the visual quality of AnimateDiff by alleviating the motion module from learning the visual distribution gap.
    2. Motion Module: learns transferable motion priors from real-world videos
    3. Motion LoRA (optional): enables a pre-trained motion module to adapt to new motion patterns, such as different shot types, at a low training and data collection cost.
  ![image](https://github.com/qiaosun22/AwesomeText2Video/assets/136222260/3fcb43e1-c30b-4152-bb90-c1b403c63faf)


### Story Board
- **VisorGPT: Learning Visual Prior via Generative Pre-Training** [link](https://arxiv.org/pdf/2305.13777) _arxiv last updated_ May 2023, _Accepted by_ NeurIPS 2023
  - VisorGPT stands for "**Vis**ual pri**or** via **G**enerative **P**re-**T**raining".
  - It proposes a method to “explicitly learn the _visual prior_ and enable the customization of sampling.” In other words, it intends to _model the visual prior_.
  - Background: _Vision Prior_ (object location, shape and relation, etc) is necessary to follow so that we can generate images or videos concording with our reality world.
  - It discretizes the visual prior (in this paper they are _bounding boxes_, _human poses_, and _instance masks_) into sequence of tokens. This tokenizing process is tuned via _likelihood maximization_.
  - Problem Formulation:
    Supposing a specific visual prior sampel $x$ follows certain probabilistic distibution $p_x$, which is cannot be explicitly given its expression. Utilizing a neural network $f_\theta$ to mimic $p_x$, where $\theta$ is the parameters and can be optimized via likelihood maximizing. Finally, we can sample from $f_\theta$ to obtain new vision prior instances.
  - It confirms customizing spatial conditions from many aspects, e.g., data type, object size, number of instances, and classes, which gears the image synthesis models (say, ControlNet) to generate endless visual-prior-aware images. 
  ![image](https://github.com/qiaosun22/AwesomeText2Video/assets/136222260/c65f9b9a-7dc6-458b-b9f1-e3cd68135bae)

### Motion Guidance
- **Video Diffusion Models are Training-free Motion Interpreter and Controller** [link](https://arxiv.org/pdf/2405.14864v1) _arxiv last updated_ May 2023
  - **Insight**: Through analysis using Principal Component Analysis (PCA), our work discloses that robust motion-aware feature _already exists in_ video diffusion models.
    - Propose one neglected question: _How do video diffusion models encode cross-frame motion information within their features?_ This is crucial for two reasons:
      - a) it offers architectureagnostic insights, meaning that such knowledge can be applied across different models and their checkpoints, an important consideration given the rapid evolution of video diffusion models; and
      - b) it supports various downstream applications. 
  - It presents _MOtion FeaTure_ (MOFT) that _effectively captures motion information_.
  - **Methodology**: By 1) _eliminating content correlation information_ and 2) _filtering motion channels_.
  - MOFT has several **advantages**:
    - a) it encodes rich motion information with high interpretability;
    - b) it can be extracted in a training-free way; and
    - c) it is generalizable to various architectures.
![image](https://github.com/qiaosun22/AwesomeText2Video/assets/136222260/99d488ee-4b82-4d66-a412-571fe7ac9418)
![image](https://github.com/qiaosun22/AwesomeText2Video/assets/136222260/146a0d82-8b21-4a29-bae7-0c3cd65a3586)

### 3D-Aware
- **3D-Aware Video Generation** [link](https://arxiv.org/pdf/2206.14797) _Accepted by_ Transactions on Machine Learning Research (06/2023)
  ![image](https://github.com/qiaosun22/AwesomeText2Video/assets/136222260/c3cbdbac-2ce9-424a-8eb1-570445e0880b)
  the spatio-temporal renderings of two scenes sampled from our 4D GAN.

### Motion-Aware
- **MotionBooth: Motion-Aware Customized Text-to-Video Generation** [link](https://arxiv.org/pdf/2406.17758#page=12.85) _arxiv last updated_ Jun 2024
  
### Physics-Aware
Recent work has been based on 3D Gausian:
- **Physics3D: Learning Physical Properties of 3D Gaussians via Video Diffusion** [link](https://arxiv.org/pdf/2406.04338) _arxiv last updated_ Jun 2024
  ![image](https://github.com/qiaosun22/AwesomeText2Video/assets/136222260/72341d45-9bd7-418c-bd41-d579682d1405)
  
- **PhysDreamer: Physics-Based Interaction with 3D Objects via Video Generation** [link](https://arxiv.org/pdf/2206.14797) _arxiv last updated_ Apr 2024
  ![image](https://github.com/qiaosun22/AwesomeText2Video/assets/136222260/50f58bac-9c35-477f-8940-1306000391a2)
  Its literature review is insightful:
  ![image](https://github.com/qiaosun22/AwesomeText2Video/assets/136222260/f844a9b9-03b4-4934-909b-f4c85f5b5ef3)
  ![image](https://github.com/qiaosun22/AwesomeText2Video/assets/136222260/05d62e93-6bf7-4288-8944-294fe068d9cb)
  ![image](https://github.com/qiaosun22/AwesomeText2Video/assets/136222260/67fea98a-9d9f-475b-9341-b5a17b844cf8)




- **Physics-as-inverse-graphics: Unsupervised physical parameter estimation from video** [link](https://arxiv.org/pdf/1905.11169) _arxiv last updated_ Apr 2020, _Accepted by_ ICLR 2020
  - This is an early work before the emergence of various DDPMs.
  - It serves as an insight to treat the inverse graphics problem (motion parameters prediction) using a network from a video input. Though the "video generation" is trivial. 
  - It significantly outperforms related unsupervised methods in long-term future frame prediction of systems with interacting objects (such as ball-spring or 3-body gravitational systems), due to its ability to build dynamics into the model as an inductive bias. 
  ![image](https://github.com/qiaosun22/AwesomeText2Video/assets/136222260/a5c60148-1a36-4aa6-b07c-a0f22918a3fc)
  ![image](https://github.com/qiaosun22/AwesomeText2Video/assets/136222260/8063d4d3-7ba7-464a-96fa-ec6715559cd7)


# Other Relevant Methods
## Inverse Problem: PSG Generation
- **TextPSG: Panoptic Scene Graph Generation from Textual Descriptions** [link](https://arxiv.org/pdf/2310.07056#page=3.84)
  ![image](https://github.com/qiaosun22/AwesomeText2Video/assets/136222260/29405b3a-f8b2-4d83-a99a-f7693c6171c1)


# Datasets
- OpenImages [link](https://arxiv.org/pdf/1811.00982)
  ![image](https://github.com/qiaosun22/AwesomeText2Video/assets/136222260/19d711b8-9a22-4cce-b13e-2a2a9cb31340)

- https://www.sciencedirect.com/science/article/pii/S2352340924004839


# Metrics
- Quality
  
- Diversity

# Literature Reviews or Investigations
- 

# Lectures & Tutorials & Blogs
- **Physics-inspired diffusion model** [link](https://collab.dvb.bayern/display/TUMdlma/Physics-inspired+diffusion+model)
