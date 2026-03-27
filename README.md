# LW3-Building-a-Custom-Image-Classifier-with-TensorFlow-Using-Personal-Image-Datasets

### Google Collab Link: https://drive.google.com/drive/folders/1oxDiImPtWEDOuG0kFKZbgJcgHZXC_UJf?usp=drive_link

### Google Drive ImageDataset link: https://drive.google.com/drive/folders/1gqCKPtXaF8xAqBMOz82Q6RH7mIx3r_pA?usp=drive_link

### Guide Questions (Student Explanation & Reflection)


####Visualization & Overfitting

#####1. What signs indicated overfitting in your first model?
  #####Answer: The training accuracy (~72%) was consistently higher than the evaluated validation accuracy (68.26%), and validation loss became unstable in later epochs — signs that the model was memorizing training data instead of generalizing.

#####2. How did data augmentation affect validation accuracy?
  #####Answer: Data augmentation helped to stabilize the validation accuracy and reduce the gap between training and validation performance. While the peak validation accuracy remained similar (around 71-72%), the model became more robust and less prone to overfitting.


####Model Improvement

#####3. What is the purpose of dropout layers?
  #####Answer:  Dropout randomly disables 30% of neurons during training, preventing the model from over-relying on specific neurons. This reduces overfitting and improves generalization on unseen data.

#####4. Why does data augmentation improve generalization?
  #####Answer: It improves generalization by creating a larger and more diverse set of training data from the existing images. By applying random transformations (like flips, rotations, and zooms), the model is exposed to more variations of the same object, making it less sensitive to the exact position, orientation, or appearance of features in the image.


####Performance Comparison

#####5. Compare accuracy before and after improvements.
  #####Answer: The initial model achieved a validation accuracy of 68.2%.
               The improved model (with augmentation and dropout) achieved a validation accuracy of 71.6%.
               There was an improvement of about 3.4%.

#####6. Which technique contributed most to improvement?
  #####Answer: Data augmentation contributed the most — it directly raised validation accuracy from 68.26% to 72.17% and produced a 96.73% confidence prediction on the test image. Dropout helped stabilize training but had less impact on raw accuracy.


  ####Deployment & Application

  #####7. Why is saving the model important?
    #####Answer: Saving the model allows you to reuse the trained model without having to retrain it. Training is computationally expensive and time-consuming; saving the model (e.g., as an .h5 or .keras file) means you can load it later for making predictions on new images or for deployment in other applications.

  #####8. How can this model be deployed in a real-world system?
    #####Answer: The saved .keras model can be converted to TensorFlow Lite for a mobile app, or wrapped in a Flask/FastAPI web API where users upload a plant photo and receive a predicted class with confidence score — useful for identifying Philippine medicinal herbs like GotuKola, Serpentina, or Kratom in the field.
