# Face Recognition Vietnamese Face
> If you need pickle files or have any questions, you can contact me via email: duc.nguyensy1999@gmail.com
## Dataset

**VN-celeb (training)**
* We  use VN-celeb as training data. 
* We apply augmentation methods (brightness, horizontal flip, adjust local brightness) used explicitly for face data to individuals with several face images less than 20. After that, we randomly sampled 20  images  from  each  person  and  split  15  and  5  for  training  and  testing.   Consequently,  the dataset consists of 20380 faces of 1020 people (20 images/person). Moreover, all the faces have already been aligned for better performance.

* ![](https://i.imgur.com/YqtWBIa.png)

Link for dataset: [VN-Celeb](https://viblo.asia/p/vn-celeb-du-lieu-khuon-mat-nguoi-noi-tieng-viet-nam-va-bai-toan-face-recognition-Az45bG9VKxY)

**BKStudent (testing)**
* This dataset consists of 536 images of 268 people (2 face images/person) in HCMUT. The first image will be augmented into five images and considered as images in the database.  The second image will be considered as the checking face.  This dataset is used fortesting our model.

## Implementing

* We generate a batch with 200 groups of triplet Anchor, Positive, and Negative images ran-domly in the training phase in each step.  Then, we choose 32 hardest triplets and randomly32 triplets.  Moreover, we create a Siamese network with the triplet loss model, FaceNet as abase model (feature extractor).  The loss is calculated based on L2 distance.  With the supportof Google Colab, we trained 830 epochs (early stopping) with Adam optimizer (learning rate =0.0001).

## Result
* Testing on 268 identities (BKStudent).

![](https://i.imgur.com/byOEeYU.png)

Link for h5 models of FaceNet and Our model: [FaceNet and Our model](https://drive.google.com/drive/folders/1cIzM-328m_wyROGjihI-xrCQ9tCM0OGx?usp=sharing)

## References

* Schroff, Florian, et al. FaceNet: A UNIFIED Embedding for Face Recognition and Clustering. 17 June 2015

* Quang, P. (2019, May 19). VN-celeb: Dữ liệu Khuôn mặt người nổi tiếng Việt NAM và Bài Toán face recognition.