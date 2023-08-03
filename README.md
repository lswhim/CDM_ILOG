# CDM_ILOG

:smile_cat: Welcome to **CDM_ILOG**, this is a comprehensive repository specializing in ***Cognitive Diagnosis Models*.**

------

## QCCDM-ECAI2023

We provide `QCCDM-ECAI23.pdf` and  `Appendix.pdf` in "papers" directory.

This repository has implementation of QCCDM: A Q-Augmented Causal Cognitive Diagnosis Model for Student Learning (**ECAI2023**) which lies in "method" directory.  If you're interested, please navigate to the method/QCCDM directory for more information.

> cd method/QCCDM

------

# Requirements

```python
EduCDM==0.0.13
joblib==1.2.0
numpy==1.23.5
pandas==1.5.3
scikit_learn==1.2.2
torch==1.13.1+cu117
tqdm==4.65.0
wandb==0.15.2
```

------

# Experiment

<u>We utilize **wandb**, a practical and effective package for visualizing our results. However, if you prefer not to use it, it can be easily disabled.</u> https://wandb.ai/

## QCCDM

We provide comprehensive instructions on how to run QCCDM in the "exps/QCCDM" directory. If you're interested, please navigate to the exps/QCCDM directory for more information.

> cd exps/QCCDM

------

# The File Tree

The file structure of this repository is as follows, and we will introduce each part one by one:

>
>     .
>     │  .gitattributes
>     │  .gitignore
>     │  LICENSE
>     │  README.md
>     │  requirements.txt
>     │
>     ├─data
>     │  │  data_analysis.py
>     │  │  data_params_dict.py
>     │  │
>     │  ├─junyi
>     │         ground_truth.xlsx
>     │         junyihier.csv
>     │         junyiTotalData.csv
>     │         q.csv
>     │         test_0.8_0.2.csv
>     │         train_0.8_0.2.csv
>     │  
>     │  
>     │          
>     │
>     ├─exps
>     │  └─QCCDM
>     │          exp-cdm-1.sh
>     │          exp-cdm.sh
>     │          exp.py
>     │          README.md
>     │
>     ├─method
>     │  │  __init__.py
>     │  │
>     │  ├─QCCDM
>     │        qccdm.py
>     │        __init__.py
>     │  
>     │  
>     │  
>     │  
>     │  
>     │          
>     │
>     ├─metrics
>     │     DOA.py
>     │     MAD.py
>     │     MLS.py
>     │  
>     │  
>     │          
>     │
>     ├─papers
>     │  └─QCCDM
>     │          Appendix.pdf
>     │          QCCDM_ECAI23.pdf
>     │
>     ├─plot
>     └─runners
>         ├─commonutils
>         │     datautils.py
>         │     util.py
>         │  
>         │  
>         │         
>         │          
>         │
>         └─QCCDM
>                cdm_runners.py
>                utils.py
>     

## Data

Here, we include Junyi, a real-world dataset collected from Junyi Academy that contains logs of students practicing math online. 

The data cleaning process was carried out as part of the HIERCDF project. For more information, you can visit the project's repository at https://github.com/CSLiJT/HCD-code.

- data_analysis.py: We provide some functions to analyze the response logs (i.e., average correct rate, sparsity)
- data_params_dict.py: This file stores a dictionary which allows you to retrieve basic attributes of the datasets, such as the number of students.
- ground_truth.xlsx: This Excel file contains the dependencies (DAG) among the knowledge concepts in the **matrix form**.
- junyihier.csv This file contains the dependencies (DAG) among the knowledge concepts in the **edge form**.
- junyiTotalData.csv: This file contains the total response logs in junyi.
- q.csv: This file contains the **Q-matrix** in junyi.
- train_0.8_0.2.csv and test_0.8_0.2.csv: These files are sourced from https://github.com/CSLiJT/HCD-code. We employ them to generate the "junyiTotalData.csv" file.

For more datasets, please visit https://github.com/bigdata-ustc/EduData to access a wider range of educational data resources.

## exps

We provide the execution entry for QCCDM experiments, along with shell script files for batch processing. For more details, please refer to the README file in the "exps/QCCDM" directory.

## metrics

We provide **three metrics** to evaluate the diagnostic results.

- DOA (Degree of Agreement): A interpretable metric which is utilized in current CDMs. Since there is no existing code available online, **we implemented it ourselves using numpy**.
- MAD (Mean Average Distance): This metric is used to measure the distance between the mastery levels of different students, and is often employed to examine whether the embedding result has an **over-smoothing** issue.
- MLS (Mastery Level Stability): This metric is used to assess the **stability** of diagnostic results under different seed settings.

## runners

- datautils.py: This file contains the dataloader for student performance prediction tasks.
- utils.py: This file contains various useful utility functions.
- QCCDM/cdm_runners.py: This file contains runner for QCCDM.
- QCCDM/utilis.py: This file contains useful utility functions for QCCDM.

------

# Our Paper

Shuo Liu, Hong Qian, Mingjia Li, Aimin Zhou "QCCDM: A Q-Augmented Causal Cognitive Diagnosis Model for Student Learning." In Proceedings of the 26th European Conference on Artificial Intelligence, 2023.

## Bibtex

> ```
> @inproceedings{liu2023ecai,
> author = {Shuo Liu, Hong Qian, Mingjia Li, Aimin Zhou},
> booktitle = {Proceedings of the 26th European Conference on Artificial Intelligence},
> title = {QCCDM: A Q-Augmented Causal Cognitive Diagnosis Model for Student Learning},
> year = {2023},
> address={Kraków, Poland}
> }
> ```

# Reference

[1]: https://dblp.org/search?q=Towards+a+New+Generation+of+Cognitive+Diagnosis	"Qi Liu. 2021. Towards a New Generation of Cognitive Diagnosis. In Proceedings of 30th International Joint Conference on Artificial Intelligence."
