# Дипломный проект. 
# Решение задачи бинарной классификации грибов по их внешним параметрам


## Оглавление
[1. Постановка задачи]()

[2. Исследование структуры данных]()

[3. Предобработка данных]()

[4. Преобразование данных]()

[5. Решение задачи классификации: стандартные модели]()

[6. Решение задачи классификации: ансамбли моделей]()

[7. Решение задачи классификации: нейросеть]()

[Результаты]()



### Постановка задачи

Обоснование выбора темы:
В связи с тематикой моей профессии мне часто приходится решать задачи классификации. Поскольку исходные данные для решаемых мною задач имеют гриф, а мне хотелось написать диплом максимально приближенным к моей работе, для выполнения диплома пришлось скачать общедоступный DataSet для бинарной классификации по категориальным признакам.

В выбранном наборе данных представлены внешние параметры для 8124 грибов с указанием их класса: съедобные и ядовитые.
Целью работы является построение математической модели классификации грибов на основании 22 категориальных признаков.
Краткая информация о данных:
* mushroom.csv - файл с исходными данными, 
данные заимствованы на платформе Kaggle: https://www.kaggle.com/datasets/ulrikthygepedersen/mushroom-attributes?resource=download


### Исследование структуры данных

Проведены: 
1.анализ типов данных, статистических параметров признаков; 
2 проверка на наличие пропусков и дубликатов в данных; 
3.проверка на сбалансированность данных.

### Предобработка данных
Проведены:
1. Исследование корреляционных связей между признаками и целевой величиной;
2. Проверка на наличик линейнозависимых строк корреляционной матрицы признаков;
3. Удаление неинформативных признаков;
4. Проверка на возможность сочетания признаков для формирования новых.

### Преобразование данных
Проведены:
1. Кодирование признаков;
2. Построение и анализ корреляционной матрицы после перекодировки;
3. Отбор информативных признаков после перекодировки.

### Решение задачи классификации: стандартные модели
Построены модели:
1. Логистической регрессии;
2. Решающие деревья;
3. Метод опорных векторов.

Осуществлен подбор параметров для всех моделей

### Решение задачи классификации: ансамбли моделей
Построены модели:
1.Случайный лес;
2. Адаптивный бустинг;
3. Градиентный бустинг;
4. VotingClassifier;
5. Стекинг

Осуществлен подбор гиперпараметров для всех моделей

### Решение задачи классификации: нейросеть
Построена модель однослойной полносвязной нейросети.

### Результаты

В процессе работы было проведено исследование возможности бинарной классификации грибов по их внешним параметрам. Проведен анализ данных, оценена значимость признаков, составлен набор оптимальной комбинации линейно независимых признаков. Исследование показало, что результаты классификации для всех всех рассмотренных типов моделей (логистическая регрессия, решающее дерево, метод опорных векторов, нейронная сеть), а также ансамблей (случайный лес, адаптивный бустинг, градиентный бустинг, VotingClassifier, стекинг) дает однинаковые метрики качества (accracy = 0.96, f1 = 0.96). Из чего следует, что оставшаяся часть неверно классифицированных данных не может быть разделена на верные классы в рассматриваемом пространстве признаков. Поэтому целесообразно использовать для решения поставленной задачи наиболее простую в обучении и применении модель - логистическую регрессию со следующими параметрами: C=0.001, penalty='none', solver ='lbfgs', max_iter=1000
