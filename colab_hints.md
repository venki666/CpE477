
1.	Each Colab instance will stay alive as long as you interact with it once every 90 minutes.
2.	Each instance will only last for a maximum of 12 hours so make sure to download all of the files you need ASAP to avoid losing them. We will discuss particular files of note as we start to use longer Colabs later in the specialization.
3.	You can access the files in the Colab VM on the left side of the screen by clicking the folder icon: 
<img width="282" alt="image" src="https://user-images.githubusercontent.com/5742488/220037769-83b187ea-596b-4e32-959c-d37e221513aa.png">

4.	By default all of your files are saved under /content and by default you start only seeing that folder. 
5.	Remember, while the code cells in Colab default to python, any bash command can be executed by prepending the command with !. For example you can unzip a file with !unzip file.zip -d destination_folder
6.	To download a file from Colab simply click the three dots next to the file’s name and then select download
7.	To upload a file to Colab simply click the icon with the piece of paper with a folded corner and an arrow on it below the word Files
8.	To make permanent changes to a Colab you need to select file->Save a copy in Drive which will make a copy of the Colab in your drive with your changes saved.
9.	You can drastically speed up Neural Network training by activating a GPU instance. This can be done through runtime->Change runtime type and then selecting GPU under Hardware accelerator: 

<img width="263" alt="image" src="https://user-images.githubusercontent.com/5742488/220038131-b737f95c-ae14-4aae-841e-59ab456a44d2.png">
