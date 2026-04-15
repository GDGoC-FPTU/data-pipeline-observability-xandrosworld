# Day 10 Lab: Data Pipeline & Data Observability

**Student Email:** 26ai.thanhmt@vinuni.edu.vn  
**Student ID:** 2A202600127  
**Name:** Mai Tấn Thành

## Mo ta

Repo nay hoan thien mot ETL pipeline don gian cho du lieu san pham. Pipeline doc du lieu tu file JSON, loai bo record khong hop le, chuan hoa category, tinh gia sau khi giam 10%, them timestamp xu ly va luu ket qua ra file CSV. Ngoai phan ETL, repo con co mot agent simulation de minh hoa tac dong cua du lieu sach va du lieu rac toi chat luong cau tra loi.

## Cach chay

### Prerequisites

```bash
pip install pandas pytest
```

### Chay ETL Pipeline

```bash
python solution.py
```

Pipeline se doc du lieu tu `raw_data.json` va tao file `processed_data.csv`.

### Tao bo du lieu garbage

```bash
python generate_garbage.py
```

Lenh nay tao file `garbage_data.csv` gom duplicate IDs, wrong data type, outlier va null values.

### Chay Agent Simulation

```bash
python agent_simulation.py
```

Script se thu agent voi `processed_data.csv` va `garbage_data.csv` de so sanh ket qua.

### Chay test

```bash
pytest -q
```

## Cau truc thu muc

```text
.
|-- solution.py
|-- raw_data.json
|-- processed_data.csv
|-- generate_garbage.py
|-- agent_simulation.py
|-- experiment_report.md
|-- README.md
`-- tests/test_autograder.py
```

## Ket qua

Du lieu dau vao co 5 records. Sau khi validate, pipeline giu lai 3 records hop le va loai 2 records vi gia khong hop le hoac category rong. File output co them cac cot `discounted_price` va `processed_at`, giup theo doi business logic va thoi diem xu ly. Ket qua stress test cho thay agent hoat dong tot hon voi du lieu sach, trong khi du lieu garbage de gay sai lech nghiem trong, vi agent co the chon mot record bat thuong nhu `Nuclear Reactor` chi vi gia tri gia cao nhat.
