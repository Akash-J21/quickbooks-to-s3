# QuickBooks Desktop to AWS S3 Data Pipeline

## 📌 Overview

This project extracts data from **QuickBooks Desktop (via ODBC DSN connection)**, converts the data into **Parquet format**, and uploads it to an **AWS S3 bucket**.

It is designed for efficient data migration and storage, enabling downstream analytics and processing.

---

## ⚙️ Features

* 🔗 Connects to QuickBooks Desktop using ODBC (DSN)
* 📊 Extracts multiple tables dynamically
* 📁 Converts data into Parquet format (optimized for analytics)
* ☁️ Uploads files to AWS S3
* ⚙️ Config-driven using YAML file

---

## 🏗️ Project Structure

```
.
├── main.ipynb              # Main script
├── config.yaml          # Configuration file
├── requirements.txt     # Dependencies
└── README.md            # Project documentation
```

---

## 📋 Prerequisites

Make sure you have the following installed:

* Python 3.8+
* QuickBooks Desktop with ODBC Driver configured
* AWS Account with S3 access

---

## 📦 Installation

1. Clone the repository:

```bash
git clone https://github.com/Akash-J21/quickbooks-to-s3.git

```

2. Install dependencies:

```bash
pip install -r requirements.txt
```

---

## 🔧 Configuration

Create a `config.yaml` file in the root directory if not available:

```yaml
database:
  dsn_name: "Your_DSN_Name"

aws:
  access_key_id: "YOUR_ACCESS_KEY"
  secret_access_key: "YOUR_SECRET_KEY"
  bucket_name: "your-s3-bucket-name"

tables:
  - table1
  - table2
  - table3
```

---

## ▶️ Usage

Run the script:

```bash
python main.ipynb
```

---

## 🔄 Workflow

1. Read configuration from YAML
2. Connect to QuickBooks via DSN
3. Extract table data into Pandas DataFrames
4. Convert data to Parquet format
5. Upload Parquet files to AWS S3

---

## 📚 Dependencies

Create a `requirements.txt` file with if not available:

```
pyodbc
pandas
boto3
pyarrow
pyyaml
```

---

## ⚠️ Error Handling

* Logs errors while reading tables
* Skips failed tables and continues processing
* Handles S3 upload failures gracefully

---

## 🔐 Security Best Practices

* ❌ Avoid hardcoding AWS credentials
* ✅ Use environment variables or IAM roles instead
* 🔒 Keep `config.yaml` out of version control (add to `.gitignore`)

---

## 🚀 Future Improvements

* Add logging framework (e.g., `logging`)
* Incremental data load support
* Retry mechanism for S3 uploads
* Parallel processing for faster execution

---

## 👨‍💻 Author

**Akash J**
📧 [jakash2105@gmail.com](mailto:jakash2105@gmail.com)

---

