# READ ME

Example MNIST training using the following tech stack:

* Ray
* PyTorch Lightning
* PyTorch
* Python 3.10.12

## Files

* [mnist.py](./mnist.py). Main training. Example from Ray's [documentation](https://docs.ray.io/en/latest/tune/examples/includes/mnist_ptl_mini.html).
* [requirements.txt](./requirements.txt). Install via: `pip install -r requirements.txt`
* [freeze.txt](./freeze.txt). Resulting run-time environment.

## Fixes

The training code in the documentation has an error. Edit

```python
self.accuracy = Accuracy()
```

to

```python
self.accuracy = Accuracy(task="multiclass", num_classes=10)
```

## Run

```sh
python mnist.py
```

The experiments will be recorded in `~/ray_results/tune_mnist`.
