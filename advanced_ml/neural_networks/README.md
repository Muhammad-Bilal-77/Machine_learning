# Deep Learning with TensorFlow & Keras

Hey there! Welcome to the advanced section. When traditional Machine Learning algorithms plateau, we bring in Deep Learning Neural Networks.

### Why Did I Use TensorFlow?
You'll notice I didn't use `scikit-learn` for this. While Sklearn has a basic `MLPClassifier`, if you want to be taken seriously in deep learning, you use a graph-based tensor framework like TensorFlow/Keras (or PyTorch). It gives us absolute control over the architecture: setting specific batch sizes, choosing advanced optimizers like Adam, and injecting specialized layers like Dropout.

### The Architecture Explained:
- **Task**: We are classifying 8x8 pixel images of handwritten digits (0-9).
- **The Network**: I built a Multi-Layer Perceptron (Dense network). It takes the 64 pixels, passes them into a 128-neuron layer, then a 64-neuron layer, and finally outputs 10 probabilities (one for each digit).
- **The Dropout Layer**: Neural nets have a bad habit of memorizing training data completely. I explicitly added a `Dropout(0.2)` layer. This randomly turns off 20% of the neurons during training, forcing the network to learn generalized patterns rather than memorizing exact pixels!
- **Diagnostics**: The most critical skill in deep learning is reading a learning curve. I plotted the training history (accuracy and loss) over 30 epochs. If training accuracy hits 100% but validation stalls, you're overfitting. My plots let you diagnose the network's health instantly!

Now that your `pip` installation for TensorFlow is fully complete, you can actually run this entire notebook and watch the neural network train live!