# audio-synthesis
This github is about Speech synthesis using tensorflowTTS api. TensorflowTTS has benchmark models such as tacotron2, fastSpeech2 along with vocoder models such as multi-band melgan, Hifi-gan for text-to-speech

## Installation procedure
1st, I checked the requirements to pip install for [tensorflowTTS](https://github.com/TensorSpeech/TensorFlowTTS) from ttheir github, then, I created a python environment using conda. 

```
conda create -n tensorflowTTS python=3.10
```
Then, I checked what is breaking with tensorflowTTS api. Tried tensorflow version 2.12.0 as following:
```
pip install tensorflow[and-cuda] ==2.12.0
pip install tfa-nightly
```
Export necessary path if needed,
```
export CUDNN_PATH=$(dirname $(python -c "import nvidia.cudnn;print(nvidia.cudnn.__file__)"))
export LD_LIBRARY_PATH=${CUDNN_PATH}/lib
```
I faced some issues with official tensorflowTTS. Therefore, used the following one.
```
pip install git+https://github.com/MohmedAAK/TensorFlowTTS
```
An error message says to downgrade the protobuf package
```
pip install "protobuf<=3.20"
```
if something breaks again, then it might be for scipy. Use the following version:
```
pip install "scipy<=1.12"
```
At the end, there may be a necessity for upgrading pip if the above process doesn't work. Make sure you have avaiable cuda version as well. 
