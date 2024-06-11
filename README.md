# Zeek Documentation

Welcome to the Zeek Documentation project! This project aims to provide comprehensive documentation for Zeek using Sphinx.This documentation is created for the National Center for Cybersecurity (NCCS) at NED to assist users in understanding and utilizing Zeek.

## View Documentation Locally

Follow these steps to build and view the documentation on your computer.

### Prerequisites

Make sure you have installed:

- [Python](https://www.python.org/downloads/)
- [pip](https://pip.pypa.io/en/stable/installation/)
- [Sphinx](https://www.sphinx-doc.org/en/master/usage/installation.html)

### Steps

1. **Clone the repository**:
    ```bash
    git clonehhttps://github.com/laibahere/zeek-documentation
    cd zeekdocumentation
    ```

2. **Install the required packages**:
    ```bash
    pip install sphinx-rtd-theme
    ```

3. **Build the documentation**:
    ```bash
    make html
    ```

4. **Open the documentation**:
    - On macOS:
        ```bash
        open _build/html/index.html
        ```
    - On Windows:
        ```bash
        start _build/html/index.html
        ```
    - On Linux:
        ```bash
        xdg-open _build/html/index.html
        ```

## Contributing

Want to help? Follow these steps:

1. **Fork the repository**.
2. **Create a new branch**:
    ```bash
    git checkout -b feature-branch
    ```
3. **Make your changes**.
4. **Commit your changes**:
    ```bash
    git commit -m 'Add a new feature'
    ```
5. **Push to your branch**:
    ```bash
    git push origin feature-branch
    ```
6. **Create a Pull Request**.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

## Contact

Questions? Reach out via:

- **Email**: laibawaseem006@gmail.com
- **GitHub Issues**: [Create an issue](https://github.com/laibahere/zeekdocumentation/issues)

---

Thank you for using Zeek Documentation! We hope it helps you in your projects.
