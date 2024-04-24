# Image Similarity Algorithm for Geometrical Shapes

In this work we are presenting a simple algorithm for the image similarity task. In particular we consider geometric shape images, and the goal is to give return the top 20 most similar images 
in the dataset to the input image. We also present a simple API built with FastAPI. The dataset is very large so it is not possible to find it in the repository. It can be found at the following
link: https://data.mendeley.com/datasets/wzr2yv7r53/1 .

## The Dataset
The Dataset is composed by more or less 90 000 images of different geometric shapes. The dataset does not have labels. The only info we have is the geometric shape represented in each image.

## The Model and its usage
As already said, the dataset doesn not provide any labels. So we do not have a ground truth indicating the most similar images for a given input image. Thus the task turns into an unsupervised task.\\
The main idea of the solution proposed is to avoid training a new deep learning algorith and used a pretrained model instead. This model would be used to extract representative features given the input image. Then given a processed representation of the images we can compare them and find the most similar ones. In particular we considered two models:**VGG** and **ResNet18**. This two model were chosen because they have been trained on Imagenet.\\
In order to compare the extraced features and find the most similar images we use the **cosine similarity** metric:

Cosine Similarity = (A • B) / (||A|| * ||B||)
