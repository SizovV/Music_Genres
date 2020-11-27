## Классификация музыкальных произведений по жанрам
### Authors:   
  - Дживеликян Е.А.
- Латышев А.К. 
- Сизов В.С.    

---


Национальный исследовательский университет ``Московский физико-технический институт''

### Проект по МИИАД, часть 1

| Модель | F1 | Параметры | Время обучения|ЭВМ |
|:----|:----:|:----:|:----:|:----------:|
| SVC                          | 59.92 | kernel=’rbf’ C=3 | 20.2 секунды  |Intel(R) Xeon(R) CPU @ 2.30GHz Google Colaboratory |
| Random Forest Classifier     | 56.23 | n_estimators=500 class_weight=’balanced’ | 28 секунд     |Intel Core i9 2400 GHz |
| Gradient Boosting Classifier | 57.13 | learning_rate=0.05 max_depth=5 n_estimators=200 subsample=0.5 | 3 минуты 32 секунды |AMD Razen 5 3500U 2100 MHz |
| Logistic Regression          | 53.22 | solver=’liblinear’ class_weight=’balanced’ multi_class =’ovr’ | 46 секунд     |Intel Core i9 2400 GHz|
