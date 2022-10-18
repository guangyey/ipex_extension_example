# Intel® Extension for PyTorch* GPU
This is an extension example for Intel® Extension for PyTorch* GPU 1.10.
# Build with CMake
```
$cmake -DCMAKE_PREFIX_PATH="/home/gta/miniconda3/envs/guangyey/lib/python3.10/site-packages/torch/share/cmake;/home/gta/miniconda3/envs/guangyey/lib/python3.10/site-packages/intel_extension_for_pytorch/share/cmake" -DCMAKE_C_COMPILER=icx -DCMAKE_CXX_COMPILER=dpcpp 
$make
```
# Build with setuptools
```
python setup.py install
```
