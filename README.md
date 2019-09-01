# Image_Captioning Using LSTM

## Dataset - Flickr_8K
<ul>
  <li>In Flickr_8K dataset, all the images of training, validation and test set are in one folder.</li>
  <li>It contains 3 different files i.e <em>Flickr_8k.trainImages.txt</em>,<em>Flickr_8k.testImages.txt</em>,     <em>Flickr_8k.devImages.txt</em> corresponding to each type of dataset i.e train, test and validation set, each file having file_name of images conatined in each dataset.</li>
  <li>Each image is given 5 different captions by 5 different humans. This is because an image can be described in multiple ways.These captions are stored in <em>'Flickr8k.token.txt'</em>.</li>
</ul>

## Link to Dataset 
https://github.com/jbrownlee/Datasets/releases/download/Flickr8k/Flickr8k_Dataset.zip
https://github.com/jbrownlee/Datasets/releases/download/Flickr8k/Flickr8k_text.zip

## Model
<b>ResNet50</b> was used as an image encoder to encode the images which were then input in the model.<br>
<b>Keras embedding layer</b> was used to generate word embeddings on the captions which were encoded earlier.<br>
The embeddings were then passed into <b>LSTM</b> after which the image and text features were combined and sent to a decoder network
to generate the next word.<br>

## Results
<b>Greedy Search</b> and <b>Beam Search</b> both were used to generate the captions.<br>
<b>Bleu Score</b> was used to evaluate the captions generated.
### Captions generated by Greedy Search are as follows:
<img width="569" alt="Screen Shot 2019-09-01 at 11 07 09 PM" src="https://user-images.githubusercontent.com/31596604/64080074-71dba600-cd0d-11e9-878f-1a51b67d0fbd.png">
<img width="815" alt="Screen Shot 2019-09-01 at 11 07 53 PM" src="https://user-images.githubusercontent.com/31596604/64080075-8029c200-cd0d-11e9-9335-d28579e2ee4f.png">
<img width="725" alt="Screen Shot 2019-09-01 at 11 08 18 PM" src="https://user-images.githubusercontent.com/31596604/64080077-828c1c00-cd0d-11e9-8d6e-c6057f36830e.png">

<hr>

### Captions generated by Beam Search with k=3 are as follows:
<img width="536" alt="Screen Shot 2019-09-01 at 11 13 23 PM" src="https://user-images.githubusercontent.com/31596604/64080118-3d1c1e80-cd0e-11e9-9773-76932450d823.png">
<img width="714" alt="Screen Shot 2019-09-01 at 11 13 48 PM" src="https://user-images.githubusercontent.com/31596604/64080119-3f7e7880-cd0e-11e9-8848-782b592a22e7.png">
<img width="412" alt="Screen Shot 2019-09-01 at 11 14 01 PM" src="https://user-images.githubusercontent.com/31596604/64080120-41e0d280-cd0e-11e9-83c4-204579e3fef2.png">
<img width="809" alt="Screen Shot 2019-09-01 at 11 14 10 PM" src="https://user-images.githubusercontent.com/31596604/64080123-43aa9600-cd0e-11e9-8b5f-f3bb414d8b58.png">

### Average Bleu Score on Test Set
<b>Greedy Search:</b> 0.4623 <br>
<b>Beam Search with k=3:</b> 0.4836
