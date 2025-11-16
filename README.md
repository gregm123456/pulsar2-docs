# Pulsar2 User Manual

[Web preview](https://pulsar2-docs.readthedocs.io/zh_CN/latest/)

## 1. Project background

Public repository for the Pulsar2 AI toolchain user guide.

- Provide a unified internal documentation portal for the AI toolchain
- Reduce maintenance overhead for AI toolchain developers
- Reduce the learning curve for AI toolchain users

## 2. Local run guide

### 2.1 git clone

```bash
git clone https://github.com/AXERA-TECH/pulsar2-docs.git
```

Directory tree:

```bash
.
├── LICENSE
├── Makefile
├── README.md
├── build
│   ├── doctrees
│   └── html
├── requirements.txt
└── source                      # 文档主体
    ├── appendix
    ├── conf.py
    ├── doc_update_info
    ├── examples                # Some examples are stored as .zip files; GitHub Pages may not support direct downloads from online docs
    ├── faq
    ├── index.rst
    ├── media
    ├── pulsar2
    ├── user_guides_advanced
    ├── user_guides_config
    ├── user_guides_quick
    └── user_guides_runtime
```

### 2.2 Build

Install dependencies

```bash
pip install -r requirements.txt
```

Run the following commands from the project root

```bash
$ make clean
$ make html
```

### 2.3 Preview

After building, open `build/html/index.html` in your browser. If you built the docs on a remote server, you can use SSH port forwarding to access the compiled documentation. Example workflow:

Start a simple HTTP server in the compiled `build/html/` folder using Python:

```bash
$ cd build/html/
-$ python -m SimpleHTTPServer 8005  # For python2, you can customize the port
# or
$ python3 -m http.server 8005      # For python3, 端口可以自定义
```

Then forward the port through SSH and access the site in a local browser:

```bash
ssh -L 8005:localhost:8005 username@server
```

然后本地浏览器访问: `localhost:8005/index.html`

## 3. Reference

- This project is built with Sphinx. For more details see https://www.sphinx-doc.org/en/master/

## 4. Release


