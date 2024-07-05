# Models
## Unconditional Models
- DALL-E

- IMAGEN

- Stable Diffusion

- 
## Conditional Models
- ControlNet

- GLIGEN

### Story Board
- **VisorGPT: Learning Visual Prior via Generative Pre-Training** [link](https://arxiv.org/pdf/2305.13777) _axiv last updated_ May 2023, _Accepted by_ NeurIPS 2023.
  - VisorGPT stands for "**Vis**ual pri**or** via **G**enerative **P**re-**T**raining".
  - It proposes a method to “explicitly learn the _visual prior_ and enable the customization of sampling.” In other words, it intends to _model the visual prior_.
  - Background: _Vision Prior_ (object location, shape and relation, etc) is necessary to follow so that we can generate images or videos concording with our reality world.
  - It discretizes the visual prior (in this paper they are _bounding boxes_, _human poses_, and _instance masks_) into sequence of tokens. This tokenizing process is tuned via _likelihood maximization_.
  - Problem Formulation:
    Supposing a specific visual prior sampel $x$ follows certain probabilistic distibution $p_x$, which is cannot be explicitly given its expression. Utilizing a neural network $f_\theta$ to mimic $p_x$, where $\theta$ is the parameters and can be optimized via likelihood maximizing. Finally, we can sample from $f_\theta$ to obtain new vision prior instances.
  - It confirms customizing spatial conditions from many aspects, e.g., data type, object size, number of instances, and classes, which gears the image synthesis models (say, ControlNet) to generate endless visual-prior-aware images. 
  ![image](https://github.com/qiaosun22/AwesomeText2Video/assets/136222260/c65f9b9a-7dc6-458b-b9f1-e3cd68135bae)

### Motion Guidance
- **Video Diffusion Models are Training-free Motion Interpreter and Controller** [link](https://arxiv.org/pdf/2405.14864v1) _axiv last updated_ May 2023
  - Propose one neglected question: _How do video diffusion models encode cross-frame motion information within their features?_ This is crucial for two reasons: a) it offers architectureagnostic insights, meaning that such knowledge can be applied across different models and their checkpoints, an important consideration given the rapid evolution of video diffusion models; and b) it supports various downstream applications.

# Datasets
- https://www.sciencedirect.com/science/article/pii/S2352340924004839


# Metrics
- Quality
  
- Diversity
