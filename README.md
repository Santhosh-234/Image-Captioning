# Image-Captioning
CNN based image captioning model that employs EfficientNetB0
In this tutorial, the chosen dataset is Flickr8K. This collection includes more than 8,000 pictures, each accompanied by five distinct descriptions.

For the purpose of text data vectorization, we will employ the TextVectorization layer. Its role is to convert the original text strings into numerical sequences, where each number signifies the position of a word within a predefined vocabulary. Our approach involves a personalized string normalization method, which involves removing punctuation marks excluding "<" and ">". Additionally, the default division scheme (splitting by spaces) will be utilized.

Our strategy involves generating pairs of images and their respective captions through the utilization of a tf.data.Dataset object. The process unfolds in two primary stages:

1. Extraction of the image from storage
2. Tokenization of all five captions associated with the given image

The architecture for our caption generation model is comprised of three core components:

1. CNN: This element facilitates the extraction of image features.
2. TransformerEncoder: The derived image features undergo processing by a Transformer-based encoder, yielding a fresh representation of the inputs.
3. TransformerDecoder: Using the encoder's output and textual data (sequences) as input, this model endeavors to learn the process of caption generation.

Observations indicate that the model commences generating coherent captions after a limited number of training epochs. To ensure ease of replication, our training procedure incorporates specific restrictions, such as minimizing the number of attention heads. For improved predictive outcomes, there is room to experiment with adjustments to these training parameters, ultimately leading to the discovery of an optimal model for your specific application.
