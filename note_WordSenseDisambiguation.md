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

Corpus for disambiguration  
    # https://www.leiphone.com/news/201701/W2G0J9H3TeTziXKp.html
    https://arxiv.org/abs/1603.07012  
    # http://www.sohu.com/a/124709523_465975  
    https://github.com/google-research-datasets/word_sense_disambigation_corpora  
    Wordnet  
        https://wordnet.princeton.edu/
    
train multiple vectors  
    GloVe
        # https://www.zhihu.com/question/30402861  
    https://blog.csdn.net/sinat_26917383/article/details/54847240
    
    

Knowledge-based Word Sense Disambiguation using a Bidirectional LSTM  
    # https://github.com/Jeff09/Word-Sense-Disambiguation-using-Bidirectional-LSTM  
        # Global Vectors for Word Representation (GloVe), introduced by Pennington et al. (2014) is a hybrid
        # approach to embedding words that combine a log-linear model, made popular by Mikolov et al. (2013),
        # with counting based co-occurrence statistics to more efficiently capture global statistics  
    Semi-supervised Word Sense Disambiguation with Neural Models” by Yuan et al. 
        Their LSTM model is trained on sense supervised unlabeled data and generates context vectors based on previous history.  
        *generates context vectors?*  
        To predict senses, they hold out the sense evaluated word and run the entire context through their LSTM.  
    conducted is replacing numbers with a <number> tag. Words not present in the training set are considered unknown during test.
    limit the size of the context to max 140 centered around the target word to facilitate faster training
    
    
    
    
    
    
    
    
    
    
## Idea  
1. Google API to get the negative samples  
2. tweet to get the positive samples  
3.  
    1. cleaning the $ tag and lower all cases
    2. if the text contain the targets  
    3. ticker classification -> context classification  
        use RNN to do the classification?


A. split a sentence in terms of the target ticker term, to generate  
    1. sentence-preceding  
    2. setence-following  
    Use the RNN to output two embeddings:  
    1. embedding-preceding
    2. embedding-following  
    context = (emb_p + emb_f) / 2
    Use MLP to do binary classification.
    
B. directly use W2V to represent the sentence, and use MLP to do binary classification  
    means, the context is moded by the occurances of words only, not considering the order or words











    
    
    
