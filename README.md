# Natural-Language-Inference.
В каждом объекте исходного датасета даны два предложения на английском и их метки, которые показывают насколько связаны данные предложения. Класс с меткой С (сontradiction) обозначает, что два предложения противоречат друг другу, метка N (neutral), что предложения нейтральны относительно друг друга, E (entailment) задаёт предложения логически связанные друг с другом. Необходимо для каждого объекта тестовой выборки предсказать метку класса. (https://nlp.stanford.edu/projects/snli/)   
![image](https://user-images.githubusercontent.com/49073655/118476084-c0191e80-b715-11eb-8613-d85bab4c09dc.png)
### Exploratory data analysis.
На данном этапе анализируется количество слов в каждом примере для первого и второго предложения, затем с помощью библиотеки nltk каждому предложению сопоставляется список из частей речи, использованных в нём. Всё это отображается в виде различных графиков и гистограмм.
### Feature engineering.
В данном разделе из каждой пары предложений формируется 6 новых признаков: BLEU score, overlap между словами, overlap между существительными, глаголами, прилагательными и наречиями, индикаторы униграмм и биграмм, индикаторы кросс-униграмм и кросс-биграмм. Данные признаки описаны в статье (https://nlp.stanford.edu/pubs/snli_paper.pdf).
### ML.
1. Обучается логистическая регрессия на вышеупомянутых 6 признаках, далее проверяются результаты на тестовых данных. 
2. Строится модель, которая с помощью берта имбедит два предложения, затем данные два имбеда подаются на вход персептрону и на выходе получаем метку класса. Затем модель оценивается на тестовых данных.


