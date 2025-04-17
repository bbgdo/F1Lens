# F1Lens 
![funny_f1_fisheye_photo](static/mclaren_fisheye.jpg)

Цей проєкт — нейронна мережа для класифікації болідів Формули 1 за зображеннями.

## Датасет
### [Formula One Cars by Sagar Khanna (vesuvius13)](https://www.kaggle.com/datasets/vesuvius13/formula-one-cars)
#### Було проведено ручне очищення датасету: видалено нерелевантні зображення та зображення, які були не відповідали своїм класам. У результаті датасет зменшився більш ніж на чверть: з *2486* до *1677*

#### Команди у датасеті:
- Mercedes
- Ferrari
- McLaren
- Red Bull Racing
- AlphaTauri
- Williams
- Renault
- Racing Point

- Поділ датасету:
- - train (72% + augmentation 100% ) 
- - val (8%) 
- - test (20%)

## Результати базових тренувань
![base50_epochs](training-results/50_epochs.png)
```
10 епох
Точність: 0.1791
F1 Score: 0.0567

25 епох
Точність: 0.1716
F1 Score: 0.0499

50 епох
Точність: 0.2612
F1 Score: 0.1751
```

## Автоматизована оптимізація
За результатами автоматизованої оптимізації найкращими параметрами є:
```
{'lr': 0.0005566812682870772, 'optimizer': 'Adam'}
```
![f1](training-results/f1.png)
![train_acc](training-results/train_acc.png)
![val_acc](training-results/val_acc.png)
![train_loss](training-results/train_loss.png)
![val_loss](training-results/val_loss.png)

## Оптимізована модель
## Adam | LR 0.0005 | 50 epochs
![final_model_training](training-results/final_model_training.png)
```
Точність: 0.9851
F1 Score: 0.9832
```
![final_model_confusion](training-results/final_model_confusion.png)
![final_usage](training-results/final_usage.png)

## Transfer learning | MobilNetV2 (25 epochs)
![transfer_learning_accuracy](training-results/transfer_learning_accuracy.png)
![transfer_learning_loss](training-results/transfer_learning_loss.png)
```
Точність: 0.9179
F1 Score: 0.9137
```
![transfer_learning_confusion](training-results/transfer_learning_confusion.png)
![transfer_usage](training-results/transfer_usage.png)

## Старт
```bash
conda create -n F1Lens python=3.12
conda activate F1Lens

jupyter notebook F1Lens.ipynb
```