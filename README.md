# Seaborn

##以下是heatmap，热力图的画法
```
import pandas as pd
import seaborn as sns
import numpy as np
import matplotlib.pyplot as plt

%config InlineBackend.figure_format = 'retina'
```

#如何把一列数据转为行
```
data_new = data.set_index(['Year','Month'])['Anomaly'] #这个就是把year当成一列，然后month展开，也就是拆分开，成为每列列表
data_new = data_new.unstack()
data_new = data_new.unstack()
data_new = data_new.rename_axis(columns=None)
data_new.set_index(['Year'],inplace = True) #这行是取消原本的index，用 year作为index
```

```
plt.subplots(figsize=(20,18)) # 设置画布大小
pic = sns.heatmap(data3,vmin=-1, vmax = 1.5,cmap='RdBu_r') #vmin是设置最小值、vmax是最大值，然后cmap是颜色
pic2 = pic.get_figure()
#pic2.savefig('pic2.svg')
plt.show()
```
