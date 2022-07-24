# Coursera Machine Learning Specialization by Andrew Ng

[course link](https://www.coursera.org/specializations/machine-learning-introduction)

This is an updated version of Andrew's previous famous ML course.

My attempt to the previous course [🔗](https://github.com/JeffChien/Coursera-ML-by-Andrew-Ng)

# Trouble shooting

## TensorFlow problem with Apple silicon

GPU support is not good, I've encountered performance issue and missing API. 2 ways to run with CPU.

```python
with tf.device("/cpu:0"):
    model.compile()
    model.fit()
```

or use cpu only [🔗](https://datascience.stackexchange.com/questions/58845/how-to-disable-gpu-with-tensorflow)

### extremely slow with GPU

Increasing the batch size helps, but the problem is that CPU is still much faster in the same condition, really have no idea what's wrong in the `tensorflow-metal` package.

issue threads

- [issue1](https://developer.apple.com/forums/thread/698901)
- [issue2](https://developer.apple.com/forums/thread/685623)

### Got error while using Adam optimizer

due to Apple's GPU is missing some APIs, use cpu instead

issue threads

- [issue1](https://developer.apple.com/forums/thread/687611)
- [issue2](https://developer.apple.com/forums/thread/700660)
