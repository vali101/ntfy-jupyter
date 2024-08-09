[![PyPI version](https://badge.fury.io/py/ntfy-jupyter.svg)](https://pypi.org/project/ntfy-jupyter/)

# ntfy-jupyter

`ntfy-jupyter` is an IPython extension that allows you to send notifications using the [ntfy](https://ntfy.sh/) service directly from Jupyter notebooks. This extension helps you keep track of your notebook tasks and results, sending notifications upon cell execution or failure.

## Features

- **Send Notifications**: Notify on cell execution success or failure.
- **Customizable Messages**: Include custom messages and cell code in notifications.
- **Error Reporting**: Automatically notify if a cell fails to execute.
- **Topic Creation**: Generate unique, pseudo-private topic names for notifications.

## Table of Contents

- [Installation](#installation)
- [Usage](#usage)
- [Configuration](#configuration)
- [Development](#development)
- [Contributing](#contributing)
- [License](#license)

## Installation

To install `ntfy-jupyter`, use [Poetry](https://python-poetry.org/) or pip. 

### Using Poetry

1. Clone the repository:

   ```bash
   git clone https://github.com/vali101/ntfy-jupyter
   cd ntfy-jupyter
   ```

2. Install dependencies:

   ```bash
   poetry install
   ```

### Using pip

Alternatively, you can install `ntfy-jupyter` directly from PyPI:

```bash
pip install ntfy-jupyter
```

## Usage

To use `ntfy-jupyter`, follow these steps:

1. **Load the Extension**: In a Jupyter notebook cell, load the extension with:

   ```python
   %load_ext ntfy_jupyter
   ```

2. **Use the Magic Command**: Notify about cell execution or errors using the `notify` magic command:

   ```python
   %%notify -t your_topic -m "Your message" -e -i
   # Your cell code here
   ```

   - `-t` or `--topic`: The topic for the notification.
   - `-m` or `--message`: The message to send. Defaults to an empty message.
   - `-e` or `--errors`: Include error details in the notification if the cell fails.
   - `-i` or `--include`: Include the cell code in the notification.

## Topic Creation

You can use the `create_topic` utility function to generate unique, pseudo-private topic names:

```python
from ntfy_jupyter import create_topic

topic = create_topic('alerts')
print(f"Generated topic: {topic}")
```

- `create_topic(base_name, key_length=16)`: Creates a unique topic name by appending a cryptographic key to the base name.

## Configuration

You can configure the behavior of `ntfy-jupyter` through the command-line arguments of the `%notify` magic command. Ensure you have a valid `ntfy` topic to receive notifications.

## Development

To contribute to the development of `ntfy-jupyter`, follow these steps:

1. **Clone the Repository**:

   ```bash
   git clone https://github.com/yourusername/ntfy-jupyter.git
   cd ntfy-jupyter
   ```

2. **Set Up Development Environment**:

   ```bash
   poetry install
   ```

4. **Make Your Changes** and submit a pull request.

For detailed contribution guidelines, refer to [CONTRIBUTING.md](CONTRIBUTING.md).

## Contributing

We welcome contributions to `ntfy-jupyter`. Please follow these guidelines:

- **Fork the Repository**: Create your own fork of the repository.
- **Create a Branch**: Make a new branch for your changes.
- **Submit a Pull Request**: Provide a clear description of your changes.

Please ensure your code adheres to the project's style guide and passes all tests.

## License

`ntfy-jupyter` is licensed under the MIT License. See [LICENSE](LICENSE) for more details.
