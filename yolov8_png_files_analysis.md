# 📊 YOLOv8 학습 결과 시각화 파일 설명 및 발표 활용 정리

본 문서는 YOLOv8 학습 완료 후 생성된 시각화 결과 이미지 5개에 대한 의미와 발표에서의 활용 방법을 정리한 자료입니다.

---

## ✅ 1. results.png (또는 results (2).png)

- **내용**: 학습 및 검증 손실, mAP, Precision, Recall 등 전반적인 학습 과정을 한 장의 이미지로 시각화
- **포함 지표**:
  - train/box_loss, cls_loss, dfl_loss
  - val/box_loss, cls_loss, dfl_loss
  - metrics/precision(B), recall(B)
  - metrics/mAP50(B), mAP50-95(B)
- **활용 포인트**:
  - 모델이 안정적으로 학습되었는지 설명 가능
  - 과적합 여부 판단 가능
  - mAP, precision/recall 수치로 성능을 종합 평가 가능

---

## ✅ 2. F1_curve.png

- **내용**: 다양한 confidence threshold에 대한 F1-score 변화 시각화
- **의미**: Precision과 Recall의 조화 평균이 가장 높은 지점을 시각적으로 확인 가능
- **활용 포인트**:
  - 모델이 전체적으로 균형 잡힌 탐지 성능을 갖췄는지 설명 가능
  - 최적의 confidence 임계값 설정에 참고

---

## ✅ 3. P_curve.png (Precision Curve)

- **내용**: confidence 값에 따라 Precision이 어떻게 변화하는지 보여줌
- **의미**: 높은 confidence에서 오탐(False Positive)을 얼마나 줄였는지 확인 가능
- **활용 포인트**:
  - "모델이 확신이 높을수록 정확하게 탐지함"을 강조할 때 사용
  - 검출 신뢰도 기반 후처리 설명 시 유용

---

## ✅ 4. R_curve.png (Recall Curve)

- **내용**: confidence 값에 따라 Recall이 어떻게 변하는지 보여줌
- **의미**: 얼마나 놓치지 않고 객체를 탐지했는지를 확인 가능
- **활용 포인트**:
  - "낮은 confidence에서도 객체를 잘 놓치지 않음"을 설명할 때 사용
  - 모델이 검출률 위주의 환경에서 얼마나 유리한지 강조

---

## ✅ 5. PR_curve.png (Precision-Recall Curve)

- **내용**: Precision과 Recall의 관계를 곡선으로 시각화
- **의미**: 우상단에 가까울수록 모델의 탐지 성능이 우수함
- **활용 포인트**:
  - 모델의 전반적인 성능 수준을 한눈에 보여줌
  - 다른 모델과 비교 시 시각적 근거로 사용

---

## 📌 발표 활용 요약표

| 파일명 | 주요 지표 | 발표 활용 키워드 |
|--------|-----------|------------------|
| results.png | loss, mAP, precision, recall | "학습 경향, 성능 종합" |
| F1_curve.png | F1-score | "탐지 성능의 균형" |
| P_curve.png | Precision | "오탐 없이 탐지함" |
| R_curve.png | Recall | "객체를 놓치지 않음" |
| PR_curve.png | P-R 곡선 | "전반적인 탐지 성능 우수" |

---

## ✅ 발표 멘트 예시

> "저희 모델은 훈련 및 검증 손실이 모두 안정적으로 감소하며, mAP@0.5는 약 0.99, mAP@0.5:0.95는 약 0.78을 기록했습니다. Precision과 Recall 모두 0.98 이상으로 우수한 탐지 성능을 보였고, PR 곡선과 F1-score 곡선에서도 높은 균형 성능을 확인할 수 있었습니다."
