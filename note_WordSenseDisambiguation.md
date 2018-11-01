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
    
    
Neural+machine+translation+with+attention+-+v4  
    # X: a processed version of the human readable dates in the training set, where each character is replaced by an index mapped to the character via human_vocab. Each date is further padded to  Tx  values with a special character (< pad >). X.shape = (m, Tx)
    

RNN with variable length  
    # http://www.cnblogs.com/data2value/p/9336572.html  
    # http://friskit.me/2018/04/23/rnn-padding-and-masking-in-keras/
    
    
    

    
    
    
    
    
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





data processing pipeline  
    1. split the sentence at the target term, if multiple target terms, 1 : m,  
        - (forward, backward, label)
    2. use a) regular expression tokenizer b) lemmatization c) padding with specifical token <//p> at the head
        - text_clean_pipeline.py  
    3. make w2v model, to make use of GloVe embeddings to transfer the terms to embeddings, deal </p> with Zero-emb  
        - w2v_translater.py  
        
model  
    1. embedding layer  
    2. forward LSTM layer + dropout  
    3. backward LSTM layer + dropout  
    4. a merging hidden layer - output the encoding of context
    5. logistic regression layer - output 0/1 to say the context is about the ticker or not  
    
model applier  
    1. check if a sentence contain the target term or not  
    2. if contains, use data processing pipeline to process the sentence to (f, b, l)  
    3. load model to predict the sample  
    





# 30/10/2018
bitbucekt  
    access key != general ssh key  
    # https://stackoverflow.com/questions/46893328/bitbucket-access-keys-can-only-be-used-for-read-only  
    

version  
    >>> keras.__version__  
    '2.2.0'  
    >>> import tensorflow as tf  
    >>> tf.__version__  
    '1.8.0'  
    >>>  
    
    

W2V
  [50, 0, 1, 1]
LSTM  
  [(20, 50), (20, 50), 0, 0, 1]

    
logging twice bug
    the get_logger is invoked 1. class definition process 2. class instantiating process
    



1. download glove
2. generate glove emb matrix




Keras 2.2 + tensorflow  
    # https://github.com/keras-team/keras/issues/4471  
    
    
1. ticker not existing in the glove  
    - not a problem, as it only have affection when it is works as the context
    
2. standarize the "term" of pipeline, use a map to map terms into tickerIdx
    - done
    
3. define metrics


np.where, multi-conditions  
    https://stackoverflow.com/questions/16343752/numpy-where-function-multiple-conditions
    
model.predict
    output shape == (1, ...)
