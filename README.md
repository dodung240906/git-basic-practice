# BÁO CÁO BÀI TẬP THỰC HÀNH GIT & GITHUB

## BÀI 1: CÂU HỎI TƯ DUY
**Câu hỏi:** Staging area (Index) có vai trò gì mà nếu không có nó, việc commit sẽ bất tiện như thế nào?
**Trả lời:**
- **Vai trò:** Staging Area là vùng đệm trung gian giúp người dùng chọn lọc chính xác từng file hoặc từng dòng code cụ thể để đóng gói vào commit, thay vì phải commit toàn bộ thay đổi.
- **Bất tiện nếu không có:** Không thể chia nhỏ công việc thành nhiều commit rõ ràng; dễ commit nhầm các file tạm, file rác hoặc các đoạn code thử nghiệm dở dang.

---

## BÀI 3: BẢNG SO SÁNH 3 LOẠI GIT RESET

| Loại Reset | Ảnh hưởng Repository | Ảnh hưởng Staging Area | Ảnh hưởng Working Directory |
| :--- | :--- | :--- | :--- |
| **`git reset --soft`** | Lùi về commit chỉ định | Giữ nguyên (vẫn được Stage) | Giữ nguyên (không mất code) |
| **`git reset --mixed`** | Lùi về commit chỉ định | Bị xóa khỏi Staging (Unstage) | Giữ nguyên |
| **`git reset --hard`** | Lùi về commit chỉ định | Xóa sạch | Xóa sạch toàn bộ thay đổi |

**Câu hỏi tư duy:** Nếu đã push code lên GitHub cho cả team dùng, việc dùng `git reset --hard` để lùi lại commit có an toàn không? Vì sao?
- **Trả lời:** **KHÔNG AN TOÀN**. 
- **Lý do:** Lệnh này viết lại lịch sử commit (rewrite history). Khi buộc phải push đè (`git push -f`), lịch sử trên remote bị lệch so với máy đồng nghiệp, gây ra xung đột (conflict) nghiêm trọng hoặc làm mất dữ liệu người khác đã kéo về.

---

## BÀI 5: LÝ THUYẾT GIT PULL
**Câu hỏi:** `git pull` thực chất là tổ hợp của 2 lệnh nào?
- **Trả lời:** `git pull` = `git fetch` (tải các commit mới từ remote về) + `git merge` (gộp các thay đổi đó vào nhánh hiện tại).
