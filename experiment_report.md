# Experiment Report: Data Quality Impact on AI Agent

**Student ID:** 2A202600034
**Name:** Dinh Cong Tai
**Date:** 15/04/2026

---

## 1. Ket qua thi nghiem

Chay `agent_simulation.py` voi 2 bo du lieu va ghi lai ket qua:

| Scenario | Agent Response | Accuracy (1-10) | Notes |
|----------|----------------|-----------------|-------|
| Clean Data (`processed_data.csv`) | Based on my data, the best choice is Laptop at $1200. | 10 | Agent dua ra lua chon hop ly voi muc gia thuc te. |
| Garbage Data (`garbage_data.csv`) | Based on my data, the best choice is Nuclear Reactor at $999999. | 1 | Agent bi danh lua boi du lieu rac, dua ra lua chon phi ly. |

---

## 2. Phan tich & nhan xet

### Tai sao Agent tra loi sai khi dung Garbage Data?

Khi su dung Garbage Data, Agent da dua ra cau tra loi hoan toan vo ly (chon "Nuclear Reactor" voi gia $999999). Nguyen nhan chinh la do chat luong du lieu dau vao kem, bao gom nhieu van de nghiem trong:
- Trong tap the du lieu co nhung gia tri ngoai lai (outliers) rat lon va khong thuoc ve thuc te kinh doanh, lam sai lech thuat toan lua chon.
- Du lieu chua cac ban ghi trung lap (duplicate rows) hoac gia tri rong (null values) khien mo hinh mat di su hieu chinh, them vao nhieu muc nhiem.
- Viec sai lech kieu du lieu (wrong data types) khien he thong khong the phan loai hay tinh toan gia tri thuc cua san pham. 
Mo hinh hoat dong theo nguyen tac chap nhan moi thu tu nguon mo, nen neu khong co buoc xac thuc (validation), cac "poisoned records" se de dang lua gat cac cong cu tinh toan hoac mo hinh tao sinh.

---

## 3. Ket luan

**Quality Data > Quality Prompt?** Dong y.

Cho du prompt duoc thiet ke rat tot de chi dan, nhung neu du lieu dau vao la sai hoac phi logic (Garbage In), thi tat yeu ket qua tra ve se khong the xu dung duoc (Garbage Out). Chat luong du lieu dong vai tro la nen tang, trong khi prompt chi la cong cu khai thac. Vi vay, viec xay dung he thong xu ly va xac thuc du lieu o muc khoi tap tin luon can uu tien hang dau trong moi du an Data/AI.
