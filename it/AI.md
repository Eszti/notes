# Artificial Intelligence

## Maths

- [group normalization](https://arxiv.org/pdf/1803.08494.pdf)

## ML problems

- classification
	- supervised
- clustering
	- unsupervised

## Neural Networks

- only interpolate (what we already have seen), not extrapolate

### Concepts

- [activation functions](https://mlfromscratch.com/activation-functions-explained/)
- loss function
	- cross-entropy loss
- one-hot encoding
- optimizer
	- gradient descend
	- Adam: momentum & velocity
- CNN
	- padding
	- maxpool
	- [tricks](https://arxiv.org/abs/1812.01187v2)

### Frameworks

- python
	- deferred execution (operation overload)
	- static graph (deferred) vs dynamic graph (eager)
	- slow because everything is an object
		- list: pointer of separate objects

#### Tensorflow

- [tensorflow](https://www.tensorflow.org/)
- robust pipeline to production
- eager by default
- rather industry

#### PyTorch

- [pytorch](https://pytorch.org/)
- eager by default, with TorchScript static graph
- support for ONNX (universal network model: Open Neuronal Network Exchange)
- rather education
- written in C++ and CUDA
- modules
	- torch.util.data
	- torch.distributed
	- torch.optim
	- TorchScript
- framework or ecosystem (fastai...)

##### Tensor

- building blocks: tensor: nativ support for backpropagation
- continuous block of array

##### Data

- Dataset
	- torch.utils.data.Dataset
	- __getitem__(self, key)
	- __len__(self)
- DataLoader
	- torch.utils.data.DataLoader
	- batching
	- augmentation
- data transformers
	- e.g. normalize

##### Examples

```python
# Init
a = torch.ones(3);
b = torch.zeros((3, 2)).short();
c = torch.tensor([1.,2.,3.], dtype=torch.double);
a = torch.rand(3, 64, 64);	# torch.Size([3, 64, 64])
a.size()
a.stride()	# how many elements in the storage one needs to move to get the next value

# Reshape
a = torch.tensor([1,2,3,4,5,6])
b = a.reshape((3,2))
b = a.reshape(-1)		# 1d array
assert id(a.storage()) == id(b.storage())
a.view(3, 3)

# Indexing
a[1:, 0]	# a[row, col]
a[::4] 		# every 4th element
diagonal = a[range(3), range(3)]

# Broadcasting
a = torch.tensor([
    [1, 2],
    [3, 4]
])
b = torch.tensor([
    1, 2
])
torch.allclose(a*b, torch.tensor([
    [1, 4],
    [3, 8]
]))

# Numpy
t_np = t.numpy()
t = torch.from_numpy(t_np)

# Serialize - h5py can aditionally be used
torch.save(t, "path_to_file.t")
torch.load("path_to_file.t")

# GPU
torch.device("cpu") # use cpu by default
torch.device("cuda") # GPU
torch.device("cuda:0") # index multiple GPUs #0 -> default: 0
torch.device("cuda:1") # use GPU #1

# Gradient
x = torch.tensor([2.5], requires_grad=True)

# Linear NN
linear_layer = torch.nn.Linear(in_features=100, out_features=20)
network = nn.Sequential(
            nn.Linear(28*28,256),
            nn.Sigmoid(),
            nn.Linear(256,10),
            nn.LogSoftmax(dim=1)
          )
network =  nn.Sequential(collections.OrderedDict([
            ("hidden1", nn.Linear(28*28,256)),
            ("sigmoid", nn.Sigmoid()),
            ("hidden2", nn.Linear(256, 100)),
            ("relu", nn.ReLU()),
            ("output", nn.Linear(100,10)),
            ("softmax", nn.LogSoftmax(dim=1))
          ]))
print(network)

# Convolutional NN
convolutional_layer = nn.Conv2d(in_channels=3, out_channels=16, kernel_size=3, padding=0, stride=1)

# Dataset
x_train, y_train = torch.load(data.DATA_PATH / "MNIST/processed/training.pt")

# Compare
torch.testing.assert_allclose()

# Train
with torch.no_grad():
	# to not extend the graph
	pass

# Persist
torch.save(model.state_dict(), data.DATA_PATH / "model_params.pt")	# only params
torch.save(model, data.DATA_PATH / "model.pt")											# with layers
model = torch.load(data.DATA_PATH / "model.pt")
model.load_state_dict(torch.load(data.DATA_PATH / "model_params.pt"))
```

## NLP

### Tasks

#### Simple tasks

- tokenization
	- break down text
	-  `word_tokenize(text)`, `sentence_tokenize(text)`
- stopword removal
	- nltk.corpus 
	- `stopwords.words('english')`
- N-Grams
	- `nltk.collocations`
	- `BigramCollocationFinder.from_words(words)`
- Word Sense Disambiguation
	- identify meaning based on context
	- wordnet
		- Synset: one single representation of a word
	- `from nltk.wsd import lesk`
- POS tagging
	- `nltk.pos_tag`
- stemming
	- same words with different ending
	- `nltk.stem`
	- e.g. LancasterStemmer

#### More complex tasks

- auto summarization
	- rule-based:
		- finding the most important word (word frequemcy) -> significance score for the word
		- sentence significance -> significance score for the sentence
		- pick the most important sentences
- spam detection
	- static rules
	- dynamic approach = machine learning
- sentiment analysis
- chatbots
	- Rasa: framework
		- open source
		- development
			- yaml files for description
			- python code for actions

### Data Representation

- Term Frequency
- TF-IDF

### Models

- mathematical equation or a set of rules, depening on the task
- classification
	- Naive Bayes
	- SVM
- clustering
	- K-Means
	- Hierarchical Clustering

### Preprocessing

- urllib2: to download html page
- BeautifulSoup: to parse webpages
- nltk.probability: FreqDist

## Tools

### Jupyter Notebooks

- documentation
	- torch.tensor??

### Version Control

- Machine Learning Version Control System: [DVC](https://dvc.org/)

