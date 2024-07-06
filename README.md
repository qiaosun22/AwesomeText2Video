# Models
## Unconditional Models
### Previous Foundation Works on Image Generation
- DALL-E

- IMAGEN

- Stable Diffusion


## Conditional Models
### Paradigm 1: cross-attention based conditioning
#### Semantic Layouts to Images

- **High-Resolution Image Synthesis with Latent Diffusion Models** [link](https://arxiv.org/pdf/2112.10752)  _arxiv last updated_ Apr 2022
  - By introducing cross-attention based conditioning into LDMs, it opens them up for various conditioning modalities previously unexplored for diffusion models.
    ![image](https://github.com/qiaosun22/AwesomeText2Video/assets/136222260/7a9124fa-2041-4416-9afe-5ec64552d04a)


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


### Motion-Aware
- **MotionBooth: Motion-Aware Customized Text-to-Video Generation** [link](https://arxiv.org/pdf/2406.17758#page=12.85) _arxiv last updated_ Jun 2024
  
### Physics-Aware
- **PhysDreamer: Physics-Based Interaction with 3D Objects via Video Generation** [link](https://arxiv.org/pdf/2206.14797) _arxiv last updated_ Apr 2024
- **Physics-as-inverse-graphics: Unsupervised physical parameter estimation from video** [link](https://arxiv.org/pdf/1905.11169) _arxiv last updated_ Apr 2020, _Accepted by_ ICLR 2020
  - This is an early work before the emergence of various DDPMs.
  - It serves as an insight to use video generation for the physics-world interactions:
  ![image](https://github.com/qiaosun22/AwesomeText2Video/assets/136222260/a5c60148-1a36-4aa6-b07c-a0f22918a3fc)


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
