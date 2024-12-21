# PHẦN 2: TERMINAL

---

# 1. Giới thiệu về Terminal

## 1.1. Terminal là gì ?

**Terminal** là một công cụ quan trọng để giao tiếp với máy tính thông qua dòng lệnh (Command Line Interface - CLI). Thay vì sử dụng chuột và giao diện đồ họa (GUI), người dùng nhập các lệnh văn bản để thực hiện các tác vụ, từ đơn giản như quản lý file, thư mục, đến phức tạp như cấu hình hệ thống và phát triển phần mềm.

**Chức năng chính của Terminal:**

- **Quản lý file và thư mục**: Người dùng có thể tạo, chỉnh sửa, xóa, sao chép hoặc di chuyển file và thư mục mà không cần dùng giao diện đồ họa.
- **Cài đặt, cấu hình phần mềm**: Dễ dàng cài đặt và cấu hình phần mềm bằng cách sử dụng các trình quản lý gói như `apt`, `yum`, hoặc `pip`.
- **Phát triển phần mềm**: Terminal hỗ trợ biên dịch mã nguồn, chạy chương trình, và kiểm tra lỗi trong quá trình phát triển.
- **Tự động hóa công việc**: Thông qua script (tệp chứa lệnh), Terminal giúp tự động hóa các tác vụ thường xuyên hoặc phức tạp.

**Giao diện cơ bản của Terminal:**
Khi mở Terminal, bạn thường thấy dòng lệnh hiển thị như sau:

```bash
user@hostname:~$
```

Trong đó:

- `user`: Tên người dùng hiện tại.
- `hostname`: Tên của máy tính hoặc máy chủ.
- `~`: Biểu thị thư mục làm việc hiện tại (thường là thư mục chính của người dùng).
- `$`: Ký hiệu của lệnh người dùng (dấu `#` biểu thị quyền admin).

## 1.2. Một số Terminal phổ biến

Các hệ điều hành khác nhau sử dụng các công cụ Terminal khác nhau, phù hợp với nhu cầu của người dùng:

**Windows:**

1. Command Prompt (CMD):

- Giao diện dòng lệnh cơ bản có từ lâu trên Windows.
- Hỗ trợ các lệnh DOS và một số lệnh hệ thống cơ bản của Windows.
- Ví dụ: `dir`, `cd`, `copy`.

2. PowerShell:

- Phiên bản nâng cao của CMD với nhiều tính năng mạnh mẽ hơn.
- Hỗ trợ script bằng ngôn ngữ PowerShell để quản lý hệ thống và tự động hóa tác vụ.
- Ví dụ: `Get-ChildItem`, `Get-Process`.

3. Windows Subsystem for Linux (WSL):

- Cho phép người dùng chạy môi trường Linux ngay trên Windows.
- Hỗ trợ các lệnh Linux như `ls`, `cp`, `grep`.

**Linux:**

1. GNOME Terminal:

- Terminal mặc định của GNOME Desktop Environment.
- Tùy chỉnh dễ dàng, hỗ trợ nhiều tab và tính năng cao cấp.

2. Konsole:

- Terminal phổ biến trên KDE Desktop Environment.
- Cung cấp giao diện mượt mà, hỗ trợ mở nhiều tab và cấu hình phím tắt.

3. xterm:

- Một Terminal truyền thống nhẹ và tối giản, phù hợp cho các hệ thống cần tiết kiệm tài nguyên.

**macOS:**

1. Terminal:

- Công cụ dòng lệnh mặc định trên macOS.
- Hỗ trợ đầy đủ các lệnh UNIX và tương thích với các công cụ Linux.

2. iTerm2:

- Một sự thay thế mạnh mẽ hơn cho Terminal mặc định.
- Hỗ trợ tìm kiếm nâng cao, chia màn hình, và tùy chỉnh giao diện.

## 1.3. Lợi ích của Terminal

1. **Tốc độ xử lý nhanh:**

- Với Terminal, bạn có thể thực hiện nhiều tác vụ chỉ bằng một dòng lệnh, thay vì phải qua nhiều bước như khi sử dụng GUI.
- Ví dụ: Thay vì mở thư mục, tìm kiếm file, rồi xóa, bạn chỉ cần một lệnh như:
  ```bash
  rm file_name
  ```

2. **Thực hiện các tác vụ phức tạp:**

- Thông qua script, bạn có thể thực hiện tự động hóa các tác vụ lặp đi lặp lại.
- Ví dụ: Một script đơn giản để sao lưu dữ liệu:
  ```bash
  #!/bin/bash
  cp -r /home/user/data /home/user/backup
  ```

3. **Hiệu quả trên hệ thống tài nguyên thấp:**

- Terminal không tiêu tốn nhiều tài nguyên hệ thống, phù hợp cho các máy tính cũ hoặc khi cần hiệu suất cao.

4. **Khả năng kiểm soát cao:**

- Terminal cung cấp quyền truy cập sâu hơn vào hệ điều hành, giúp bạn kiểm soát nhiều khía cạnh hơn, đặc biệt khi quản lý máy chủ hoặc hệ thống.

5. **Hỗ trợ lập trình viên và DevOps:**

- Các công cụ như git, docker, kubectl đều được sử dụng chủ yếu trên Terminal.
- Lập trình viên có thể biên dịch và chạy mã trực tiếp, ví dụ:
  ```bash
  gcc -o program program.c
  ./program
  ```

---

# 2. Di chuyển giữa các Thư mục (Directories)

Trong Terminal, bạn có thể di chuyển qua lại giữa các thư mục (Directories) bằng lệnh `cd` (change directory):

**Các lệnh cơ bản:**

1. Di chuyển vào thư mục con:

   ```bash
   cs folder_name
   ```

   Thay `folder_name` bằng tên thư mục bạn muốn vào.

2. Trở về thư mục cha:

   ```bash
   cd ..
   ```

3. Trở về thư mục gốc (home):

   ```bash
   cd ~
   ```

4. Di chuyển đến đường dẫn cụ thể:

   ```bash
   cd /path/to/directory
   ```

5. Kiểm tra đường dẫn hiện tại:
   ```bash
   pwd
   ```
   Lệnh `pwd` (print working directory) hiển thị đường dẫn thư mục hiện tại.

---

# 3. Làm việc với Tệp (Files) và Thư mục (Directories)

Bạn có thể sử dụng Terminal để tạo, xem, chỉnh sửa, di chuyển, sao chép, hoặc xóa file và thư mục.

## 3.1. Quản lý Files

1. Tạo file:

   ```bash
   touch file_name
   ```

   Thay `file_name` bằng tên file bạn muốn tạo.

2. Xem nội dung file:

   ```bash
   cat file_name
   ```

3. Chỉnh sửa file:
   Sử dụng trình soạn thảo như nano, vim:

   ```bash
   cat file_name
   ```

4. Xoá file:

   ```bash
   rm file_name
   ```

5. Đổi tên hoặc di chuyển file:

   ```bash
   mv old_file_name new_file_name
   ```

   Thay `old_file_name` và `new_file_name` bằng tên file tương ứng.

6. Sao chép file:
   ```bash
   cp source_file destination_file
   ```
   Thay `source_file` và `destination_file` bằng tên file tương ứng.

## 3.2. Quản lý Directories

1. Tạo thư mục:

   ```bash
   mkdir folder_name
   ```

2. Xoá thư mục rỗng:

   ```bash
   rmdir folder_name
   ```

3. Xoá thư mục cùng toàn bộ nội dung:

   ```bash
   rm -r folder_name
   ```

4. Đổi tên hoặc di chuyển thư mục:

   ```bash
   mv old_folder_name new_folder_name
   ```

5. Liệt kê nội dung thư mục:
   ```bash
   ls
   ```
   Tuỳ chọn:
   - `ls -l`: Hiển thị chi tiết.
   - `ls -a`: Hiển thị cả file ẩn.
