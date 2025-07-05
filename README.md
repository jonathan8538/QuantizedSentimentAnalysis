# QuantizedSentimentAnalysis
QuantizedSentimentAnalysis project aims to turn BERT and DistilBERT model to be more efficient (energy and speed) in analysing text sentiment. 

dataset TweetSentimentAnalysis 
-> rows : text (raw tweet) and sentiment (label : positive, neutral, negative)
-> preprocessing: lowercase, remove punctuation, tokenization, remove stopwords, and balance the dataset (initially all class ranging from 9000 to 12000 data rows but then balanced to 8500 counts each class)

pretrained model : distilbert
flow:
1) data loading
2) data preprocessing
3) initialize quantized module(including the replacement of standard layer like Activation layer, Linear layer with provided layer from Brevitas library (eg. QuantLinear and QuantRELU)
4) Fine tune model
5) Apply quantized module
6) Apply quantization aware training
   
suggested future work:
1) integrate ONNX
2) apply pruning or knowledge distillation from main model
