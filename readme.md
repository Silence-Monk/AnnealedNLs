# Deep Facial Expression Recognition via Annealed Negative Sampling

## Usage

### 1. download FER2013 dataset
https://drive.google.com/drive/folders/18ovcnZBsPvwXXFVAqczACe9zciO_1q6J?usp=drive_open

### 2. modify config file
example: configs/fer2013_config.json
```json
{
	"data_path": "data",
	"image_size": 224,
	"in_channels": 3,
	"num_classes": 7,
	"arch": "resnet34",
	"lr":  0.0001,
	"weighted_loss": 0,
	"momentum": 0.9,
	"weight_decay": 0.001,
	"distributed": 0,
	"batch_size": 48, 
	"num_workers": 8,
	"device": "cuda:0",
	"max_epoch_num": 50,
	"max_plateau_count": 8,
	"plateau_patience": 2,
	"steplr": 50,
	"log_dir": "log",
	"checkpoint_dir": "checkpoint",
	"model_name": "test",
	"ln_neg": 200,
	"ln_neg_min": 10
}

```
* \# of NLs: 200 -> 10
### 3. run python script
```shell
python main_fer2013.py
```

## *project inherits from https://github.com/phamquiluan/ResidualMaskingNetwork