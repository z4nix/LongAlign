## Needle Test Evaluation

**Reconstruction of the original "Needle In A Haystack - Pressure Test" [code](https://github.com/gkamradt/LLMTest_NeedleInAHaystack) to add support for evaluating HuggingFace models. The evaluation procedure involves 3 steps: *Test prompt generation*, *model predicting*, and *scoring*.**

It is assumed that the config files are in the same directory as the corresponding scripts.

### Test prompt generation

Configure the test parameters in `config-prompt.yaml`, then run
```bash
python prompt.py
```
The test prompts will be generated under `prompts/`.

### Model predicting

Set your model details (Kaggle implementation) in `config-pred.yaml`, then run
```bash
CUDA_VISIBLE_DEVICES=0 python pred.py
```
The model prediction will be saved under `pred/`.

### Scoring

Configure your scoring model (default as `gpt-4`) in `config-eval.yaml`, and your API key in `eval.py`. Run
```bash
python eval.py
```
The scoring result will be saved as *json* under `results/`.

Finally, visualize your result with
```bash
python vis.py
```
This script assumes that the results directory is in the same directory as the script.
