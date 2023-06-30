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

### Pareper your dataset (coming soon):
```
xxxxxxxx  # pred to csv
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

@article {Wang2023.06.28.23291994,
	author = {Xin Wang and Tao Tan and Yuan Gao and Ruisheng Su and Tianyu Zhang and Luyi Han and Jonas Teuwen and Anna D{\textquoteright}Angelo and Caroline A. Drukker and Marjanka K. Schmidt and Regina Beets-Tan and Nico Karssemeijer and Ritse Mann},
	title = {Predicting up to 10 year breast cancer risk using longitudinal mammographic screening history},
	elocation-id = {2023.06.28.23291994},
	year = {2023},
	doi = {10.1101/2023.06.28.23291994},
	publisher = {Cold Spring Harbor Laboratory Press},
	abstract = {Risk assessment of breast cancer (BC) seeks to enhance individualized screening and prevention strategies. BC risk informs healthy individuals of the short- and long-term likelihood of cancer development, also enabling detection of existing BC. Recent mammographic-based deep learning (DL) risk models outperform traditional risk factor-based models and achieve state-of-the-art (SOTA) at short-term risk prediction, but mainly use single-time exams, which seem to rely more on detecting existing lesions. We present a novel temporospatial and explainable deep learning risk model, the Multi-Time Point Breast Cancer Risk Model (MTP-BCR), which learns from longitudinal mammography data to identify subtle changes in breast tissue that may signal future malignancy. Utilizing a large in-house dataset of 171,168 screening mammograms from 42,792 consecutive exams involving 9,133 women, our model demonstrates a significant improvement in long-term (10-year) risk prediction with an area under the receiver operating characteristics (AUC) of 0.80, outperforming the traditional BCSC 10-year risk model and other SOTA methods at 5-year AUC in various screening cohorts. Furthermore, MTP-BCR provides unilateral breast-level predictions, achieving AUCs up to 0.81 and 0.77 for 5-year risk and 10-year risk assessments, respectively. The heatmaps derived from our model may help clinicians better understand the progression from normal tissue to cancerous growth, enhancing interpretability in breast cancer risk assessment.Competing Interest StatementThe authors have declared no competing interest.Funding StatementThis study was funded by Chinese Scholarship Council scholarship (CSC)Author DeclarationsI confirm all relevant ethical guidelines have been followed, and any necessary IRB and/or ethics committee approvals have been obtained.YesThe details of the IRB/oversight body that provided approval or exemption for the research described are given below:This study was approved by the Netherlands Cancer Institute(NKI) institutional review board.I confirm that all necessary patient/participant consent has been obtained and the appropriate institutional forms have been archived, and that any patient/participant/sample identifiers included were not known to anyone (e.g., hospital staff, patients or participants themselves) outside the research group so cannot be used to identify individuals.YesI understand that all clinical trials and any other prospective interventional studies must be registered with an ICMJE-approved registry, such as ClinicalTrials.gov. I confirm that any such study reported in the manuscript has been registered and the trial registration ID is provided (note: if posting a prospective study registered retrospectively, please provide a statement in the trial ID field explaining why the study was not registered in advance).Yes I have followed all appropriate research reporting guidelines, such as any relevant EQUATOR Network research reporting checklist(s) and other pertinent material, if applicable.YesThe inhouse dataset is used under license to the respective hospital system for the current study and is not publicly available.},
	URL = {https://www.medrxiv.org/content/early/2023/06/29/2023.06.28.23291994},
	eprint = {https://www.medrxiv.org/content/early/2023/06/29/2023.06.28.23291994.full.pdf},
	journal = {medRxiv}
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
