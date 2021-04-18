Michael Tobin
Prof. Malouf
LING 583
Lab 8 writeup

**1-vader.ipynb**
I didn't need to do anything with this one except re-index the DF, though it may not have been necessary with this file.

**2-classify.ipynb**
I initially had an issue with the tokenizer where each row would either have NaN for its values, or have tokens that correspond with another row index. After figuring out that the issue was caused by each row retaining its index from the original DF, I re-indexed the test and train DF's and that seems to have resolved the issue. From there, the baseline SGD classifier gave a macro F1 average score of 0.83. Running a hyperparameter search with 50 iterations narrowed the parameters to min_df=12, max_df=0.84, and alpha=5.4e-5. This brought the macro F1 average score up to 0.87, still not great, but a 22% increase.  

**3-parse.ipynb**
This file was run with no modifications.

**4-syntax.ipynb**
IF YOU ARE GOING TO RUN THE FILES, DO NOT USE RUN ALL CELLS; THERE ARE A TON OF MANUAL CLASSIFIER RUNS AT THE END THAT WILL TAKE FOREVER.
I did not re-index the test and train DF's for this file since the various forms of add negativity function all operated by altering the original DF through the test and train DF's being references to it. After running the supplied code, I attempted to do a hyperparameter search, but could not get it to work. I kept receiving cryptic error messages that yielded zero results when searching on the internet. After a while of trying and failing to get that working, I removed that code and set to manually changing parameters and running them. I had one run that had a score of 0.9427, but for some reason, subsequent runs with the same parameters yielded much lower results. In the end I accepted an SGD classifier with values: max_df=0.8, min_df=10, alpha=4e-5 as my best run with a score of 0.9131. This gave a macro F! score of 0.8847, which was a 13.5% improvement over the 'm1' classifier. 