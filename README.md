# gpuheater

<p align="center"> English | <a href="README_zh_Hans.md">中文</a></p>

In the harsh winter, with lackluster air conditioning and heating, it's time to use GPUs for heating.

GPU, start!

## Installation

prerequisite: cudatoolkit

```bash
# pip install git+https://github.com/sword4869/gpuheater.git
pip install gpuheater
```

## Running

- Specify which GPUs
    ```bash
    # use all gpus
    # gpuheater --device_index 0 1
    $ gpuheater
    device_index [0, 1]
    Fan speed   |  Temperature  |  GPU utilization   |        Memory Free/Memory Total        
        22% 0%     |   60C 59C     |     100% 100%      |   1855MiB/11264MiB 1423MiB/11264MiB    

    # use the second gpu
    $ gpuheater --device_index 1
    device_index [1]
    Fan speed   |  Temperature  |  GPU utilization   |        Memory Free/Memory Total        
        0%       |     57C       |       100%         |           1423MiB/11264MiB
    ```
- Decide to use a certain amount of free memory size (default of 10%)
    
    The size of free memory does not refer to the total memory size, but to the available free memory. So, it will not interfere with already running applications.

    ```bash
    # Only 1%
    $ gpuheater --memory_free_percent 1 
    device_index [0, 1]
    Fan speed   |  Temperature  |  GPU utilization   |        Memory Free/Memory Total        
    25% 20%     |   57C 50C     |      37% 34%       |  920.1MiB/11264MiB 442.9MiB/11264MiB    
    ```

- type in `q` (and enter) or ctrl-c to exit