
# Tutorial

hab hier mal einen entwurf angefangen, wie in etwa ich mir das vorstelle. muss natürlich dann am ende aktualisiert werden.

## Installation
- install git (for Windows [url]) or download the `.zip` file and unzip, e.g., in `C:\User\myusername\Documents\<ti-project-creak>`
- in anaconda, navigate to directory with code: `cd C:\User\myusername\Documents\<ti-project-creak>`
- run `pip install -e .`, wait until finished



## Usage

On first use, run the minimum working example to check if all is set up correctly:
- `run_mwe.py` oder so ähnlich
- this produces files xyz and should usually only take some seconds to process (depending on your computer but still <1minute).

This step only needs to be carried out once after installation!

### Set your configuration
Before you can run the code with your data, set the paths to your files in the configuration file `config/config.yaml`.
On Windows, replace the Backslashes `\` or `\\` in your path with single slashes `/` so that you get something like `C:/User/myusername/Documents/creak`

### Classify audio file
You can use the pretrained models to detect creak in your speech signals. For more information on the training process, see [Pretrained Model](#pretrained-model).
1. change paths as described [above](#set-your-configuration).
2. run script `xyz.py` and wait; note: takes approx. 3 times as long as the audio file on a computer with processor xyz, ...; so for longer sound files, you need to be patient

### Train on your own data
1. change paths as described [above](#set-your-configuration).
2. either use an existing `.TextGrid` file that contains any annotations or create a new one. Important: this file needs to have the exact same length as your audio file.
3. create a new tier where you label creaky segments with "c" and non-creaky segments with "nc":
  - make sure that you label only those segments with "nc" that potentially _could_ be creaky, i.e., voiced segments like vowels or sonorants; ![label example](label_example.png)
  - make sure that the number of "c" and "nc" labels are approximately the same. otherwise your classification performance will suffer from this.
change the tier name in your `.TextGrid` (or `.stg`) file to the tier where you labelled creaky and non-creaky segments
4. [optional] if you used other labels than the default labels `c` for creak, `nc` for no creak, change the values xyz in the config file


## Pretrained Model
We trained a model on xyz Austrian German speakers. (ggf. aufs paper referenzieren, falls das zeitlich irgendwie zusammenpasst; dann müsst ihr hier weniger schreiben)

## hinweis
- [ ] möglicherweise müsste man auch einen verweis auf die nutzung von den notebooks geben oder den code von den notebooks in python files stecken; können wir uns am ende überlegen. da würde ich mal abwarten, was anneliese dazu meint
