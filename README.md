# Photo to Monet: CycleGAN Transformation

## Project Overview
This project uses CycleGAN to transform real-world photos into Monet-style artwork. CycleGAN, or Cycle-Consistent Generative Adversarial Network, is a model specifically designed for unpaired image-to-image translation, making it suitable for converting a large dataset of photos into paintings in the style of Claude Monet without needing paired data.

This project was an opportunity to delve into advanced generative models, exploring techniques in neural style transfer and learning domain transformations.

## Approach

### Data Preprocessing
1. **Data Collection**: The model was trained on unpaired datasets consisting of photos and Monet paintings.
2. **Data Augmentation**: Techniques such as flipping, cropping, and resizing were applied to improve model generalization and prevent overfitting.
3. **Normalization**: Images were scaled to the range [-1, 1] for optimal model performance.

### Model Architecture
The CycleGAN model consists of:
- **Two Generators**: One to map Photos to Monet (G), and the other to map Monet to Photos (F).
- **Two Discriminators**: Used to differentiate between real and generated images in both domains.
- **Cycle Consistency Loss**: Ensures that translating an image to the target domain and back results in the original image, maintaining content consistency.

### Training Process
- **Adversarial Loss**: Each generator aims to fool its corresponding discriminator, helping the model learn realistic transformations.
- **Cycle Consistency Loss**: Promotes content preservation by ensuring that a photo, after translation to Monet and back to photo, remains unchanged.
- **Identity Loss**: Enforces style adaptation by penalizing deviations from target style when applied to Monet images in the Monet generator.

The model was trained for several epochs with alternating generator and discriminator updates to reach optimal style transformation.

## Challenges & Solutions
- **Color Artifacts**: Addressed by fine-tuning the cycle consistency loss weight and applying identity loss.
- **Content Preservation**: Balancing between style transfer and maintaining photo details by tuning hyperparameters.

## Results
The model successfully generates Monet-style artwork from real-world photos. Below are some visualizations of the transformation:

- **Generated Monet-Style Images**
- **Cycle Consistency Check**

## Future Improvements
- **Enhanced Model Complexity**: Experimenting with additional GAN architectures such as StyleGAN.
- **Hyperparameter Tuning**: Refining the balance between cycle consistency and adversarial loss.
- **Data Augmentation**: Using more diverse transformations to improve model robustness.

## Conclusion
This project provided a hands-on experience in generative modeling and neural style transfer. CycleGAN proved to be a powerful tool for unpaired image-to-image translation, successfully learning the transformation between photo realism and Monet’s impressionistic style.

## Acknowledgments
- **CycleGAN Paper**: [Unpaired Image-to-Image Translation using Cycle-Consistent Adversarial Networks](https://arxiv.org/abs/1703.10593)
- **Dataset**: Photos and Monet paintings dataset from Kaggle.

