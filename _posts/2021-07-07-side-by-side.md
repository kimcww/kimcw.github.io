---
title : "[Trouble Shoot] side by side
date : 2021-07-07
categories : Python
---

```python
```
import os
import sys

absolutepath = os.path.abspath(__file__)
print(absolutepath)

fileDirectory = os.path.dirname(absolutepath)
print(fileDirectory)
#Path of parent directory
parentDirectory = os.path.dirname(fileDirectory)

# 문제발생
    외부 dll load 하는데 side by side 이슈가 발생했다  
    
<br/>
![image](https://user-images.githubusercontent.com/42766429/124692542-ba230b00-df18-11eb-931e-6cfce5728311.png)


solution
1. ![image](https://user-images.githubusercontent.com/42766429/124693806-00796980-df1b-11eb-9511-56b460afa088.png)  
2. ![image](https://user-images.githubusercontent.com/42766429/124693834-0bcc9500-df1b-11eb-842c-31082f0c0765.png)  
3. ![image](https://user-images.githubusercontent.com/42766429/124693857-1850ed80-df1b-11eb-9426-6ada45d4c1ed.png)  
4. ![image](https://user-images.githubusercontent.com/42766429/124693891-2737a000-df1b-11eb-99b8-b9bd6f5254c9.png)  
5. ![image](https://user-images.githubusercontent.com/42766429/124694351-0face700-df1c-11eb-9519-a1b6ae26526a.png)



