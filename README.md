[![Open in Visual Studio Code](https://classroom.github.com/assets/open-in-vscode-2e0aaae1b6195c2367325f4f02e2d04e9abb55f0b24a779b69b11b9e10269abc.svg)](https://classroom.github.com/online_ide?assignment_repo_id=23574097&assignment_repo_type=AssignmentRepo)
# Day 10 Lab: Data Pipeline & Data Observability

**Student Email:** 26ai.taidc@vinuni.edu.vn
**Name:** Dinh Cong Tai

---

## Mo ta

Day 10 Lab ve Data Pipeline & Data Observability. Bai lab bao gom viec xay dung mot ETL pipeline de xu ly, lam sach va xac thuc du lieu tu file `raw_data.json`, sau do xuat ra `processed_data.csv`. Ngoai ra, bai lab con thuc hien kiem tra muc do anh huong cua chat luong du lieu den AI Agent thong qua viec mo phong so sanh ket qua giua du lieu da lam sach va du lieu rac (`garbage_data.csv`).

---

## Cach chay (How to Run)

### Prerequisites
```bash
pip install pandas
```

### Chay ETL Pipeline
```bash
python3 solution.py
```

### Chay Agent Simulation (Stress Test)
```bash
# 1. Tao file du lieu rac de phuc vu thi nghiem
python3 generate_garbage.py

# 2. Chay thi nghiem mo phong LLM Agent so sanh Clean vs Garbage data
python3 agent_simulation.py
```

---

## Cau truc thu muc

```
├── solution.py              # ETL Pipeline script & validation logic
├── generate_garbage.py      # Script tao data hieu ung xau (poisoned data)
├── agent_simulation.py      # Script mo phong Agent dua ra lua chon
├── processed_data.csv       # Output cua pipeline (Du lieu sach)
├── garbage_data.csv         # File du lieu rac cho thi nghiem
├── experiment_report.md     # Bao cao thi nghiem Data Observability
└── README.md                # File nay
```

---

## Ket qua

- Qua trinh ETL da xu ly thong tin tu `raw_data.json`.
- So ban ghi **hop le (Valid)**: 3 ban ghi.
- So ban ghi **bi loai (Errors)**: 2 ban ghi (due to negative prices or missing fields).
- **Thi nghiem Agent**: Cho thay ro su khac biet hoan toan ve do chinh xac cua Agent (10/10 voi data clean vs 1/10 voi data garbage). Qua do giup chung minh viec xay dung Pipeline lam sach du lieu truoc khi dua vao cac mo hinh GenAI la bat buoc de dong bo chat luong "Garbage In, Garbage Out".
