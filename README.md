# MTP-BCR: Predicting long term breast cancer risk using longitudinal mammographic screening history


## Usage
### Environment
```bash
conda env create -f py37_environment.yml
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



## Disclaimer

This code and accompanying pretrained models are provided with no guarantees
regarding their reliability, accuracy or suitability for any particular
application and should be used for research purposes only. The models and code
are not to be used for public health decisions or responses, or for any
clinical application or as a substitute for medical advice or guidance.




## License

The code is MIT licensed, as found in the [LICENSE file](LICENSE)

## Contact details
If you have any questions please contact us. 

Email: ritse.mann@radboudumc.nl (Ritse Mann); taotanjs@gmail.com (Tao Tan); x.wang@nki.nl (Xin Wang)

Links: [Netherlands Cancer Institute](https://www.nki.nl/), 
[Radboud University Medical Center](https://www.radboudumc.nl/en/patient-care) and 
[Maastricht University](https://www.maastrichtuniversity.nl/nl)

## Acknowledgements:
