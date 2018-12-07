# Neural-Machine-Translation
Version update:
1. Attention seems working. I ran it using the lab data an batch size = 1. The
   training adopts teacher forcing and the result shows the training error is
   decreasing.
2. Batch code finished. 
3. Can use nltk BLEU score
4. No beam search during the training process.(Confirmed by TA)
5. Evaluation finished
6. greedy search completed
7. beam search completed(tested, it works)
8. batch-train, train-iteratoin finished
Problem:
For encoderRNN, since it is bidirectional, hence the output hidden is
(2xn_layers) x B x H, but we only need (n_layers) x B x H for decoder_hidden.
According to Lab, decoder_hidden = encoder_hidden[:decoder.n_layers], which I am
concerned about(seems it took only one direction)

I made possible correction, by summing up two directions up before output from
encoder, hence decoder_hidden = encoder_hidden. However, Cho stated in lecture
note that we need to conctenate two directions together to get context dependent
vector(?)


