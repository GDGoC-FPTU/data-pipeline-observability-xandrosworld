# Experiment Report: Data Quality Impact on AI Agent

**Student ID:** 2A202600127  
**Name:** Mai Tấn Thành  
**Date:** 2026-04-15

---

## 1. Ket qua thi nghiem

Chay `agent_simulation.py` voi 2 bo du lieu va ghi lai ket qua:

| Scenario | Agent Response | Accuracy (1-10) | Notes |
|----------|----------------|-----------------|-------|
| Clean Data (`processed_data.csv`) | Agent: Based on my data, the best choice is Laptop at $1200. | 8 | Du lieu sach giup agent tim dung nhom `electronics` va chon san pham hop ly nhat theo logic hien tai. Cau tra loi con don gian, nhung ket qua van hop ly va nhat quan voi du lieu da xu ly. |
| Garbage Data (`garbage_data.csv`) | Agent: Based on my data, the best choice is Nuclear Reactor at $999999. | 1 | Agent bi outlier chi phoi va dua ra mot ket qua phi thuc te vi khong co validation cho duplicate, wrong type, outlier va gia tri bat thuong. |

---

## 2. Phan tich & nhan xet

### Tai sao Agent tra loi sai khi dung Garbage Data?

Agent trong bai nay khong thuc su hieu ngu nghia cua du lieu, no chi loc category va lay record co gia cao nhat. Vi vay, khi du lieu garbage chua duplicate IDs, wrong data type, outlier va null values, toan bo qua trinh suy luan rat de bi lech. Record `Nuclear Reactor` co gia 999999 la mot outlier cuc lon, nhung agent van xem no la lua chon tot nhat chi vi gia tri lon nhat trong nhom electronics. Dieu nay cho thay neu khong co validation va data quality checks, mot tac nhan AI hoac script truy van don gian se toi uu tren thong tin sai va dua ra ket luan vo ly. Ngoai ra, wrong data type nhu `ten dollars` co the gay loi khi tinh toan hoac sap xep, duplicate IDs lam mo ho nguyen tac xac dinh ban ghi duy nhat, con null values lam mat ngu canh can thiet. Garbage data khong chi lam giam do chinh xac ma con lam giam do tin cay cua he thong, vi cau tra loi co the nghe hop ly ve mat cu phap nhung hoan toan sai ve mat nghiep vu.

---

## 3. Ket luan

**Quality Data > Quality Prompt?** Dong y. Prompt tot chi giup agent dien dat va truy van ro hon, nhung neu du lieu nen sai, thieu hoac bi nhiem rac thi ket qua van sai. Chat luong du lieu la dieu kien nen tang de mo hinh hoac agent dua ra cau tra loi dang tin cay.
