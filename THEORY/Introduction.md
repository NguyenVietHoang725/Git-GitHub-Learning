# PHẦN 1: GIỚI THIỆU VỀ GIT

---

# 1. Git là gì ?

## 1.1. Source Control

### 1.1.1. Source Control là gì ?

**Source Control** (hay còn gọi là **Version Control**) là một hệ thống quản lý các thay đổi đối với mã nguồn hoặc tài liệu theo thời gian. Nó được sử dụng để lưu trữ, theo dõi lịch sử chỉnh sửa, và hợp tác làm việc trên các dự án, đặc biệt là trong phát triển phần mềm.

### 1.1.2. Chức năng chính

- **Theo dõi thay đổi**: Lưu lại lịch sử thay đổi của tệp, bao gồm ai đã thực hiện thay đổi, khi nào và nội dung thay đổi.
- **Quản lý phiên bản**: Cho phép quay lại các phiên bản trước nếu cần.
- **Hợp tác**: Hỗ trợ nhiều người làm việc trên cùng một dự án mà không xung đột thay đổi.
- **Phân nhánh (Branching)**: Tạo các nhánh riêng để thử nghiệm hoặc phát triển tính năng mới mà không ảnh hưởng đến mã nguồn chính.
- **Hợp nhất (Merging)**: Kết hợp các thay đổi từ các nhánh khác nhau vào một nhánh chung.

### 1.1.3. Các loại Source Control

- **Hệ thống Local**: Dữ liệu được lưu trữ và quản lý trên máy cá nhân. _Ví dụ: RCS._
- **Hệ thống Centralized**: Dữ liệu được lưu trên một máy chủ trung tâm, và các nhà phát triển kết nối tới máy chủ để làm việc. _Ví dụ: SVN, Perforce._
- **Hệ thống Distributed**: Mỗi nhà phát triển giữ một bản sao đầy đủ của kho dữ liệu (repository) trên máy cá nhân. _Ví dụ: Git, Mercurial._

### 1.1.4. Công cụ phổ biến

- **Git**: Là hệ thống quản lý mã nguồn phân tán phổ biến nhất hiện nay. Thường sử dụng với các nền tảng như GitHub, GitLab, Bitbucket.
- **Subversion (SVN)**: Một công cụ quản lý mã nguồn tập trung.
- **Mercurial**: Giống Git nhưng ít phổ biến hơn.
- **TFS/Azure DevOps**: Công cụ của Microsoft dành cho quản lý mã nguồn và dự án.

### 1.1.5. Lợi ích của Source Control

- **Bảo vệ dữ liệu**: Giảm nguy cơ mất mát mã nguồn do lỗi người dùng hoặc sự cố hệ thống.
- **Cải thiện hợp tác**: Hỗ trợ làm việc nhóm hiệu quả hơn, đặc biệt là với các dự án lớn.
- **Quản lý lịch sử**: Giúp dễ dàng kiểm tra, đánh giá, và gỡ lỗi thông qua lịch sử thay đổi.
- **Tăng năng suất**: Hỗ trợ phát triển song song và quản lý nhiều phiên bản của dự án.

## 1.2. Git

### 1.2.1. Git là gì ?

**Git** là một hệ thống quản lý mã nguồn phân tán (Distributed Version Control System) phổ biến nhất, được Linus Torvalds phát triển vào năm 2005. Git cho phép theo dõi thay đổi mã nguồn, quản lý các phiên bản, và làm việc nhóm hiệu quả trên các dự án phần mềm.

### 1.2.2. Tại sao nên sử dụng Git ?

- **Phân tán (Distributed)**:

  - Mỗi người dùng có một bản sao đầy đủ của toàn bộ lịch sử dự án trên máy tính của mình.
  - Giảm phụ thuộc vào máy chủ trung tâm, làm việc offline cũng hiệu quả.

- **Theo dõi lịch sử thay đổi chi tiết**:

  - Git lưu lại toàn bộ lịch sử chỉnh sửa của dự án, bao gồm ai, khi nào, và thay đổi gì.

- **Hỗ trợ làm việc nhóm hiệu quả**:

  - Dễ dàng hợp tác, tạo nhánh (branch), hợp nhất (merge), và giải quyết xung đột mã nguồn.

- **Nhanh và nhẹ**:

  - Git được thiết kế để hoạt động nhanh và tối ưu, đặc biệt là với các dự án lớn.

- **Quản lý nhánh linh hoạt**:

  - Nhánh trong Git rất nhẹ và dễ tạo/xóa, giúp phát triển tính năng mới hoặc thử nghiệm mà không ảnh hưởng đến nhánh chính.

- **An toàn**:

  - Dữ liệu và lịch sử thay đổi trong Git được bảo mật thông qua mã hóa, giúp tránh thất thoát hoặc chỉnh sửa trái phép.

- **Phổ biến và hỗ trợ mạnh mẽ**:

  - Nhiều nền tảng như GitHub, GitLab, Bitbucket tích hợp với Git, cung cấp thêm công cụ quản lý và chia sẻ dự án.

---

# 2. Git vs. GitHub: Sự khác biệt và mối liên hệ

## 2.1. Github là gì ?

- **GitHub** là một nền tảng lưu trữ mã nguồn dựa trên Git.
- Cho phép lưu trữ dự án trên đám mây để dễ dàng chia sẻ, hợp tác với các thành viên khác.
- **GitHub** cung cấp các tính năng bổ sung như quản lý dự án, báo cáo lỗi (issues), review mã nguồn (pull request), và tích hợp CI/CD.

## 2.2. Sự khác biệt

| **Số S.** | **Git**                                                              | **GitHub**                                                                          |
| --------- | -------------------------------------------------------------------- | ----------------------------------------------------------------------------------- |
| **1.**    | Git là một phần mềm.                                                 | GitHub là một dịch vụ.                                                              |
| **2.**    | Git là một công cụ dòng lệnh.                                        | GitHub là một giao diện người dùng đồ họa.                                          |
| **3.**    | Git được cài đặt cục bộ trên hệ thống.                               | GitHub được lưu trữ trên web.                                                       |
| **4.**    | Git được bảo trì bởi Linux.                                          | GitHub được Microsoft bảo trì.                                                      |
| **5.**    | Git tập trung vào kiểm soát phiên bản và chia sẻ mã.                 | GitHub tập trung vào việc lưu trữ mã nguồn tập trung.                               |
| **6.**    | Git là một hệ thống kiểm soát phiên bản để quản lý lịch sử mã nguồn. | GitHub là dịch vụ lưu trữ cho kho lưu trữ Git.                                      |
| **7.**    | Git được phát hành lần đầu tiên vào năm 2005.                        | GitHub được ra mắt vào năm 2008.                                                    |
| **8.**    | Git không có tính năng quản lý người dùng.                           | GitHub có tính năng quản lý người dùng tích hợp sẵn.                                |
| **9.**    | Git được cấp phép theo dạng mã nguồn mở.                             | GitHub bao gồm gói miễn phí và gói trả phí.                                         |
| **10.**   | Git có cấu hình công cụ bên ngoài tối thiểu.                         | GitHub có một thị trường tích hợp công cụ năng động.                                |
| **11.**   | Git cung cấp giao diện Desktop có tên là Git Gui.                    | GitHub cung cấp giao diện Desktop có tên là GitHub Desktop.                         |
| **12.**   | Git cạnh tranh với CVS, Subversion, Mercurial, v.v.                  | GitHub cạnh tranh với GitLab, Bitbucket, AWS Code Commit, Azure DevOps Server, v.v. |

## 2.3. Mối liên hệ

- **Git** là một phần mềm quản lý mã nguồn cho phép bạn lưu lại các snapshots của dự án, đồng thời hỗ trợ phân phối các thay đổi và chỉnh sửa qua thời gian.

- **GitHub** là một ứng dụng cung cấp nền tảng lưu trữ kho mã nguồn (repository) trên máy chủ từ xa, đồng thời tích hợp nhiều tính năng bổ sung như công khai dự án, cấp phép (licensing), và quản lý cộng tác viên (collaborators).

$\Rightarrow$ **Git** là "xương và thịt" của việc quản lý mã nguồn, cung cấp cốt lõi cho việc theo dõi và kiểm soát phiên bản. Trong khi đó, **GitHub** là công cụ giúp bạn làm việc với kho mã nguồn một cách dễ dàng và thuận tiện hơn nhờ giao diện và các tính năng hỗ trợ.

---

## 3. Cài đặt

### 3.1. Cài đặt Git và tạo tài khoản GitHub

#### 3.1.1. Cài đặt Git

**Bước 1: Tải xuống Git**

- Trang web chính thức dành cho Git: [https://git-scm.com/](https://git-scm.com/)
- Nhấn nút Download để tải phiên bản phù hợp với hệ điều hành của bạn (Windows, macOS, hoặc Linux).
<p align="center">
  <a href="https://git-scm.com/downloads/win" style="text-decoration: none; display: inline-block; background-color: #4CAF50; color: white; padding: 10px 20px; border: none; border-radius: 5px; cursor: pointer; margin-right: 10px;">Windows</a>
  <a href="https://git-scm.com/downloads/mac" style="text-decoration: none; display: inline-block; background-color: #008CBA; color: white; padding: 10px 20px; border: none; border-radius: 5px; cursor: pointer; margin-right: 10px;">macOS</a>
  <a href="https://git-scm.com/downloads/linux" style="text-decoration: none; display: inline-block; background-color: #f44336; color: white; padding: 10px 20px; border: none; border-radius: 5px; cursor: pointer;">Linux/Unix</a>
</p>

**Bước 2: Cài đặt Git trên máy tính**
a) Đối với Windows:

1. Mở tệp cài đặt đã tải về (đuôi .exe).
2. Trong cửa sổ cài đặt:

- Chọn các thành phần mặc định (hoặc tùy chỉnh theo nhu cầu của bạn).
- Ở bước "Adjusting your PATH environment," chọn Git from the command line and also from 3rd-party software.

4. Tiếp tục nhấn Next cho đến khi hoàn tất.
5. Sau khi cài đặt xong, mở Git Bash để kiểm tra.

b) Đối với macOS:

1. Cài đặt Git thông qua Homebrew (nếu chưa cài đặt Homebrew, bạn cần cài trước):

```bash
brew install git
```

2. Kiểm tra phiên bản Git đã cài đặt bằng lệnh:

```bash
git --version
```

c) Đối với Linux:

1. Mở terminal và chạy lệnh cài đặt phù hợp với bản phân phối Linux của bạn:

- Ubuntu/Debian:
  ```bash
    sudo apt update
    sudo apt install git
  ```
- Fedora:
  ```bash
    sudo dnf install git
  ```
- Arch Linux:
  ```bash
    sudo pacman -S git
  ```

2. Kiểm tra phiên bản Git bằng lệnh:

```bash
git --version
```

**Bước 3: Cấu hình Git**

1. Mở terminal hoặc Git Bash và thiết lập tên người dùng:

```bash
git config --global user.name "Tên của bạn"
```

2. Thiết lập Email:

```bash
git config --global user.email "email@cuaban.com"
```

3. Kiểm tra cấu hình:

```bash
git config --list
```

4. Kiểm tra xem Git đã hoạt động:

```bash
git --version
```

#### 3.1.2. Tạo tài khoản GitHub

**Bước 1: Truy cập Github**

- Mở trình duyệt và truy cập vào trang web chính thức của GitHub: [https://github.com/](https://github.com/)

**Bước 2: Đăng ký tài khoản**

- Tại trang chủ GitHub, bạn sẽ thấy nút Sign up. Nhấp vào nút này để bắt đầu quá trình đăng ký.

**Bước 3: Nhập thông tin tài khoản**

- Username: Nhập tên người dùng bạn muốn sử dụng trên GitHub. Đây sẽ là tên duy nhất của bạn trên GitHub.
- Email address: Nhập địa chỉ email mà bạn muốn liên kết với tài khoản GitHub.
- Password: Nhập mật khẩu mạnh cho tài khoản của bạn. Hãy chắc chắn rằng mật khẩu có ít nhất 15 ký tự và bao gồm cả chữ hoa, chữ thường, số và ký tự đặc biệt để bảo mật tốt hơn.

**Bước 4: Xác minh tài khoản**

- GitHub sẽ yêu cầu bạn giải quyết một bài kiểm tra bảo mật để chứng minh bạn không phải là bot (ví dụ: chọn các hình ảnh có một đối tượng cụ thể).
- Sau khi vượt qua kiểm tra bảo mật, nhấn Continue.

**Bước 5: Chọn kế hoạch**

- GitHub cung cấp các kế hoạch miễn phí và trả phí. Bạn có thể chọn Free để sử dụng GitHub miễn phí.
- Nhấn Continue.

**Bước 6: Cấu hình tài khoản**

- GitHub sẽ yêu cầu bạn trả lời một vài câu hỏi để tùy chỉnh tài khoản của bạn, chẳng hạn như mục đích sử dụng GitHub (ví dụ: học tập, cá nhân, công việc).
- Bạn có thể bỏ qua các câu hỏi này hoặc trả lời tùy thích.

**Bước 7: Xác nhận Email**

- Sau khi đăng ký, GitHub sẽ gửi một email xác nhận đến địa chỉ email bạn đã cung cấp.
- Mở email và nhấp vào liên kết xác nhận để hoàn tất quá trình đăng ký.

## 3.2. Kết nối Git và GitHub thông qua giao thức SSH

(cập nhật sau)

---
