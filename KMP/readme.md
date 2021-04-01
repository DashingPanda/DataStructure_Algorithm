## 对KMP算法中的 k=next[k]的理解

当p[k]和p[j]在不匹配发生时，next[j+1]的取值各不相同，而k = next[k]可以很好的识别出来；
前提是已知next[j]和k的值，求next[j+1]的值
有前提可知 p[0]p[2]…p[k-1] == p[j-k]p[j-k+1]…p[j-1]
但是p[k] != p[j]，那我们就应该找稍微短一些的匹配前后缀串
next[k]的意义是在模式串的k角标之前的匹配的前后缀串的长度
也就是存在一个k’，使得p[0]p[1]…p[k’-1] == p[k-k’]p[k-k’+1]…p[k-1]
结合前提推得 p[0]…p[k’-1] == p[j-k’]p[j-k’-1]…p[j-1];
而p[0-(j-1)]的这个串里面存在多对前后缀串；
详细分析可以结合图片理解：
![avatar](https://github.com/DashingPanda/DataStructure_Algorithm/blob/main/KMP/images/KMP1.png)

      
      
## 模式串和母串匹配过程的理解看下面视频：    
[![Watch the video](https://github.com/DashingPanda/DataStructure_Algorithm/blob/main/KMP/images/KMP2.png)](https://pan.baidu.com/play/video#/video?path=%2F%E6%95%B0%E6%8D%AE%E7%BB%93%E6%9E%84%E4%B8%8E%E7%AE%97%E6%B3%95%E8%A7%86%E9%A2%91%2FKMP%2FTo_Understand_KMP.mp4&t=-1)
