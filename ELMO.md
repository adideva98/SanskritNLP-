# Setting up Azure 

The ELMO model was trained on a virtual machine on Microsoft Azure. The first part of the document talks about the setting up procedure for Azure. Here , we assume a Student Developer Pack is used, while other Pay-as-you-go subscriptions can also be opted for. 

To start off Google search  Azure for Students. The sign up procedure is simple. It would help if you already have a Student Developer Pack activated on your GitHub account , although this is not necessary. If you have a SDP on GitHub use the same email id while registering on Azure. If not complete the registration procedure with whichever option provided there. If you do use your institution mail id it may take a few days for Azure to verify. Having set that up , you should be redirected to the following screen. 

![image-20210106180123206](C:\Users\Om Adideva\AppData\Roaming\Typora\typora-user-images\image-20210106180123206.png)

Then using the hamburger menu on the left top corner navigate to Home which should bring you to the next screen which looks like the following .

![image-20210106180345729](C:\Users\Om Adideva\AppData\Roaming\Typora\typora-user-images\image-20210106180345729.png)
At the navigate tab select Resource Groups , and then find the Add button towards the left corner to create a new resource group. There name your resource group what you like and select the region East US. The subscription plan is already selected for you in its respective box. Click on review and create and then if all validations are passed you can click on create and your resource group will be set up. 
Next go back to Home and click on Machine Learning. Here you will find a similar screen to that of Resource Group. Again click on add and the following screen should be presented to you 

![image-20210106180931078](C:\Users\Om Adideva\AppData\Roaming\Typora\typora-user-images\image-20210106180931078.png)
Choose the resource group as the one you created and then name the Machine Larning project. Choose the region again as East US and rest of the fields will be filled in automatically. Then click on Review+Create and then create after validations are passed. 
After this a loading screen will appear saying that your resource is being deployed. After it is deployed the system will notify you and on the notification box click on Take me to Resource. That should land you on a screen like this. 

![image-20210106181332109](C:\Users\Om Adideva\AppData\Roaming\Typora\typora-user-images\image-20210106181332109.png)
Click on the Launch Studio button below and that will take you to the main page. This page should look like the following. 

![image-20210106181524366](C:\Users\Om Adideva\AppData\Roaming\Typora\typora-user-images\image-20210106181524366.png)

Click on Create New dropdown list and click on Compute Instance. 

![image-20210106181630505](C:\Users\Om Adideva\AppData\Roaming\Typora\typora-user-images\image-20210106181630505.png)

Choose whichever machine you want to choose. Although in the Student pack only one GPU machine is allowed. After this click on next and then set the name for the machine and click on Create. It should take a few minutes to create the machine . After it is done you should see a Green Play button alongside the phrase Running appear along with your GPU name on the ML Studio Home. This means your VM is connected and running. Now you can start working on a notebook. 



Click on Start Now on the Notebooks section and this will take you to the notebooks screen. Click on create new , name the file and choose the file type. Once your notebook is running , you will see that your notebook has connected to the Compute you had created and it is running. It generally connects to the Python3.6-Azure ML kernel and this can be viewed on the Kernel Screen. 

![image-20210106182506434](C:\Users\Om Adideva\AppData\Roaming\Typora\typora-user-images\image-20210106182506434.png)

With this your notebook is up and running, and you are ready to start your training for ELMO. Before that get your data ready for training. It is advisable to keep your training and validation sentences in separate CSV and then upload these CSV files onto your Azure Notebook Workspace.  

Make sure you go through the BIL

[BILM-TF] (https://github.com/allenai/bilm-tf)

M-TF repository to know how data should be arranged. Here is another useful 

[link] (https://appliedmachinelearning.blog/2019/11/30/training-elmo-from-scratch-on-custom-data-set-for-generating-embeddings-tensorflow/)	

 that guides on how to use the ELMO model. Follow the same steps verbatim to create a directory with training and validation holdout files, and the vocabulary file in the txt format. Follow the preprocessing steps provided in either links. The training directory creation on Azure should take between 5000-6000 (also depends on the VM and the tier of subscription)

With this your data is ready and now you can follow the steps in the BILM-TF. Remember to clone the repository before running any instructions. 

![image-20210106183404437](C:\Users\Om Adideva\AppData\Roaming\Typora\typora-user-images\image-20210106183404437.png)

At this step remember to install TensorFlow 1.2 also , along with these. Also change directories as you work with these commands. Then run the next steps. Before running the training cell , ensure to specify the correct paths to your files. Depending on the machines you use and the size of your dataset it should take a while to train. As a standard,  ELMO can train on 1 Billion words in 24 hours when using two NVIDIA P100 GPUs. A Collab notebook has been linked here to understand better how to implement the model. 

![image-20210106183951092](C:\Users\Om Adideva\AppData\Roaming\Typora\typora-user-images\image-20210106183951092.png)
The TensorFlow magic words can be used only on Colab, however the device listing command can be used on any Jupyter Notebook. The Colab Notebook can be found 

[here] (https://colab.research.google.com/drive/1SNEqzdw21pYMI3XaOJIEtYqYHmK6bvHY#scrollTo=rkJukjoWOuas)
