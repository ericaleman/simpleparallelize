# SimpleParallelize

SimpleParallelize is a lightweight Python package that helps you easily parallelize for loops with a progress bar. It makes parallel processing simple and user-friendly.

```bash
Processing requests:  27%|███████▊                     | 270871/1000000 [00:02<00:06, 109052.10it/s]
```

## Table of Contents

- [Installation](#installation)
- [Usage](#usage)
- [Example](#example)
- [License](#license)

## Installation

To install SimpleParallelize, you can use pip:

```bash
pip install simpleparallelize
```

Or, if you're using Poetry:
```bash
poetry add simpleparallelize
```


## Usage

Here's a simple example of how to use SimpleParallelize in your Python project:

```python
from simpleparallelize.simple import parallelize

def my_func(input):
    # Add your code here
    pass

def main():
	inputs = [...] # List of inputs
	responses = parallelize(inputs, my_func)

if __name__ == '__main__':
    main()
```

Make sure to wrap your code in a main block to avoid forking issues:
```python
if __name__ == '__main__':
    main()
```

## Example

A more concrete example with a request handling function that makes HTTP requests:

```python
import requests
from simpleparallelize.simple import parallelize

def fetch_url(url):
    response = requests.get(url)
    return response.content

def main():
	urls = [
	    'https://httpbin.org/get',
	    'https://httpbin.org/anything'
	]

	responses = parallelize(urls, fetch_url)

	for response in responses:
	    print(response)

if __name__ == '__main__':
    main()
```

## License

This project is licensed under the MIT License.
