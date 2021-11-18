PyTorch 中有数据集接口 torch.utils.data.Dataset，它们实现了____getitem____ 和 __len____ ，因此构造的实现就是对这个函数的实现。Pytorch中含后大量的自带数据集借口，但在比赛中数据集往往需要自己构造。

构建自己的Dataset必须对 __init__、__getitem__ 和 __len__ 方法进行重载

```python

from torch.utils.data.dataset import Dataset

class MyDataset(Dataset):  # 继承Dataset类
   def __init__(self):
       # 初始化图像文件路径或图像文件名列表等
       pass
   
   def __getitem__(self, index):
        # 1.根据索引index从文件中读取一个数据（例如，使用numpy.fromfile，PIL.Image.open，cv2.imread）
        # 2.预处理数据（例如torchvision.Transform）
        # 3.返回数据对（例如图像和标签）
       pass
   
   def __len__(self):
       return count  # 返回数据量
```
