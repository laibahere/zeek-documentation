# Zeek Documentation

Welcome to the Zeek Documentation project! This project aims to provide comprehensive documentation for Zeek using Sphinx. This documentation is created for the National Center for Cybersecurity (NCCS) at NED to assist users in understanding and utilizing Zeek.

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
    git clone https://github.com/laibahere/zeek-documentation.git
    cd zeek-documentation
    ```

2. **Install the required packages**:
    ```bash
    pip install sphinx sphinx-rtd-theme
    ```

3. **Run Virtual Environment**: 
    ```bash 
     source zeekrenv/bin/activate
    ```

4. **Build the documentation**:
    ```bash
    make html
    ```

5. **Open the documentation**:
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

## Contact

Questions? Reach out via:

- **Email**: laibawaseem006@gmail.com

---

Thank you for using Zeek Documentation! We hope it helps you in your projects.
```
