This repository contains code and config files supporting the following blog post:

https://medium.com/@shashankprasanna/running-rapids-experiments-at-scale-using-amazon-sagemaker-d516420f165b


## My own Comments

- Sagemaker SDK needed a role to be created in AWS IAM. the role could not be passed to the root user so another user was created with full admin priviledges.

- The HIGGs data is TOO BIG for my tinny 1070, (7GB), so we changed the amount of lines loaded to 1/10 of original, ie. 1M lines.

```bash
(base) fabio@dorothy:/work/fabiononato/gitlocal/ext/sagemaker-rapids$ du -d 1 -h dataset/
7.5G	dataset/
(base) fabio@dorothy:/work/fabiononato/gitlocal/ext/sagemaker-rapids$ wc -l dataset/HIGGS.csv 
11000000 dataset/HIGGS.csv

```

- raised an issue about .to_gpu_array(): [Link](https://github.com/shashankprasanna/sagemaker-rapids/issues/1) 
