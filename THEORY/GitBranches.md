# PHẦN 4: GIT BRANCHES

---

# 1. Nhánh là gì ?

Trong quản lý mã nguồn (source control), **branch (nhánh)** là một `nhánh rẽ` của dòng mã chính (main codebase), cho phép bạn phát triển các tính năng, sửa lỗi, hoặc thử nghiệm ý tưởng mới mà `không làm ảnh hưởng` đến dòng mã chính hoặc các nhánh khác. Mỗi **branch** là một `bản sao độc lập` của mã nguồn tại một thời điểm nhất định.

**Ví dụ**: Khi làm việc trên một dự án, bạn có thể tạo một nhánh riêng để phát triển tính năng mới, trong khi các thành viên khác tiếp tục làm việc trên **branch chính** (thường là `main` hoặc `master`).

---

# 2. Tại sao nên sử dụng Nhánh ?

1. **Tách biệt công việc**

   - Mỗi branch là một không gian làm việc riêng, giúp tách biệt các thay đổi để không ảnh hưởng đến mã nguồn chính hoặc công việc của người khác.

2. **Hỗ trợ phát triển song song**

   - Branches cho phép nhiều lập trình viên cùng làm việc trên các tính năng hoặc sửa lỗi khác nhau mà không lo xung đột mã nguồn.

3. **Quản lý thử nghiệm**

   - Branches rất hữu ích khi thử nghiệm ý tưởng mới hoặc những thay đổi lớn. Nếu ý tưởng không hiệu quả, bạn có thể xóa branch mà không làm ảnh hưởng đến dự án chính.

4. **Dễ dàng quản lý và triển khai tính năng**

   - Khi hoàn thành và kiểm tra kỹ, bạn có thể hợp nhất (merge) branch vào nhánh chính, đảm bảo các thay đổi đã được kiểm soát.

5. **Khả năng hồi phục (rollback)**
   - Nếu có sự cố trong branch riêng, bạn có thể dễ dàng quay lại trạng thái của branch chính mà không ảnh hưởng đến toàn bộ dự án.

---

# 3. Làm việc với Nhánh

Làm việc với **branch** trong hệ thống quản lý mã nguồn bao gồm các thao tác `tạo`, `chuyển đổi`, và `xóa` **branch**.

**Các thao tác cơ bản:**

1. **Tạo nhánh mới:** Dùng lệnh để tạo một branch mới từ nhánh hiện tại:

   ```bash
   git branch branch_name
   ```

2. **Chuyển đổi giữa các nhánh:** Sử dụng lệnh `checkout` hoặc `switch` để di chuyển giữa các nhánh:

   ```bash
   git checkout branch_name
   git switch branch_name
   ```

3. **Liệt kê các nhánh:** Hiện thi danh sách các nhánh hiện tại:

   ```bash
   git branch
   ```

4. **Xoá nhánh:** Xoá nhánh không còn cần thiết:
   ```bash
   git branch -d branch_name # Nếu branch đã được merge
   git branch -D branch_name # Ép buộc xoá branch chưa được merge
   ```

---

# 4. Chỉnh sửa trên Nhánh

Khi làm việc trên branch, bạn có thể thực hiện các thay đổi, thêm commit, hoặc cập nhật branch hiện tại.

**Quy trình chỉnh sửa nhánh:**

1. **Chỉnh sửa mã nguồn:** Sau khi chuyển sang branch cần chỉnh sửa, bạn có thể thực hiện thay đổi trong file mã nguồn.

2. **Thêm thay đổi vào staging:** Dùng lệnh `git add` để thêm các thay đổi vào khu vực chờ commit.

   ```bash
   git add file_name
   git add .
   ```

3. **Commit thay đổi:** Lưu các thay đổi vào branch hiện tại.

   ```bash
   git commit -m "Mô tả thay đổi"
   ```

4. **Cập nhật nhánh từ branch chính (nếu cần):** Nếu nhánh chính đã thay đổi, bạn cần cập nhật nhánh hiện tại:
   ```bash
   git pull origin main # Hoặc nhánh gốc khác
   ```

---

# 5. Hợp nhất Nhánh

**Merging** là quá trình kết hợp các thay đổi từ một branch khác vào nhánh hiện tại, thường được sử dụng để đưa các tính năng mới hoặc bản sửa lỗi từ nhánh phụ vào nhánh chính.

**Quy trình hợp nhất nhánh:**

1. **Chuyển sang nhánh mục tiêu:** Nhánh mục tiêu là nơi bạn muốn hợp nhất thay đổi.

   ```bash
   git checkout main
   ```

2. **Thực hiện merge:** Kết hợp các thay đổi từ nhánh nguồn vào nhánh hiện tại.

   ```bash
   git merge branch_name
   ```

3. **Xử lý xung đột (nếu có):** Nếu hai nhánh chỉnh sửa cùng một file theo các cách khác nhau, Git sẽ yêu cầu bạn giải quyết xung đột:

- Mở file có xung đột, chỉnh sửa lại nội dung.
- Thêm các thay đổi đã sửa vào staging:

  ```bash
  git add file_name
  ```

- Hoàn tất merge bằng lệnh:
  ```bash
  git commit
  ```

4. **Kiểm tra lại lịch sử:** Sau khi merge, kiểm tra lịch sử commit để đảm bảo mọi thứ đã hợp nhất chính xác:
   ```bash
   git log --oneline
   ```
