# gpuheater

<p align="center"> <a href="README.md">English</a> | 中文</p>

严冷的冬天，乏善可陈的空调和暖气，是时候用GPU来取暖了。

GPU，启动！

## 安装

预先安装：cudatoolkit

```bash
# pip install git+https://github.com/sword4869/gpuheater.git
pip install gpuheater
```

## 运行

- 指定哪些GPU
    ```bash
    # 使用所有gpu
    # gpuheater --device_index 0 1
    $ gpuheater
    device_index [0, 1]
    Fan speed   |  Temperature  |  GPU utilization   |        Memory Free/Memory Total        
        22% 0%     |   60C 59C     |     100% 100%      |   1855MiB/11264MiB 1423MiB/11264MiB    

    # 使用第二个gpu
    $ gpuheater --device_index 1
    device_index [1]
    Fan speed   |  Temperature  |  GPU utilization   |        Memory Free/Memory Total        
        0%       |     57C       |       100%         |           1423MiB/11264MiB
    ```
- 决定使用一定程度的空闲内存大小（默认10%）
    
    空闲内存大小，并不是指总内存大小，而是可用的空闲内存。所以，它不会干扰已经运行的应用。
    ```bash
    # 仅用1%
    $ gpuheater --memory_free_percent 1 
    device_index [0, 1]
    Fan speed   |  Temperature  |  GPU utilization   |        Memory Free/Memory Total        
    25% 20%     |   57C 50C     |      37% 34%       |  920.1MiB/11264MiB 442.9MiB/11264MiB    
    ```

- 输入 q(且回车) 或者 ctrl-c 来退出