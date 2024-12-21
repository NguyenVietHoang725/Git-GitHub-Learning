# PHẦN 5 : GIT STASH & SUBMODULES

---

# 1. Git Stash

## 1.1. Stash là gì ?

**Git Stash** là một tính năng trong Git cho phép bạn lưu tạm thời các thay đổi đang thực hiện trong working directory mà không cần commit chúng. Điều này rất hữu ích khi bạn muốn chuyển sang làm việc trên nhánh khác hoặc xử lý một vấn đề khẩn cấp mà không muốn mất các thay đổi hiện tại.

## 1.2. Lợi ích của Stash

1. **Lưu trữ tạm thời:** Bạn có thể lưu các thay đổi mà không cần commit chúng.
2. **Tiện lợi:** Dễ dàng chuyển đổi giữa các nhánh mà không mất tiến trình công việc.
3. **Phục hồi nhanh chóng:** Bạn có thể áp dụng lại các thay đổi đã stash bất kỳ lúc nào.

## 1.3. Các thao tác với Stash

1. **Lưu thay đổi vào stash:**
   ```bash
   git stash
   ```
   Lệnh này lưu các thay đổi trong working directory và reset chúng về trạng thái sạch (clean).
2. **Liệt kê các stash đã lưu:**
   ```bash
    git stash list
   ```
   Hiển thị danh sách các stash đã lưu cùng với ID của chúng.
3. **Áp dụng lại stash:**
   ```bash
   git stash apply
   ```
   Áp dụng lại thay đổi từ stash vào working directory mà không xóa stash.
4. **Xoá stash sau khi áp dụng:**
   ```bash
   git stash pop
   ```
   Áp dụng stash vào working directory và xóa stash đó khỏi danh sách.
5. **Xoá stash cụ thể:**
   ```bash
   git stash drop stash_id
   ```
   Xóa stash theo ID đã chỉ định.
6. **Xoá toàn bộ stash:**
   ```bash
   git stash clear
   ```

---

# 2. Git Submodule

## 2.1. Submodule là gì ?

**Git Submodule** là một tính năng cho phép bạn nhúng (embed) một kho Git khác vào trong kho Git của dự án chính. Submodule thường được sử dụng khi bạn cần tích hợp một thư viện hoặc dự án khác làm một phần của dự án chính mà vẫn muốn quản lý chúng độc lập.

## 2.2. Lợi ích của Submodule

1. **Tái sử dụng mã nguồn:** Dễ dàng tích hợp và sử dụng lại các thư viện hoặc module.
2. **Quản lý độc lập:** Submodule được quản lý như một kho Git riêng biệt, cho phép bạn cập nhật hoặc thay đổi mà không ảnh hưởng đến dự án chính.
3. **Linh hoạt:** Thích hợp cho các dự án lớn hoặc có sự phụ thuộc phức tạp.

## 2.3. Các thao tác với Submodule

1. **Thêm Submodule vào dự án:**

   ```bash
   git submodule add repo_url path
   ```

   - `repo_url`: Đường dẫn đến kho submodule.
   - `path`: Đường dẫn thư mục lưu submodule trong dự án chính.

2. **Cập nhập Submodule:**

   ```bash
   git submodule update --remote
   ```

   Cập nhật submodule lên phiên bản mới nhất từ kho của nó.

3. **Clone dự án có Submodule:**
   Khi clone một dự án có submodule, bạn cần khởi tạo và tải submodule:

   ```bash
   git clone repo_url
   git submodule init
   git submodule update
   ```

4. **Xoá Submodule:**
   Để xóa một submodule, bạn cần thực hiện các bước sau:
   - Xóa submodule khỏi file .gitmodules và .git/config.
   - Xóa thư mục chứa submodule:
     ```bash
     git rm --cached path_to_submodule
     rm - rf path_to_submodule
     ```
