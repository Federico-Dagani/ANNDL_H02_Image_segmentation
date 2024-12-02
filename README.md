# ANNDL_H02

## Baseline (file baseline10, Kaggle version 10)
Preprocessing: Normalisation (/255 --> anche per TEST SET!!), NO augmentation, only alien removal, NO modifiche fede \
Model: (prof model) 32,64 + 128 \
Score: 0.46627 on Kaggle and 46.72 validation Mean Intersection Over Union

## Baseline + label adjustment (file marsadjusted)
Preprocessing: Normalisation (/255 --> anche per TEST SET!!), NO augmentation, only alien removal and label adjustment (removal of inconsistencies in the labels) \
Model: (prof model) 32,64 + 128 \
Score: 0.46983 on Kaggle and 45.81 validation Mean Intersection Over Union \
/kaggle/working/submission_241201_214359.csv

## Unet with 32/64/128/256 bottleneck (file marsadjusted256)
Preprocessing: Normalisation (/255 --> anche per TEST SET!!), NO augmentation, only alien removal and label adjustment (removal of inconsistencies in the labels) \
Model: 32,64,128 + 256 \
Score: 0.48088 on Kaggle and 48.24 validation Mean Intersection Over Union \
/kaggle/working/submission_241202_093600.csv

## Unet with 32/64/128/256/512 bottleneck (file marsadjusted512)
Preprocessing: Normalisation (/255 --> anche per TEST SET!!), NO augmentation, only alien removal and label adjustment (removal of inconsistencies in the labels) \
Model: 32,64,128,256 + 512 \
Score: 0.48756 on Kaggle and 47.98 validation Mean Intersection Over Union \
/kaggle/working/submission_241202_100314.csv

## Unet with transpose convolution (file marsadjusted512conv)
Preprocessing: Normalisation (/255 --> anche per TEST SET!!), NO augmentation, only alien removal and label adjustment (removal of inconsistencies in the labels) \
Model: 32,64,128,256 + 512 using transpose convolution instead of upsampling\
Score: 0.47759 on Kaggle and 47.35 validation Mean Intersection Over Union \
/kaggle/working/submission_241202_103806.csv
