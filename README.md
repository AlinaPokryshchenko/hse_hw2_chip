# hse_hw2_chip
[Colab](https://colab.research.google.com/drive/1cT7HwhwYVLE4CRWp5uif2d7cwLc83sz1?usp=sharing)
В работе была использована клеточная линия DOHH2 и гистоновая метка H3F3A

Изначально по результатам FastQC В образцах наблюдалось не очень хорошее качество ридов, в связи с чем был применем trimmomatic ко всем образцам. Ниже представлены результаты по всем образцам до и после применения trimmomatic. 

## Результаты FastQC

##### Для ENCFF321ZLW
До                                        | После
----------------------------------------- | ----------------------------------------
![ENCFF321ZLW_1](ENCFF321ZLW_fastqc_1.png)|![ENCFF321ZLW_2](ENCFF321ZLW_fastqc_1.png)
![ENCFF321ZLW_3](ENCFF321ZLW_fastqc_3.png)|![ENCFF321ZLW_4](ENCFF321ZLW_fastqc_4.png)
![ENCFF321ZLW_5](ENCFF321ZLW_fastqc_5.png)|![ENCFF321ZLW_6](ENCFF321ZLW_fastqc_6.png)
![ENCFF321ZLW_7](ENCFF321ZLW_fastqc_7.png)|![ENCFF321ZLW_8](ENCFF321ZLW_fastqc_8.png)

##### Для ENCFF954XHM
До                                        | После
----------------------------------------- | ----------------------------------------
![ENCFF954XHM_1](ENCFF954XHM_fastqc_1.png)|![ENCFF954XHM_2](ENCFF954XHM_fastqc_2.png)
![ENCFF954XHM_3](ENCFF954XHM_fastqc_3.png)|![ENCFF954XHM_4](ENCFF954XHM_fastqc_4.png)
![ENCFF954XHM_5](ENCFF954XHM_fastqc_5.png)|![ENCFF954XHM_6](ENCFF954XHM_fastqc_6.png)
![ENCFF954XHM_7](ENCFF954XHM_fastqc_7.png)|![ENCFF954XHM_8](ENCFF954XHM_fastqc_8.png)

##### Для ENCFF002AYR
До                                        | После
----------------------------------------- | ----------------------------------------
![ENCFF002AYR_1](ENCFF002AYR_fastqc_1.png)|![ENCFF002AYR_2](ENCFF002AYR_fastqc_2.png)
![ENCFF002AYR_3](ENCFF002AYR_fastqc_3.png)|![ENCFF002AYR_4](ENCFF002AYR_fastqc_4.png)
![ENCFF002AYR_5](ENCFF002AYR_fastqc_5.png)|![ENCFF002AYR_6](ENCFF002AYR_fastqc_6.png)
![ENCFF002AYR_7](ENCFF002AYR_fastqc_7.png)|![ENCFF002AYR_8](ENCFF002AYR_fastqc_8.png)

## Статистика по чтениям

Chip-seq sample| Total reads| Aligned exactly 1 time| Aligned >1 times| aligned 0 times
---------------|----------------------------------|----------------|---------------|--------
ENCFF321ZLW    |29960272                          |1122408 (3.75%) |2744901 (9.16%)|26092963 (87.09%)
ENCFF954XHM|41182404|1518886 (3.69%)|3708054 (9.00 %)|35955464 (87.31%)
ENCFF002AYR|31731860|1272850 (4.01%)|4051654 (12.77%)|26407356 (83.22%)

## Сравнение результатов

Проанализируйте выдачу bowtie. Почему процент выравниваний получился именно таким?
Имеет смысл для дальнейшего анализа отобрать уникально картированные риды.

Сравниваем те пики, которые мы получили, с пиками, которые приведены в ENCODE (важно, чтобы версии генома hg38 или hg19) для .bed файла из ENCODE и той хромосомы, которую скачивали выше, сопадали.
Проанализируйте полученные результаты и приведите свои рассуждения в README.md. Как можно объяснить различия в количестве пересечений?

