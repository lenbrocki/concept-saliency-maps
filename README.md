# concept-saliency-maps
Contains the jupyter notebooks to reproduce the results of the paper 'Concept Saliency Maps to Visualize Relevant Features in Deep Generative Models'. 

Keras with tensorflow backend is required to run the notebooks.


# celebA
The celebA dataset can be downloaded from http://mmlab.ie.cuhk.edu.hk/projects/CelebA.html (*img_align_celeba.zip*) and the labels and landmark annotations from https://www.kaggle.com/jessicali9530/celeba-dataset (*list_attr_celeba.csv* and *list_landmarks_align_celeba.csv*). 

Make sure that after unpacking all images are in a folder called 'img_align_celeba' and the csv files are in the same directory as the notebook.

To create the saliency maps the implementation https://github.com/1202kbs/Rectified-Gradient is used. The folder 'deepexplain' and the python file 'utils.py' need to be in the same directory as the notebook.
