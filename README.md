# poemgenerator
Machine Learning Project which involves creating dataset, training a model and evaluating its performance


Motivation/Goal of this project:
The main goal of this project was to uplift people who are suffering from depression using the help of poems.
These poems are generated using RNN (LSTM).

How do poems help depressed people?
When reading a poem, people are generally forced to sit for a while and use many of their abilities to
understand the underlying meaning of a poem. If they get into the flow of reading a poem and slowly start to 
grasp the meaning of it, their senses will start to come out of the depressive stages of the mind, since they have to
allocate their mind to a new task. This will help them to get influenced by the uplifting emotions conveyed by the poems. 


How did I create the data?
Online I couldn't find any datasets that contain poems with a sense of uplifting, or hope giving.
Due to this reason I created my own dataset of uplifting peoms with 4 lines each using GPT-4.
All these poems were then generated into a .txt file ("poems.txt"), to which I did some cleaning, such as removing
unnecessary lines inbetween poems etc. The dataset that I finally used was ("modified_poems.txt") which is uploaded in this Git Repository.
My dataset contains approx. 930 peoms that I created myself using GPT-4.
In this link below, you will find the different prompts I gave GPT-4 to generate the poems.
https://chat.openai.com/share/e3fa85e3-7f92-4d52-893b-bb81b04bcaf0

Modeling:
I trained a model from scratch. 
These were the preprocess of building the model:
1. Loading the data and convert all characters to lowercase
2. Tokenization
3. Create Sequences
4. Prepare Input and Output pairs
5. Define Total Unique Words
6. Encode the output
After 1-6 I have preprocessed the input "x" and the output "y" data.

The modeling part and the architecture I have used can be seen from the code.
Here I want to mention the different variations in architecture that I have used and their respective outputs, because of which i decided to use
the model "poem3.h5". 
To test each model, we can choose different seed_text as input for example "Uplifting Souls", "Dark", "Together" etc.
for the model to generate more and more words, we can change the n_words parameter accordingly.

Modelword.h5 epochs=50 batch_size= 100 units = 400
- lullaby resides through every dance hope ignites a lullaby serene a radiant gentle lullaby at eventide the moon's soft light paints a solemn sight can keep the gloom on the
- skies the lesson in bethlehem's loom it finds the day with your love will you'll can share a testament to
- our eternal force through every dance hope ignites a lullaby each a beacon in the sky in its silver glow may


Modelword2.h5 epochs=75 batch_size= 50 units = 400 The selected model.
- strength and resilience that forever light from bloodshed's darkest storm release the length change are by mile life soul refreshening renewed as hearts that love find     strength and strive with

- even in darkness are majestic monarch of sight beyond to unfold from the himalayan quests to find rays this flame within you can cope above may flicker in the depths

- every storm find souls renewed soul refreshened our essence unshaken renewed soul refreshened through despair and strength pursued our love remains

_Modelword3.h5 epochs=75 batch_size= 50 units=500
deep echoes tales of joy and how bearing the day beneath the echoes of conflict and their gentle embrace forever by each ancient hopeful light each drop nourishes together we are a testament

_yet flows calm where time amidst the unbroken veil echoes brave and bright each thread tells a tale of peace of hope

_forever in each other's wildest love hums from up my anchor like spring you may well wide like in a hopeful dance__

_the soul like stories of silent will it does fall by love's healing but in hues mile and vibrant__


modelwordgigantic.h5 epochs=82 batch_size = 50 units = 700
- deep echoes tales of joy and how bearing the day beneath the echoes of conflict and their gentle embrace forever by each ancient hopeful light each drop nourishes          together we are a testament
- from america's waves skies from every waves to every turn so vast whispers holds secrets of unity can find our tide from
- mile amidst it whispers amidst the waves hills whispers soothing from yet waves it takes flight so yet from every bustling streets

modelword4.h5 epochs=74 batch_size = 60 units = 600
- is but amidst the waves inspire your soul with divine finds despair remember an space and bright never to mend even amidst the waves where faith is ever light is but yet   is
- who need at her call in each fear that is not alone the city that life may be an unseen dawn life
- by love's light amidst the waves where life may brew our love is deep as time we are my strength is unfurled

--------------From this point onwards I trained my model with a larger dataset----------------------------------------
poem.h5, epochs=12, bsize=50, Units=500
learning rate=0.01

output:
and light and peace and
peace and peace and peace
and peace and peace and
peace and peace and peace
and peace

poem.h5, epochs complete=35, bsize=50, Units = 300 learning rate=0.01

output with seed text "India":
free whispers on hope's presence
is a melody sung by
a beacon of light in
the darkest night steady calm
and serene a promise of

poem2.h5, epochs completed=35, bsize=50, Units = 400 learning rate=0.001
output with seed_text "India"
Epoch 70/75
456/456 [==============================] - 4s 9ms/step - loss: 0.2661 - val_loss: 9.1319
Epoch 71/75
456/456 [==============================] - 4s 9ms/step - loss: 0.2507 - val_loss: 9.1534
Epoch 72/75
456/456 [==============================] - 4s 9ms/step - loss: 0.2405 - val_loss: 9.1511
Epoch 73/75
456/456 [==============================] - 4s 9ms/step - loss: 0.2296 - val_loss: 9.2486
Epoch 74/75
456/456 [==============================] - 4s 9ms/step - loss: 0.2239 - val_loss: 9.3994
Epoch 75/75
456/456 [==============================] - 4s 9ms/step - loss: 0.2078 - val_loss: 9.4394

we can see that the loss is getting better

poem3.h5, epochs completed=92, bsize=40, Units = 440 learning rate=0.001
Epoch 92/120
570/570 [==============================] - 5s 9ms/step - loss: 0.0978 - val_loss: 11.7174
output with seed_text "Uplifting Souls"

as radiant power day in
the realm of sunshine dreams
find their way a symphony
of possibilities where dreams can
near it fuels determination igniting

These poems were evaluated by my friends who all have in depth knowledge in English.poem, do give a sense of motivation but to bring the poetic beauty to it, improvements are necessary.
Their validation was that the model generated a bunch of sentences in a poetic way, but the grammar 
and punctuation were poor. The words in the poem, do give a sense of motivation but to bring the poetic beauty to it, improvements are necessary.


How to train the model?
NOTE: i trained my model first with a dataset containing 459 poems, then i trained another model with a larger dataset.
That is why I have two notebooks.
use the JMJpoemgeneratorMelvin.ipynb 
the model is peom3.h5
the dataset is modified_poems.txt
-Upload the dataset
-Run each code block
For training I used the GPU T4 and higher RAM (Google colab)

How to use the model?
You should have the same Tokenizer, that was used to train the model to work the code.
Then run the code.
The parameters that you can alter for generating poems are seed_text and n_words.
seed_text is a word or a sequence of words you can enter in the code as a String.
n-words is the total number of words to be generated.

