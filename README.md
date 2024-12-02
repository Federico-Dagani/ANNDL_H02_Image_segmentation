# ANNDL_H02

## Baseline (file baseline10, Kaggle version 10)
Preprocessing: Normalisation (/255 --> anche per TEST SET!!), NO augmentation, only alien removal, NO modifiche fede \
Model: (prof model) 32,64 + 128 \
Score: 0.46627 on Kaggle and 46.72 validation Mean Intersection Over Union

## Baseline + label adjustment (file marsadjusted)
Preprocessing: Normalisation (/255 --> anche per TEST SET!!), NO augmentation, only alien removal and label adjustment (removal of inconsistencies in the labels) \
Model: (prof model) 32,64 + 128 \
Score: 0.46983 on Kaggle and 45.81 validation Mean Intersection Over Union

## Unet with 32/64/128/256 bottleneck (file marsadjusted256)
Preprocessing: Normalisation (/255 --> anche per TEST SET!!), NO augmentation, only alien removal and label adjustment (removal of inconsistencies in the labels) \
Model: (prof model) 32,64,128 + 256 \
Score: 0.4808 on Kaggle and 48.24 validation Mean Intersection Over Union
