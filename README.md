# CLIP-implement
 Try to get used with CLIP neural network

 ## CLIP: Connection Text and Images
[blog](https://openai.com/blog/clip/) |
[paper](https://arxiv.org/pdf/2103.00020.pdf) |
[code](https://github.com/openai/CLIP)

- Problem:
  - Typical vision datasets are labor intensive and costly to create while teaching only a narrow set of visual concepts
  - Standard vision models are good at one task and one task only, and require significant effort to adapt to a new task
  - Models that perform well on benchmarks have disappointingly poor performance on stress tests

- Introduction:
  - CLIP (Contrastive Language–Image Pre-training) builds on a large body of work on zero-shot transfer, natural language supervision, and multimodal learning.
  - Zero-shot Learning: Zero-shot learning is a promising learning method, in which the classes covered by training instances and the classes we aim to classify are disjoint. In other words, Zero-shot learning is about leveraging supervised learning with no additional training data.

- Approach
  - Training task for CLIP: given an image, predict which out of a set of 32,768 randomly sampled text snippets, was actually paired with it in our dataset.
  - Mitigate some major problems in the standard deep learning approach to compputer vision:
    - Costly datasets. CLIP learns from text-image pairs that are already publicly avaliable on the internet. Reducing the need for expensive large labeled datasets has been extensively studied by prior works. 
    - Narrow: CLIP can be adapted to perform a wide variety of visual classification tasks without needing additional training examples. To apply CLIP to a new task, all we need to do is “tell” CLIP’s text-encoder the names of the task’s visual concepts, and it will output a linear classifier of CLIP’s visual representations. The accuracy of this classifier is often competitive with fully supervised models.
    - Poor real-world performance:  There is a gap between “benchmark performance” and “real performance.” We conjecture that this gap occurs because the models “cheat” by only optimizing for performance on the benchmark, much like a student who passed an exam by studying only the questions on past years’ exams. In contrast, the CLIP model can be evaluated on benchmarks without having to train on their data, so it can’t “cheat” in this manner. This results in its benchmark performance being much more representative of its performance in the wild. 
  
  - Limitations
    - CLIP strugggles on these tasks such as counting the number of objects in an image and on more complex tasks such as predicting how close the nearest car is in a photo.
    - CLIP also still has poor generalization to images not covered in its pre-training dataset. 