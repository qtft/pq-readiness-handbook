# Post-Quantum Readiness Handbook for Thai Organizations (คู่มือการเตรียมความพร้อมเพื่อเข้าสู่ยุคควอนตัมสำหรับองค์กรไทย)

This project uses a [Jupyter-Book](https://jupyterbook.org/en/stable/intro.html) template from [TeachBooks](https://github.com/TeachBooks/template).

Live Handbook: https://qtft.github.io/pq-readiness-handbook

# Build the book locally

Create Python environment
```
python3 -m venv venv
source venv/bin/activate
```

Installation
```
pip install --upgrade pip  
pip install -r requirements.txt
```

Build the book
```
teachbooks build book
```

Use the following command for running the server locally.
```
teachbooks serve
```

To stop the server, run:
```
teachbooks serve stop
```

# Deploy the book
Once a commit is merged, GitHub Action deploys it automatically