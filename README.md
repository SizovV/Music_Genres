Министерство науки и высшего образования Российской Федерации

Федеральное государственное автономное образовательное учреждение высшего образования 

**«Московский физико-технический институт (национальный исследовательский университет)»**

**Физтех-школа прикладной математики и информатики**

Магистерская программа «Методы и технологии искусственного интеллекта»

---

# Классификация музыкальных произведений по жанрам

**Авторы:**   
- Дживеликян Е.А.
- Латышев А.К. 
- Сизов В.С.

**Результаты:**
[Презентация](presentation.pdf)  
**Датасет:**
[FMA. A Dataset For Music Analysis](https://github.com/mdeff/fma)

---
## Первая часть проекта
[Тетрадка](part_1.ipynb)  
**Признаки:**
[Темп-MFCC-HP-Tonnetz + метки классов](https://drive.google.com/file/d/1_l37zHMwYQLEliCqQ3TGPT0zdXxKnS07/view?usp=sharing)

| Модель | F1 | Параметры | Время обучения|ЭВМ |
|:----|:----:|:----:|:----:|:----------:|
| SVC                          | 59.92 | kernel=’rbf’ C=3 | 20.2 секунды  |Intel(R) Xeon(R) 2CPU @ 2.30GHz Google Colaboratory |
| Random Forest Classifier     | 56.23 | n_estimators=500 class_weight=’balanced’ | 28 секунд     |Intel Core i9 2400 GHz |
| Gradient Boosting Classifier | 57.13 | learning_rate=0.05 max_depth=5 n_estimators=200 subsample=0.5 | 3 минуты 32 секунды |AMD Razen 5 3500U 2100 MHz |
| Logistic Regression          | 53.59 | C=0.01, solver='lbfgs', multi_class='multinomial' | 516 милисекунд     |AMD Razen 5 3500U 2100 MHz 8CPU|
| CatBoost                     | 59.34 | iterations=800, depth=6, bagging_temperature=0.5, l2_leaf_reg=0| 3 минуты 28 секунд |AMD Razen 5 3500U 2100 MHz 8CPU|

---
## Вторая часть проекта
### Эмбединги
Вычисление эмбеддингов проводилось с помощью обученной на датасете Audoiset нейронной сети архитектуры [VGG](https://github.com/tensorflow/models/tree/master/research/audioset/vggish).  
[Тетрадка](compute_embeddings.ipynb)  
[VGG Embeddings + метки классов](https://drive.google.com/file/d/184k-41ytAEg2ibZKqJHh3IcgWEw-FkjP/view?usp=sharing)  
### Обучение
**Разбиение на train, valid, test выборки:**
[id треков](https://drive.google.com/file/d/1PpP3HXTFQSctKoG3SkhrprtUH1TrG-4q/view?usp=sharing)  
[Полносвязные архитектуры](part_2FCNN.ipynb)  
[Рекуррентные архитектуры](part_2RNN.ipynb)  
[Свёрточные архитектуры](part_2CNN.ipynb)


| Модель | F1 |  ЭВМ |
|:----|:----:|:----------:|
| LofReg (BaseLine)  | 52.63 | AMD Razen 5 3500U 2100 MHz  |
| LSTM               | 54.01 |NVIDIA Tesla T4 Google Colaboratory |
| Fully Connected NN | 48.32 |NVIDIA Tesla T4 Google Colaboratory |
| CNN                | 49.01 |NVIDIA Tesla T4 Google Colaboratory|



