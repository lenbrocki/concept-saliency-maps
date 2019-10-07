# Concept Saliency Maps
Evaluating, explaining, and visualizing high-level concepts in generative models, such as variational autoencoders (VAEs), is challenging in part due to a lack of known prediction classes that are required to generate saliency maps in supervised learning. While saliency maps may help identify relevant features (e.g., pixels) in the input for classification tasks of deep neural networks, similar frameworks are understudied in unsupervised learning. Therefore, we introduce a new method of obtaining saliency maps for latent representations of known or novel high- level concepts, often called concept vectors in generative models. Concept scores, analogous to class scores in classification tasks, are defined as dot products between concept vectors and encoded input data, which can be readily used to compute the gradients. The resulting concept saliency maps are shown to highlight input features deemed important for high-level concepts. Our method is applied to the VAE’s latent space of CelebA dataset in which known attributes such as “smiles” and “hats” are used to elucidate relevant facial features. Furthermore, our application to spatial transcriptomic (ST) data of a mouse ol- factory bulb demonstrates the potential of latent representations of morphological layers and molecular features in advancing our understanding of complex biological systems. By extending the popular method of saliency maps to generative models, the proposed concept saliency maps help improve interpretability of latent variable models in deep learning.

## Reproduce
Contains the jupyter notebooks to reproduce the results of the paper 'Concept Saliency Maps to Visualize Relevant Features in Deep Generative Models'. 

Keras with tensorflow backend is required to run the notebooks.

To create the saliency maps the implementation https://github.com/1202kbs/Rectified-Gradient is used. The folder 'deepexplain' and the python file 'utils.py' need to be in the same directory as the notebooks.

### CelebFaces Attributes Dataset (CelebA)

CelebA is a large database of face images with known attributes, consisting of 202593 images and 40 binary annotations of facial attributes for each image. The images have been aligned, scaled and cropped to 128×128 pixels using the landmark annotations that come with the dataset.

The celebA dataset can be downloaded from http://mmlab.ie.cuhk.edu.hk/projects/CelebA.html (*img_align_celeba.zip*) and the labels and landmark annotations from https://www.kaggle.com/jessicali9530/celeba-dataset (*list_attr_celeba.csv* and *list_landmarks_align_celeba.csv*). 

Make sure that after unpacking all images are in a folder called 'img_align_celeba' and the csv files are in the same directory as the notebook.

Training of the VAE can take quite long, pretrained weights can be downloaded here https://drive.google.com/file/d/17_3u_KAjpTP8QPfYyP_vMkKn9GjVKYfv/view 

Z. Liu, P. Luo, X. Wang, and X. Tang, “Deep learning face attributes in the wild,” in Proceedings of International Conference on Computer Vision (ICCV), December 2015.

### Spatial Gene Expression of a Mouse Olfactory Bulb
Spatial Transcriptomics (ST) data of a mouse olfactory bulb contains genome-wide gene expressions from a sliced tissue section of a mouse olfactory bulb. When positioned on a microchip, there are 267 spots in a grid that measure expression activities of upto 16573 genes within that locality. Each of 16573 genes is treated as a sample with 267 features, which are the counts of RNAs at the different spots in the tissue.

The Spatial Transcriptomics dataset can be downloaded from https://www.spatialresearch.org/resources-published-datasets/doi-10-1126science-aaf2403/ (*Count matrices, Alignments*). The count matrices (in the notebook only *MOB Replicate 1* is considered) should be placed in a folder called 'data' and alignments in a folder 'alignments'. 

St{\aa}hl, Patrik L and Salm{\'e}n, Fredrik and Vickovic, Sanja and Lundmark, Anna and Navarro, Jos{\'e} Fern{\'a}ndez and Magnusson, Jens and Giacomello, Stefania and Asp, Michaela and Westholm, Jakub O and Huss, Mikael and et al., “Visualization and analysis of gene expression in tissue sections by spatial transcriptomics,” Science, 2016.
