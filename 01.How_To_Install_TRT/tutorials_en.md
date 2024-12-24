## 0. Pre-prepared Environment
In this project, we will use TensorRT 10.1 to study how to build an engine and run some inference examples. Users should have an environment with CUDA installed. My CUDA version is 12.1, and the cuDNN version is compatible. If you are not interested in setting up a local environment, you can use Docker images to build a container for this purpose.  

You can pull a Docker image with CUDA 12.1 using the following command:  
```docker pull nvcr.io/nvidia/pytorch:24.05-py3```  
After pulling the image, you can build a container based on it.

---

## 1. How to Install TensorRT  
If you have CUDA 12.1 and cuDNN installed, you can proceed to install TensorRT. Go to the [NVIDIA official website](https://developer.nvidia.com/tensorrt) to download the TensorRT package. You need to have an NVIDIA account to log in before downloading the TensorRT SDK.  

In this repository, we will use TensorRT 10.1, which can be found in the pre-release versions. Once you have downloaded the TensorRT SDK, unzip the package to your desired location. I suggest unzipping the package to `/usr/local` and renaming the folder to `tensorrt`, but you can modify the folder name as you like.  

For this guide, let's assume the TensorRT path is `/usr/local/tensorrt`. The next step is to add this path to the system path.  

```shell
vim ~/.bashrc
export LD_LIBRARY_PATH=/usr/local/tensorrt/lib:$LD_LIBRARY_PATH
export PATH=/usr/local/tensorrt/bin:$PATH
source ~/.bashrc
```

After completing these steps, we should verify the installation. Navigate to the following directory:  
```cd /usr/local/tensorrt/samples/sampleOnnxMNIST```  
Then type:  
```make```  

Wait a few seconds, and you will find an executable named `sample_onnx_mnist`. Run the executable:  
```./sample_onnx_mnist```  

If you see any output, it means the installation works!
