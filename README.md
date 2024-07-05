# Models
- **VisorGPT: Learning Visual Prior via Generative Pre-Training** [link](https://arxiv.org/pdf/2305.13777) _axiv last updated_ May 2023, _Accepted by_ NeurIPS 2023.
  - Visor GPT stands for "**Vis**ual pri**or** via **G**enerative **P**re-**T**raining".
  - It proposes a method to “explicitly learn the _visual prior_ and enable the customization of sampling.” In other words, it intends to _model the visual prior_.
  - _Vision Prior_ (object location, shape and relation, etc) is necessary to follow so that we can generate images or videos concording with our reality world.
  - It discretizes the visual prior (in this paper they are _bounding boxes_, _human poses_, and _instance masks_) into sequence of tokens. This tokenizing process is tuned via _likelihood maximization_.
  ![image](https://github.com/qiaosun22/AwesomeText2Video/assets/136222260/c65f9b9a-7dc6-458b-b9f1-e3cd68135bae)


# Datasets
- https://www.sciencedirect.com/science/article/pii/S2352340924004839
