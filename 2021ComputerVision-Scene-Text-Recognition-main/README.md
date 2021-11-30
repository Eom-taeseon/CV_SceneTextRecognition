## 챌린지 개요

본 챌린지는 Optical Character Recognition(OCR) task 중 'Scene Text Recognition(STR)'을 수행하는 챌린지 입니다. STR는 컴퓨터가 물체의 레이블, 도로 표지판 등과 같은 natural scenes에 존재하는 텍스트를 읽을 수 있게 합니다. STR는 machine이 어떤 방향으로 가야 하는지, 어떤 행동을 취할지, 어떤 물체를 선택할 지와 같은 텍스트 정보에 기반한 결정을 내릴수 있도록 도와줍니다.

![](https://raw.githubusercontent.com/Denny-Warhol/cv_course/leader-board-img/str_process.PNG)

본 첼린지에서는 연구[1]에서 제안한 vision transformer(ViT)기반 ViTSTR 모델을 통해 얻은 성능을 베이스라인으로 설정하였습니다.

![](https://raw.githubusercontent.com/Denny-Warhol/cv_course/leader-board-img/detr_arch.PNG)

### 설명 영상

챌린지 설명, 베이스라인 논문 및 코드 사용법에 대한 설명은 아래 동영상을 참고할 수 있습니다.

*   [동영상](https://youtu.be/1CBn6AmTa2w)

## 데이터셋 구성

### 훈련 데이터셋

STR 모델을 훈련할 수 있는 labeling된 real data가 부족하기 때문에 STR 모델 훈련의 관행은 synthetic data를 사용하는 것입니다. 이번 첼린지의 베이스라인 성능은 MJSynth(MJ also known as Synth90k)과 SynthText(ST) 데이터셋을 각각 50% 사용해 훈련을 진행한 모델을 통해 얻은 결과입니다. 첼린지에 MJ와 ST 데이터셋을 100% 모두 사용하거나 기타 데이터셋도 사용 가능합니다. 다만 아래 테스트 데이터셋으로 명시한 데이터는 훈련 과정에서 사용할 수 없습니다.

![](https://raw.githubusercontent.com/Denny-Warhol/cv_course/leader-board-img/synth_dataset.PNG)

### 테스트 데이터셋

모델의 훈련에는 합성된 synthetic data를 사용하는 것과 달리 성능 테스트는 real data를 사용해야 합니다. 연구[2]에서는 STR 모델의 fair evaluation을 위해 통일된 performance evaluation framework을 제안했습니다. 이번 첼린지에서는 연구[2]에서 사용한 방법과 동일한 성능 측정 방법을 사용하였습니다. 모델 성능 테스트를 위해 실제 secene text iamge dataset인 IIIT5K, SVT, IC03, IC13, IC15, SVTP, CT 데이터셋의 테스트 셋 부분의 이미지를 취합하여 성능 테스트 데이터셋으로 사용하였습니다.

![](https://raw.githubusercontent.com/Denny-Warhol/cv_course/leader-board-img/real_dataset.PNG)

훈련 데이터셋과 테스트 데이터셋은 아래 링크를 통해 다운로드할 수 있습니다.

1.  [Google Drive](https://drive.google.com/drive/folders/192UfE9agQUMNq6AgU3_E05_FcPZK4hyt)
2.  [Dropbox](https://www.dropbox.com/sh/i39abvnefllx2si/AAAbAYRvxzRp3cIE5HzqUw3ra?dl=0)

## 베이스라인 코드

베이스라인 코드는 2021년 arVix에 공개된 ViT기반 signle stage model architecture를 가진 ViTSTR 모델을 제안한 논문[1]를 참고하였습니다.

ViTSTR의 코드 및 사용 방법은 논문의 저자가 공개한 GitHub repository[3]를 참고하였습니다.(*해당 GitHub repository에서 훈련된 가중치를 제공하고 있지만 자신만의 모델을 훈련해야 합니다. 제공한 가중치를 사용하면 저자의 모델과 똑같은 성능이 나오게 됩니다.)

*Windows 환경에서 Dataloader 관련애서 TypeError: can't pickle Environment objects와 같은 에러가 발생했다면 [issue1](/../../issues/1) 확인

#### 참고자료

*   [1] Vision Transformer for Fast and Efficient Scene Text Recognition[(Link)](https://arxiv.org/abs/2105.08582)
*   [2] What Is Wrong With Scene Text Recognition Model Comparisons? Dataset and Model Analysis[(Link)](https://arxiv.org/abs/1904.01906)
*   [3] ViTSTR GitHub Repository[(Link)](https://github.com/roatienza/deep-text-recognition-benchmark)

#### 추천하는 논문

*   [1] What is wrong with scene text recognition model comparisons? dataset and model analysis.[(Link)](https://arxiv.org/abs/1904.01906)
*   [2] Robust scene text recognition with automatic rectification.[(Link)](https://arxiv.org/abs/1603.03915)
*   [3] Principal warps: Thin-plate splines and the decomposition of deformations.[(Link)](https://user.engineering.uiowa.edu/~aip/papers/bookstein-89.pdf)
*   [4] STAR-Net: a spatial attention residue network for scene text recognition.[(Link)](http://www.bmva.org/bmvc/2016/papers/paper043/paper043.pdf)
*   [5] Swin Transformer: Hierarchical Vision Transformer using Shifted Windows.[(Link)](https://arxiv.org/abs/2103.14030)
*   [6] TrOCR: Transformer-based Optical Character Recognition with Pre-trained Models.[(Link)](https://arxiv.org/abs/2109.10282)
