# MTP-BCR: Predicting up to 10 year breast cancer risk using longitudinal mammographic screening history

Risk assessment of breast cancer (BC) seeks to enhance individualized screening and prevention strategies. 
BC risk informs healthy individuals of the short- and long-term likelihood of cancer development, 
also enabling detection of existing BC. 
We present a temporospatial and explainable deep learning risk model, 
the **Multi-Time Point Breast Cancer Risk Model (MTP-BCR)**, 
which learns from longitudinal mammography data to identify subtle changes in breast tissue 
that may signal future malignancy. Utilizing a large in-house dataset of 171,168 screening mammograms 
from 42,792 consecutive exams involving 9,133 women, 
our model demonstrates a significant improvement in long-term (10-year) risk prediction 
with an area under the receiver operating characteristics (AUC) of 0.80. Furthermore, 
MTP-BCR provides unilateral breast-level predictions, achieving AUCs up to 0.81 and 0.77 for 5-year risk 
and 10-year risk assessments, respectively.

![ROC figures](figures/result.svg)

## Usage
### Environment
```bash
conda env create -f py37_environment.yml  # don't forget to change the path
conda activate py37
```

### Example training:
```bash
python src/train.py \
  --method side_specific_4views_mtp_tumor \
  --num-classes 16 \
  --test-num-classes 11 \
  --batch-size 8 \
  --num_time_points 6 \
  --use_risk_factors \
  --multi_tasks \
  --pooling last_timestep \
  --years_at_least_followup 0 \
  --results-dir ./log/Mammo_risk/
```

The configs above are meant to specify exact implementation details and our experimental procedure

### Example Result analysis

```
python result_anaysis/xxxxx.py  # pred to csv
python result_anaysis/xxxxx.py  # calculate AUC with CI and plot ROCs
```

### Predicting on External Dataset (not support yet!)
```
python src/custom_predict.py
```


## Disclaimer

This code and accompanying pretrained models are provided with no guarantees
regarding their reliability, accuracy or suitability for any particular
application and should be used for research purposes only. The models and code
are not to be used for public health decisions or responses, or for any
clinical application or as a substitute for medical advice or guidance.


## Citation
If you use this code or models in your scientific work, please cite the following paper:
```bibtex
@misc{****,
      title={Predicting up to 10 year breast cancer risk using longitudinal mammographic screening history}, 
      author={Xin Wang, Tao Tan, Yuan Gao, Ruisheng Su, Tianyu Zhang, Luyi Han, Jonas Teuwen, Anna D’Angelo, Caroline A. Drukker, Marjanka K. Schmidt, Regina Beets-Tan, Nico Karssemeijer and Ritse Mann},
      year={***},
      eprint={***},
      archivePrefix={***},
      primaryClass={***}
}
```

## License

The code is MIT licensed, as found in the [LICENSE file](LICENSE)

## Contact details
If you have any questions please contact us. 

Email: ritse.mann@radboudumc.nl (Ritse Mann); taotanjs@gmail.com (Tao Tan); x.wang@nki.nl (Xin Wang)

Links: [Netherlands Cancer Institute](https://www.nki.nl/), 
[Radboud University Medical Center](https://www.radboudumc.nl/en/patient-care) and 
[Maastricht University](https://www.maastrichtuniversity.nl/nl)

## Acknowledgements:
