# khorshidSoft_Interview_Project

# Goal
To classify Persian reviews that people have given to products on Digikala.com store.

# Steps
1. We need to import essential Modules. We will import ordinary Sentiment analysis project modules,
however because we will analyse Persian text, we will use `hazm` module and a text containing Persian stop-words.

2. In EDA phase, we show that data is imbalance and most of the records are positive sentiment reviews which are labeled as 0.
3. Next step is to preprocess and clean data. We first use `hazm` module to normalize text: for example it will replace
Arabic `ی` to Persian `ی`.
4. Then, we will remove punctuation from the text as they don't carry any usefull information about sentiment. Also, we will remove persian numbers from text.
5. In one of the important steps, we will tokenize reviews and then lemmatize it to save base form of tokens.
6. Removing Stop words which are most common words in Persian language is the next step.
7. Encoding words to integer is to make the text suitable as input to our model.
8. After removing zero-length reviews, we have total of 3199 reviews. because longest review's length is 221, we set max_length to 221.
9. Another important step is to pre-pad all reviews with zero so that all reviews have the same length. 
10. After splitting data, we have 80% percent data for training, 10% percent for validation and 10% percent for test.
11. The most important step is to make our model. In the first level, we hava a Embeddin layer which length of embeddin vector is set to 200,
Second layer is a LSTM layer with 100 nodes. And finally we will have a dense layer with  `sigmoid` as activation function to calculate probability of belonging to each calss.
12. The final model's accuracy is 87.5% which is not perfect but acceptable.

# Examples
Here we demonestrate output for some reviews to test our model's performance:

Example1:
خیلی بده اصلا به درد نمیخوره

0.98242676
  
Example2:
برای پوستای چرب واقعا ایده آل هستش  هم آبرسانی خوبی داره هم زود جذب میشه  بوش هم عالیه

0.00049004

Example3:
بسیار با کیفیت وسرعت شارز سریع برابی نوت   ممنون از دی جی کالا من یکی خریدم یکی هم هدیه دادن

0.00302509

Example4:
اونجوری که انتظار داشتم  موهای زائد رو جدا نمیکنه از پوست  ولی در کل خوبه

0.00201276

Example5:
من اینو استفاده کردم خاصیت آبرسانی و مرطوب کنندگی عالی و بدون چربی و سبک مناسب ساختار پوست آقایان و رایحه عالی  به سلامتی خود اهمیت بدهیم

0.01065985

Example6:
به هیچ عنوان کارایی ندارد  تا وارد دندان شده پاره میشود و آزار دهنده است

0.42215022
