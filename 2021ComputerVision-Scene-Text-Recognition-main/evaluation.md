## 평가지표

*   STR task에서 흔히 사용하는 평가지표인 accuracy를 사용했습니다. 여기에서의 accuracy는 단어 level의 accuracy로 이미지내의 단어를 정확하게 맞춘 비률을 의미합니다.

![](https://raw.githubusercontent.com/Denny-Warhol/cv_course/leader-board-img/acc_fromula.PNG)

*   예를 들어 아래와 같이 5개의 text image에서 3개를 정확하게 예측하였다면 정확도는 60%입니다.

![](https://raw.githubusercontent.com/Denny-Warhol/cv_course/leader-board-img/perf_measure.PNG)

## 제출 방법

*   Submition 파일의 형식은 CSV format의 파일이여야 합니다.
*   파일 형식은 아래 그림과 같이 `id`와 `predict`을 header로 설정해야 합니다.
*   `id` column의 값은 데이터셋의 이름 @ LMDA format으로 저장된 테스트 파일의 label_key로 설정해야 합니다.
*   `predict` column의 값은 모델이 예측한 값입니다.

![](https://raw.githubusercontent.com/Denny-Warhol/cv_course/leader-board-img/submit_format.PNG)