https://blog.csdn.net/liugallup/article/details/51164962  
https://blog.csdn.net/u012871493/article/details/72782744  
https://www.jiqizhixin.com/articles/2018-07-05-20  
https://juejin.im/entry/58d8ae23a22b9d00646bde92  
https://www.leiphone.com/news/201701/W2G0J9H3TeTziXKp.html  
https://arxiv.org/abs/1712.03376  
http://www.aclweb.org/anthology/W16-5307  
http://aclweb.org/anthology/C18-1030  
https://web.stanford.edu/class/cs224n/reports/2762042.pdf  
https://yq.aliyun.com/articles/586761  
https://www.zhihu.com/question/30402861  
https://blog.csdn.net/u013378306/article/details/64441250?locationNum=7&fps=1  
http://www.sohu.com/a/124709523_465975  
https://github.com/Jeff09/Word-Sense-Disambiguation-using-Bidirectional-LSTM  
  
  
# 29/10/2018

meaning of basic tags  
    # https://blog.csdn.net/u013378306/article/details/64441250?locationNum=7&fps=1

fastText + RNN  
    # https://www.jiqizhixin.com/articles/2018-07-05-20  
    generate training set - manually label small part, then use semi-supervised approach to enlarge the set  
        cooccurance of words to label the sentence  
    fastText - classifies the context to tell if the context in which the target term has the target meaning 
    RNN - fix the imbalance problem
    
fastText + TextCNN + TextRNN  
    # https://juejin.im/entry/58d8ae23a22b9d00646bde92  
    Hyper-parameter tuning - A Sensitivity Analysis of (and Practitioners’ Guide to) Convolutional Neural Networks for Sentence Classification  

Wordnet Mappings  
    # https://www.leiphone.com/news/201701/W2G0J9H3TeTziXKp.html
    https://arxiv.org/abs/1603.07012
    
train multiple vectors  
    GloVe
        # https://www.zhihu.com/question/30402861  
    https://blog.csdn.net/sinat_26917383/article/details/54847240
    
    
    
    
    
    
## Idea  
1. Google API to get the negative samples  
2. tweet to get the positive samples  
3.  
    1. cleaning the $ tag and lower all cases
    2. if the text contain the targets  
    3. ticker classification -> context classification  
        use RNN to do the classification?













    
    
    
