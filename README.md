# hse_hw2_chip
[Colab](https://colab.research.google.com/drive/1cT7HwhwYVLE4CRWp5uif2d7cwLc83sz1?usp=sharing)

В работе была использована клеточная линия DOHH2 и гистоновая метка H3F3A
Реплика 1 - ENCFF321ZLW; Реплика 2 - ENCFF954XHM; Контроль - ENCFF002AYR

Изначально по результатам FastQC В образцах наблюдалось не очень хорошее качество в конце ридов, что в целом свойственно для Illumina. GC состав не идеален, однако это зависит от изначального качества ридов. В связи с чем был применем trimmomatic ко всем образцам. Ниже представлены результаты по всем образцам до и после применения trimmomatic. 

## Результаты FastQC

##### Для ENCFF321ZLW
До                                        | После
----------------------------------------- | ----------------------------------------
![ENCFF321ZLW_1](/images/ENCFF321ZLW_fastqc_1.png)|![ENCFF321ZLW_2](/images/ENCFF321ZLW_fastqc_1.png)
![ENCFF321ZLW_3](/images/ENCFF321ZLW_fastqc_3.png)|![ENCFF321ZLW_4](/images/ENCFF321ZLW_fastqc_4.png)
![ENCFF321ZLW_5](/images/ENCFF321ZLW_fastqc_5.png)|![ENCFF321ZLW_6](/images/ENCFF321ZLW_fastqc_6.png)
![ENCFF321ZLW_7](/images/ENCFF321ZLW_fastqc_7.png)|![ENCFF321ZLW_8](/images/ENCFF321ZLW_fastqc_8.png)

##### Для ENCFF954XHM
До                                        | После
----------------------------------------- | ----------------------------------------
![ENCFF954XHM_1](/images/ENCFF954XHM_fastqc_1.png)|![ENCFF954XHM_2](/images/ENCFF954XHM_fastqc_2.png)
![ENCFF954XHM_3](/images/ENCFF954XHM_fastqc_3.png)|![ENCFF954XHM_4](/images/ENCFF954XHM_fastqc_4.png)
![ENCFF954XHM_5](/images/ENCFF954XHM_fastqc_5.png)|![ENCFF954XHM_6](/images/ENCFF954XHM_fastqc_6.png)
![ENCFF954XHM_7](/images/ENCFF954XHM_fastqc_7.png)|![ENCFF954XHM_8](/images/ENCFF954XHM_fastqc_8.png)

##### Для ENCFF002AYR
До                                        | После
----------------------------------------- | ----------------------------------------
![ENCFF002AYR_1](/images/ENCFF002AYR_fastqc_1.png)|![ENCFF002AYR_2](/images/ENCFF002AYR_fastqc_2.png)
![ENCFF002AYR_3](/images/ENCFF002AYR_fastqc_3.png)|![ENCFF002AYR_4](/images/ENCFF002AYR_fastqc_4.png)
![ENCFF002AYR_5](/images/ENCFF002AYR_fastqc_5.png)|![ENCFF002AYR_6](/images/ENCFF002AYR_fastqc_6.png)
![ENCFF002AYR_7](/images/ENCFF002AYR_fastqc_7.png)|![ENCFF002AYR_8](/images/ENCFF002AYR_fastqc_8.png)

## Статистика по чтениям
Перед применением trimmomatic я провела анализ неизмененных fastq файлов, в целом, можно отметить, что в них наблюдался меньший процент уникально или выровненных более чем 1 раз ридов. Ниже же приведены результаты отработки программы для trimmed образцов. 

Chip-seq sample| Total reads| Aligned exactly 1 time| Aligned >1 times| aligned 0 times
---------------|--------------------------------|----------------|---------------|--------
ENCFF321ZLW|29960272|1122408 (3.75%)|2744901 (9.16%)|26092963 (87.09%)
ENCFF954XHM|41182404|1518886 (3.69%)|3708054 (9.00 %)|35955464 (87.31%)
ENCFF002AYR|31731860|1272850 (4.01%)|4051654 (12.77%)|26407356 (83.22%)

Мы выравнивали риды лишь на одну из 23 хромосом, поэтому процент выравнивания так низок.
## Сравнение результатов

#### Пересечение пиков 1 реплики с пиками ENCODE
![venn_1](/images/venn_1.png)
#### Пересечение пиков ENCODE с пиками 1 реплики
![venn_2](/images/venn_2.png)
#### Пересечение пиков 2 реплики с пиками ENCODE
![venn_3](/images/venn_3.png)
#### Пересечение пиков ENCODE с пиками 2 реплики
![venn_4](/images/venn_4.png)

Вывод по диаграммам: количество пиков малое, и, соответственно, пересечений мало, потому что мы провели лишь на одну хромосому. 
В образце из базы данных ENCODE пики указаны для всех хромосом. 
Цифры в пересечении наших пиков с пиками ENCODE и в пересечении пиков ENCODE с нашими пиками разнятся, поскольку в первом случае считается число таких пиков в первом файле, которые есть и во втором, а во втором случае подсчет производится наоборот (считаем число таких пиков во втором файле, которые есть и в первом файле) 

## Бонус
#### Heat maps для двух экспериментов
![heat_1](/images/heat_map_1.png)
![heat_2](/images/heat_map_2.png)
Если сравнить полученные heat map между собой, то мы заметим, что они практически идентичны. 
Есть общая информация о типичном расположении гистоновой метки относительно генов (участков транскрипции). Задача посмотреть согласуется ли данные ChIP-seq эксперимента из ENCODE для выбранной гистоновой метки с картинкой ниже. Распределение сигнала метки из ENCODE эксперимента относительно генов можно получить с помощью программы ngs.plot (т.н. meta-gene plot) Это можно сделать с помощью ngs.plot.

