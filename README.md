# SimpleParallelize

SimpleParallelize is a lightweight Python package that helps you easily parallelize HTTP requests with a progress bar. It aims to make parallel processing of requests simple and user-friendly.

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
from simpleparallelize import run_requests

def my_request_function(request):
    # Add your request handling code here
    pass

def main():
	requests = [...] # List of requests
	responses = parallelize(requests, my_request_function)

if __name__ == '__main__':
    main()
```

## Example

A more concrete example with a request handling function that makes HTTP requests:

```python
import requests
from simpleparallelize import run_requests

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
