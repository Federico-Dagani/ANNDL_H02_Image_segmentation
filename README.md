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
Preprocessing: Normalisation (/255 --> anche per TEST SET!!), NO augmentation, only alien removal \
Model: 32,64,128,256 + 512 \
Score: 0.47244 on Kaggle and 47.~~ validation Mean Intersection Over Union \
/kaggle/working/submission_241202_213214.csv

## Unet with 32/64/128/256/512 bottleneck (file marsadjusted512)
Preprocessing: Normalisation (/255 --> anche per TEST SET!!), NO augmentation, only alien removal and label adjustment (removal of inconsistencies in the labels)  \
Model: 32,64,128,256 + 512 \
Score: 0.48756 on Kaggle and 47.98 validation Mean Intersection Over Union \
/kaggle/working/submission_241202_100314.csv

## Unet with transpose convolution (file marsadjusted512conv)
Preprocessing: Normalisation (/255 --> anche per TEST SET!!), NO augmentation only alien removal and label adjustment (removal of inconsistencies in the labels) \
Model: 32,64,128,256 + 512 using transpose convolution instead of upsampling\
Score: 0.47759 on Kaggle and 47.35 validation Mean Intersection Over Union \
/kaggle/working/submission_241202_103806.csv

## Unet with addition (file marsadjusted512add)
Preprocessing: Normalisation (/255 --> anche per TEST SET!!), NO augmentation, only alien removal only alien removal and label adjustment (removal of inconsistencies in the labels) \
Model: 32,64,128,256 + 512 using addition instead of concatenation\
Score: 0.47636 on Kaggle and 47.10 validation Mean Intersection Over Union \
/kaggle/working/submission_241202_110358.csv

## Unet with 32/64/128/256/512/1024 bottleneck (file marsadjusted1024)
Preprocessing: Normalisation (/255 --> anche per TEST SET!!), NO augmentation, only alien removal and label adjustment (removal of inconsistencies in the labels) \
Model: 32,64,128,256,512 + 1024 \
Score: 0.48448 on Kaggle and 47.85 validation Mean Intersection Over Union \
/kaggle/working/submission_241202_112820.csv

## Unet with 32/64/128/256/512 bottleneck + basic augm
Preprocessing: Normalisation (/255 --> anche per TEST SET!!), basic augmentation (flip, brightness(+/-0.15) and contrast (+/-0.5)), only alien removal and label adjustment (removal of inconsistencies in the labels)  \
Model: 32,64,128,256 + 512 \
Score: 0.46906 on Kaggle\
/kaggle/working/submission_241203_155546.csv

## Unet with 32/64/128/256/512 bottleneck + geometric augm
Preprocessing: Normalisation (/255 --> anche per TEST SET!!), geometric augmentation (flip and rotation(+/180°)), only alien removal and label adjustment (removal of inconsistencies in the labels)  \
Model: 32,64,128,256 + 512 \
Score: 0.49359 on Kaggle and 48.79 validation Mean Intersection Over Union\
/kaggle/working/submission_241203_164321.csv

## Unet++ (file marsadjustedunet++)

## Unet (densely connected) with 32/64/128/256/512 bottleneck (file unet-512-densely-connected)
Preprocessing: Normalisation (/255 --> anche per TEST SET!!), NO augmentation, only alien removal, no label adjustment \
Model: 32,64,128,256 + 512. I connected all the upsampling layers to all the downsampling layers \
Score: 0.51146 on Kaggle and 48.73 validation Mean Intersection Over Union \
/kaggle/working/submission_UNet_48.73.csv

## Unet (densely connected) with 32/64/128/256/512 bottleneck (no file)
Preprocessing: Normalisation (/255 --> anche per TEST SET!!), NO augmentation, only alien removal, no label adjustment \
Model: 32,64,128,256 + 512. I connected all the upsampling layers to all the downsampling layers, **class weights added**\
Score: 0.5064 on Kaggle and 49.76 validation Mean Intersection Over Union \
submission_UNet_49.76.csv

## Unet (densely connected) with 32/64/128/256/512 bottleneck (file unet-512-densely-connected-balanced)
Preprocessing: Normalisation (/255 --> anche per TEST SET!!), NO augmentation, only alien removal, no label adjustment \
Model: 32,64,128,256 + 512. I connected all the upsampling layers to all the downsampling layers, class weights added and **higher patience (30) for dyn. learning rate** \
Score: 0.54698 on Kaggle and 51.91 validation Mean Intersection Over Union \
submission_UNet_51.91.csv
