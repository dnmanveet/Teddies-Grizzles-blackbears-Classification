# Teddies-Grizzles-blackbears-Classification
Built using fast.ai library.
![Screenshot from 2019-05-23 22-31-31](https://user-images.githubusercontent.com/29728855/58272702-b4a3ee80-7dac-11e9-98b8-32c9e24d88c7.png)\
This is model is traied with a dataset which built by my own from google images.
Uploading inthe google drive and then extracting data from that google drive.
# Process to creating our own Dataset from Google Images:
Open google images and enter teddy bears in the url same process is to be followed for all the three kinds, that we are going to classify now.
1. [**Teddy bears**](https://www.google.com/search?tbm=isch&source=hp&biw=1366&bih=620&ei=CtfmXN-ZJMrbrQGZh73gDQ&q=teddy+bear&oq=tedd&gs_l=img.1.0.35i39j0l9.1311.2132..3749...0.0..0.356.603.3j3-1......1....1..gws-wiz-img.....0.Yets_E4QgmY)
2. [**Grizzles**](https://www.google.com/search?tbm=isch&q=grizzlies+images&chips=q:grizzly+images,g_1:wildlife&usg=AI4_-kTUV54TnXbN1bcMKGPHNbRBu5JDEA&sa=X&ved=0ahUKEwjt3K-mlrLiAhWz8XMBHb0ODDgQ4lYIMygH&biw=1366&bih=620&dpr=1)
3. [**Black Bear**](https://www.google.com/search?biw=1366&bih=620&tbm=isch&sa=1&ei=GdjmXOGUH5_Cz7sPxeqQ0Ac&q=black+bear&oq=black+bear&gs_l=img.3..35i39l2j0l8.26322.31573..31907...0.0..0.105.946.8j2......2....1..gws-wiz-img.....0..0i67j0i10.C36eah85mcs)

When you open each url for particular set of images above. You need to press `ctrl+shft+J` then it will pop up a small window. 
Then paste this follwing jason command in that. 

`urls = Array.from(document.querySelectorAll('.rg_di .rg_meta')).map(el=>JSON.parse(el.textContent).ou);
window.open('data:text/csv;charset=utf-8,' + escape(urls.join('\n'))); `

and press `Enter`.
It will download a file called `download` containing urls of all the images in that particular page. We need to add an extension of `.txt` to that.
After that, create a seperate folder in Google drive for each file and uplaod each file seprately in each folder as shown in the ipnd notbook.
My `.txt` files:

 1.[**Teddies**](https://github.com/dnmanveet/Teddies-Grizzles-blackbears-Classification/blob/master/teddies.txt)\
 2.[**Grizzles**](https://github.com/dnmanveet/Teddies-Grizzles-blackbears-Classification/blob/master/grizzles.txt)\
 3.[**Black Bears**](https://github.com/dnmanveet/Teddies-Grizzles-blackbears-Classification/blob/master/blackbears.txt)

Now using a the path of the folder and the .txt file path as:

**Example:**\
    `folder = 'black'`\
    `file = 'blackbears.txt'`

**Downloading:**\
    `download_images(path/folder/file, path/folder, max_pics=400);`\
We need to follow the same process according for all the 3 kinds of bears.\
**Now our own dataset is ready for training** \
We will start training the model on our dataset.
