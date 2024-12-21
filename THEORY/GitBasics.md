# PHẦN 3: GIT CƠ BẢN

---

# 1. Git Cheatsheet

## 1.1. Getting & Creating Projects

| Command                                                           | Description                                |
| ----------------------------------------------------------------- | ------------------------------------------ |
| `git init`                                                        | Initialize a local Git repository          |
| `git clone ssh://git@github.com/[username]/[repository-name].git` | Create a local copy of a remote repository |

## 1.2. Basic Snapshotting

| Command                            | Description                                                           |
| ---------------------------------- | --------------------------------------------------------------------- |
| `git status`                       | Check status                                                          |
| `git add [file-name.txt]`          | Add a file to the staging area                                        |
| `git add -A`                       | Add all new and changed files to the staging area                     |
| `git commit -m "[commit message]"` | Commit changes                                                        |
| `git rm -r [file-name.txt]`        | Remove a file (or folder)                                             |
| `git remote -v`                    | View the remote repository of the currently working file or directory |

## 1.3. Branching & Merging

| Command                                              | Description                                             |
| ---------------------------------------------------- | ------------------------------------------------------- |
| `git branch`                                         | List branches (the asterisk denotes the current branch) |
| `git branch -a`                                      | List all branches (local and remote)                    |
| `git branch [branch name]`                           | Create a new branch                                     |
| `git branch -d [branch name]`                        | Delete a branch                                         |
| `git push origin --delete [branch name]`             | Delete a remote branch                                  |
| `git checkout -b [branch name]`                      | Create a new branch and switch to it                    |
| `git checkout -b [branch name] origin/[branch name]` | Clone a remote branch and switch to it                  |
| `git branch -m [old branch name] [new branch name]`  | Rename a local branch                                   |
| `git checkout [branch name]`                         | Switch to a branch                                      |
| `git checkout -`                                     | Switch to the branch last checked out                   |
| `git checkout -- [file-name.txt]`                    | Discard changes to a file                               |
| `git merge [branch name]`                            | Merge a branch into the active branch                   |
| `git merge [source branch] [target branch]`          | Merge a branch into a target branch                     |
| `git stash`                                          | Stash changes in a dirty working directory              |
| `git stash clear`                                    | Remove all stashed entries                              |
| `git stash pop`                                      | Apply latest stash to working directory                 |

## 1.4. Sharing & Updating Projects

| Command                                                                           | Description                                                 |
| --------------------------------------------------------------------------------- | ----------------------------------------------------------- |
| `git push origin [branch name]`                                                   | Push a branch to your remote repository                     |
| `git push -u origin [branch name]`                                                | Push changes to remote repository (and remember the branch) |
| `git push`                                                                        | Push changes to remote repository (remembered branch)       |
| `git push origin --delete [branch name]`                                          | Delete a remote branch                                      |
| `git pull`                                                                        | Update local repository to the newest commit                |
| `git pull origin [branch name]`                                                   | Pull changes from remote repository                         |
| `git remote add origin ssh://git@github.com/[username]/[repository-name].git`     | Add a remote repository                                     |
| `git remote set-url origin ssh://git@github.com/[username]/[repository-name].git` | Set a repository's origin branch to SSH                     |

## 1.5. Inspection & Comparison

| Command                                    | Description                    |
| ------------------------------------------ | ------------------------------ |
| `git log`                                  | View changes                   |
| `git log --summary`                        | View changes (detailed)        |
| `git log --oneline`                        | View changes (briefly)         |
| `git diff [source branch] [target branch]` | Preview changes before merging |

---

# 2. Git Workflow

## 2.1. Repository

**Repositories**, thường được gọi là ‘_repos_’, là nơi lưu trữ toàn bộ lịch sử và kiểm soát phiên bản của một dự án.

**Lưu trữ:**

- Repositories có thể được lưu trữ cục bộ trên máy tính hoặc trên một máy chủ chia sẻ, chẳng hạn như GitHub.
- Phần lớn repositories thường được lưu trữ trên GitHub, nơi các cộng tác viên chính sẽ tạo bản sao của repository trên máy của họ và cập nhật repository thông qua hệ thống push/pull.

**Kho từ xa (Remote Repository):**

- Bất kỳ repository nào không được lưu trữ cục bộ trên máy tính đều được gọi là ‘_remote repository_’.

## 2.2. Repos vs. Directories

**Repositories** và **directories** có sự khác biệt quan trọng:

- **_Repositories_**:
  - Là một dòng thời gian lưu giữ toàn bộ lịch sử của dự án, bao gồm tất cả các thay đổi được thực hiện.
  - Repositories chứa các bản ghi chi tiết về cách dự án phát triển qua thời gian.
- **_Directories (Working Directories)_**:
  - Là trạng thái hiện tại của dự án tại một thời điểm cụ thể.
  - Bất kỳ thư mục cục bộ nào liên kết và làm việc với một repository đều có thể được xem là một repository. Tuy nhiên, để dễ phân biệt, chúng thường được gọi là ‘_local repositories_’, vì chúng là phiên bản cục bộ của một repository từ xa.

## 2.3. Workflow Diagram

Biểu đồ workflow minh họa cách thức hoạt động cơ bản của quy trình Git.

![Git Workflow Diagram](../Images/git-workflow.png)

**Khu vực staging (Staging Area):**

- Đây là nơi tập hợp tất cả các thay đổi đã thực hiện trên dự án mà bạn muốn ghi nhận (commit).
- Staging area giống như một bản nháp, cho phép bạn lựa chọn thay đổi nào sẽ được đưa vào lịch sử của repository.

**Commit:**

- Hành động commit giống như chụp một ảnh chụp nhanh (snapshot) của trạng thái hiện tại của dự án, và lưu lại nó trên một dòng thời gian.
- Mỗi commit là một bước phát triển của dự án, giúp dễ dàng quay lại hoặc kiểm tra lịch sử thay đổi khi cần.

Workflow trong Git thường bao gồm ba bước chính:

1. Làm việc trên Working Directory – Bạn thực hiện các thay đổi trong dự án.
2. Thêm vào Staging Area – Bạn chọn các thay đổi để ghi nhận.
3. Commit – Lưu trạng thái hiện tại vào lịch sử repository.

Workflow này giúp bạn quản lý và theo dõi tiến trình làm việc của dự án một cách rõ ràng và có tổ chức.

---

# 3. Tạo một Repository mới

Dưới đây là các bước chi tiết để tạo một repository mới sử dụng Git:

## 3.1. Khởi tạo Local Repository

**Local Repository** là nơi lưu trữ dự án trên máy tính của bạn. Làm theo các bước sau:

1. **Tạo một thư mục cho dự án:**
   - Mở Git Bash (hoặc terminal / command prompt).
   - Tạo một thư mục mới và điều hướng đến thư mục đó:
     ```bash
     mrdir prj_name
     cd prj_name
     ```
2. **Khởi tạo Git trong thư mục:**
   - Chạy lệnh sau để biến thư mục hiện tại thành một repository Git:
     ```bash
     git init
     ```
   - Git sẽ tạo một thư mục ẩn `.git`, nơi lưu trữ dữ liệu và lịch sử của repository.

## 3.2. Thêm Tệp vào Repository

1. Tạo hoặc sao chép tệp vào thư mục làm việc:

   - Bạn có thể tạo một tệp mới (ví dụ: `README.md`) hoặc sao chép các tệp hiện có vào thư mục này.

2. Thêm tệp vào Staging Area:

   - Sử dụng lệnh sau để thêm một tệp cụ thể:
     ```bash
     git add file_name
     ```
   - Hoặc thêm tất cả các tệp:
     ```bash
     git add -A
     ```

3. Lưu trạng thái đầu tiên của dự án (Commit):
   - Ghi lại trang thái đầu tiên của dự án:
     ```bash
     git commit -m "Initial commit"
     ```

## 3.3. Tạo Remote Repository

**Remote Repository** là nơi bạn lưu trữ dự án trực tuyến, giúp bạn dễ dàng chia sẻ và làm việc nhóm.

1. **Đăng nhập vào GitHub (hoặc nền tảng khác):**

- Truy cập [GitHub](https://github.com/) và đăng nhập tài khoản.

2. **Tạo repository mới trên GitHub:**

- Nhấp vào nút `New repository`.
- Điền thông tin:
  - `Repository name`: Tên repository (ví dụ: `ten-du-an`).
  - `Description`: Mô tả ngắn gọn về dự án (tuỳ chọn).
  - `Visibility`: Chọn Public (công khai) hoặc Private (riêng tư).
- Nhấn `Create repository`.

## 3.4. Kết nối Local Reposiroty và Remote Repository

1. Đổi tên nhánh chính thành `main`:

   - Trong Git, nhánh mặc định khi khởi tạo mới sẽ là `master`. Tuy nhiên, GitHub và nhiều nền tảng khác hiện nay khuyến khích sử dụng nhánh `main` thay vì `master`.

   - Sau khi bạn đã khởi tạo repository và thực hiện commit lần đầu, nếu nhánh của bạn vẫn là `master`, bạn có thể đổi tên nhánh mặc định này thành `main` để đồng bộ với GitHub.

   - Lệnh đổi tên nhánh:
     ```bash
     git branch -M main
     ```
   - Lệnh tự động đặt nhánh mặc định là `main` cho các repo mới:
     ```bash
     git config --global init.defaultBranch main
     ```

2. Kết nối Local repository và Remote repository
   - Sao chép URL Remote repository (dạng SSH hoặc HTTPS)
   - Thêm URL này làm remote origin:
     ```bash
     git remote add origin <URL-repository>
     ```
   - Thay <URL-repository> bằng URL thực tế của repository trên GitHub (ví dụ: git@github.com:username/ten-du-an.git).
3. Đẩy nội dung lên Remote repository
   - Đẩy commit đầu tiên lên GitHub:
   ```bash
   git push -u origin main
   ```
   - `origin`: Là tên mặc định của remote repository.
   - Nếu nhánh chính không phải `main`, thay đổi `main` thành tên nhánh của bạn.

## 3.5. Xác minh kết nối thành công

1. Kiểm tra Remote repository
   - Để xác minh remote repository đã được kết nối đúng, chạy lệnh sau:
     ```bash
     git remote -v
     ```
   - Kết quả sẽ hiển thị URL của remote repository mà bạn đã thêm vào.
2. Kiểm tra nội dung trên GitHub:
   - Truy cập lại repository trên GitHub và kiểm tra xem các tệp đã được đẩy lên hay chưa.

## 3.6. Tóm tắt các lệnh chính để tạo Repository mới

```bash
# Tạo thư mục dự án và điều hướng vào thư mục đó
mkdir prj_name
cd prj_name

# Khởi tạo Git repository
git init

# Thêm tất cả các tệp vào staging area
git add -A

# Commit lần đầu
git commit -m "Initial commit"

# Đổi tên nhánh mặc định thành 'main'
git branch -M main

# Thêm remote repository
git remote add origin <URL-repository>

# Đẩy dữ liệu lên GitHub (remote repository)
git push -u origin main

# Kiểm tra remote repository
git remote -v
```

---

# 4. Git Checkout

Lệnh `git checkout` trong Git là một công cụ rất mạnh mẽ và linh hoạt được sử dụng để thay đổi các nhánh hoặc khôi phục các tệp. Dưới đây là các tình huống và cách sử dụng phổ biến của lệnh này:

## 4.1. Chuyển đổi giữa các nhánh (branch)

Lệnh `git checkout` thường được sử dụng để chuyển đổi giữa các nhánh trong repository.

**Cách sử dụng:**

```bash
git checkout branch_name
```

**Ví dụ:** Nếu bạn muốn chuyển sang nhánh `feature-1`, bạn sẽ chạy lệnh:

```bash
git checkout feature-1
```

**Lưu ý:** Khi chuyển nhánh, Git sẽ cập nhật `thư mục làm việc (working directory)` để phản ánh trạng thái của nhánh mà bạn chuyển đến. Nếu có thay đổi chưa commit trên nhánh hiện tại, bạn sẽ cần phải `commit` hoặc `stash` các thay đổi đó trước khi chuyển nhánh.

## 4.2. Tạo và chuyển đến nhánh mới

Bạn có thể tạo một nhánh mới và ngay lập tức chuyển sang nhánh đó bằng cách sử dụng tham số `-b` với lệnh `git checkout`.

**Cách sử dụng:**

```bash
git checkout -b new_branch_name
```

**Ví dụ:** Để tạo một nhánh mới có tên `feature-2` và chuyển sang nhánh đó, bạn sẽ chạy:

```bash
git checkout -b feature-2
```

**Lưu ý:** `git checkout -b new_branch_name` sẽ tạo nhánh mới từ nhánh hiện tại và chuyển đến nhánh mới ngay lập tức.

## 4.3. Khôi phục các tệp từ một nhánh hoặc commit cũ

Lệnh `git checkout` cũng có thể được sử dụng để khôi phục lại một tệp cụ thể từ một nhánh khác hoặc một commit cũ, giúp bạn thay đổi trạng thái của một tệp mà không cần phải chuyển nhánh.

**Cách sử dụng:**

```bash
git checkout commit_hash -- file_path
```

**Ví dụ:** Nếu bạn muốn khôi phục tệp `README.md` từ commit có mã hash `abc123`, bạn sẽ chạy:

```bash
git checkout abc123 -- README.md
```

**Lưu ý:** Lệnh này chỉ thay đổi tệp trong thư mục làm việc mà không ảnh hưởng đến các commit hoặc nhánh khác. Nếu bạn muốn lưu những thay đổi này, bạn sẽ cần phải commit.

## 4.4. Quay lại trạng thái của một commit cũ

Bạn có thể sử dụng `git checkout` để di chuyển `HEAD` (con trỏ hiện tại) về một commit cũ mà không thay đổi nhánh hiện tại. Điều này giúp bạn có thể kiểm tra trạng thái của repository tại một thời điểm cụ thể trong lịch sử commit.

**Cách sử dụng:**

```bash
git checkout commit_hash
```

**Ví dụ:**

```bash
git checkout abc123
```

**Lưu ý:** Khi bạn sử dụng git checkout với một commit cũ, bạn sẽ rơi vào trạng thái "`detached HEAD`". Điều này có nghĩa là bạn không còn làm việc trên một nhánh cụ thể. Nếu bạn thực hiện các thay đổi và commit trong trạng thái này, bạn sẽ phải tạo một nhánh mới từ đó để lưu lại các thay đổi này.

## 4.5. Huỷ bỏ các thay đổi trong tệp

Lệnh `git checkout` cũng có thể được sử dụng để hủy bỏ các thay đổi trong một tệp và khôi phục lại tệp đó như trong commit cuối cùng.

**Cách sử dụng:**

```bash
git checkout -- file_path
```

**Ví dụ:** Nếu bạn muốn hủy bỏ các thay đổi trong tệp `example.txt`, bạn sẽ chạy:

```bash
git checkout -- example.txt
```

**Lưu ý:** Lệnh này chỉ hủy bỏ các thay đổi trong thư mục làm việc, không làm ảnh hưởng đến lịch sử commit. Nếu bạn đã commit các thay đổi này, bạn sẽ phải sử dụng các lệnh khác như `git revert` để hoàn tác commit.

## 4.6. Lưu ý quan trọng

- Trước khi sử dụng `git checkout` để chuyển nhánh hoặc khôi phục tệp, đảm bảo rằng bạn đã commit hoặc lưu lại các thay đổi quan trọng để tránh mất dữ liệu.
- Git đã thay thế một số chức năng của `git checkout` bằng lệnh mới như `git switch` (cho việc chuyển nhánh) và `git restore` (cho việc khôi phục tệp), vì vậy bạn có thể sử dụng những lệnh này nếu bạn muốn một cách tiếp cận rõ ràng hơn.
  - Chuyển nhánh: `git switch branch_name`
  - Khôi phục tệp: `git restore file_path`

---

# 5. Git Revert & Reset

`git revert` và `git reset` là hai lệnh quan trọng trong Git, thường được sử dụng để hoàn tác các thay đổi. Tuy nhiên, chúng hoạt động theo những cách khác nhau và có những tác dụng riêng biệt đối với lịch sử commit và thư mục làm việc.

## 5.1. `git revert`

Lệnh `git revert` được sử dụng để tạo ra một commit mới, đảo ngược tác động của một commit trước đó. Điều này có nghĩa là thay vì xóa bỏ commit cũ, `git revert` sẽ tạo một commit mới với những thay đổi ngược lại để "hoàn tác" commit trước đó.

1. **Mục đích sử dụng:** `git revert` rất hữu ích khi bạn muốn hoàn tác các thay đổi mà không làm thay đổi lịch sử commit. Điều này đặc biệt quan trọng khi làm việc trong các dự án nhóm hoặc khi bạn đã đẩy commit lên remote repository và không muốn thay đổi lịch sử đã được chia sẻ.

2. **Cách sử dụng:**

   ```bash
   git revert commit_hash
   ```

   Ví dụ: Nếu bạn muốn hoàn tác commit có mã hash là abc123, bạn sẽ sử dụng:

   ```bash
   git revert abc123
   ```

3. **Hoạt động:**

- Git sẽ tạo ra một commit mới thay thế các thay đổi của commit cũ, nhưng lịch sử commit ban đầu vẫn được giữ lại.
- Điều này giữ cho lịch sử commit của bạn sạch sẽ và không gây ảnh hưởng đến các commit khác.

4. **Lưu ý:**

- Sau khi chạy git revert, Git sẽ mở trình soạn thảo văn bản để bạn nhập thông điệp cho commit mới. Bạn có thể thay đổi thông điệp này nếu cần, sau đó lưu và thoát trình soạn thảo.

## 5.2. `git reset`

Lệnh `git reset` được sử dụng để "quay lại" một trạng thái trước đó trong lịch sử commit của repository. Nó có thể ảnh hưởng đến chỉ mục (staging area) và thư mục làm việc, giúp bạn bỏ qua các commit mà bạn không muốn nữa.

Có ba chế độ chính của git reset: `soft`, `mixed`, và `hard`.

### 5.2.1. `git reset --soft`

Lệnh này di chuyển HEAD (con trỏ hiện tại) về một commit cụ thể, nhưng giữ lại tất cả các thay đổi trong staging area. Điều này có nghĩa là các thay đổi của bạn vẫn còn trong trạng thái chuẩn bị để commit lại.

1. **Cách sử dụng:**

   ```bash
   git reset --soft commit_hash
   ```

2. **Hoạt động:** HEAD sẽ di chuyển đến commit đã chỉ định, và các thay đổi sau commit đó sẽ vẫn còn trong staging area, sẵn sàng để bạn commit lại.

### 5.2.2. `git reset --mixed`

Lệnh này di chuyển HEAD về một commit cụ thể và cũng hủy bỏ các thay đổi trong staging area, nhưng các thay đổi trong thư mục làm việc (working directory) sẽ được giữ lại. Bạn sẽ cần phải thêm lại các thay đổi vào staging area nếu muốn commit lại.

1. **Cách sử dụng:**

   ```bash
   git reset --mixed commit_hash
   ```

2. **Hoạt động:** HEAD sẽ di chuyển đến commit chỉ định và các thay đổi sau commit đó sẽ bị loại bỏ khỏi staging area, nhưng sẽ vẫn còn trong thư mục làm việc (working directory).

### 5.2.3. `git reset --hard`

Lệnh này là lệnh mạnh mẽ nhất. Nó sẽ di chuyển HEAD về một commit cụ thể và hủy bỏ tất cả các thay đổi trong cả staging area và thư mục làm việc. Tất cả các thay đổi sau commit đó sẽ bị xóa bỏ vĩnh viễn, không thể phục hồi nếu không có backup.

1. **Cách sử dụng:**

   ```bash
   git reset --hard commit_hash
   ```

2. **Hoạt động:** HEAD sẽ di chuyển đến commit chỉ định và tất cả các thay đổi trong staging area và thư mục làm việc sẽ bị xóa. Điều này rất hữu ích nếu bạn muốn hoàn toàn quay lại trạng thái của một commit cũ và không giữ lại bất kỳ thay đổi nào.

3. **Lưu ý:** Dùng git reset --hard cẩn thận, vì các thay đổi trong thư mục làm việc sẽ bị mất vĩnh viễn nếu bạn chưa commit hoặc chưa lưu lại.

## 5.3. So sánh giữa `git revert` và `git reset`

| Tính năng                      | `git revert`                                                         | `git reset`                                                                    |
| ------------------------------ | -------------------------------------------------------------------- | ------------------------------------------------------------------------------ |
| Tác động đến lịch sử           | Tạo commit mới đảo ngược một commit cũ, giữ nguyên lịch sử commit.   | Di chuyển HEAD, thay đổi staging area và working directory                     |
| Sử dụng cho lịch sử công khai  | An toàn khi làm việc với lịch sử công khai (trong nhóm hoặc remote). | Thường không an toàn cho lịch sử công khai, có thể gây xung đột.               |
| Tác động đến staging area      | Không thay đổi staging area.                                         | Có thể thay đổi staging area tùy thuộc vào tùy chọn (`soft`, `mixed`, `hard`). |
| Tác động đến working directory | Không thay đổi working directory                                     | Có thể thay đổi working directory tuỳ thuộc vào tuỳ chọn                       |
| Khôi phục các thay đổi         | Tạo một commit mới để hoàn tác thay đổi.                             | Thay đổi trực tiếp lịch sử commit và trạng thái của các thay đổi.              |

## 5.4. Khi nào nên dùng `git revert` và `git reset`

1. `git revert`:

- Khi bạn muốn hoàn tác một commit nhưng vẫn muốn giữ nguyên lịch sử commit của bạn.
- Khi bạn đã đẩy commit lên remote và không muốn thay đổi lịch sử chung của dự án.

2. `git reset`:

- Khi bạn muốn hủy bỏ các commit gần đây và quay lại trạng thái trước đó trong lịch sử của dự án.
- Khi bạn chưa đẩy commit lên remote và muốn chỉnh sửa lịch sử trước khi chia sẻ với người khác.

---

# 6. Tạo và sử dụng `.gitignore`

`.gitignore` là một tệp đặc biệt trong Git dùng để chỉ định các tệp và thư mục mà bạn không muốn Git theo dõi và đưa vào trong lịch sử commit của repository. Việc sử dụng .gitignore giúp bạn loại bỏ các tệp tạm, tệp nhị phân, hoặc các tệp cấu hình cụ thể mà không cần thiết phải chia sẻ trong repository.

## 6.1. Cấu trúc tệp `.gitignore`

Tệp `.gitignore` chứa danh sách các mẫu (patterns) về các tệp và thư mục mà Git sẽ bỏ qua. Tệp này có thể đặt ở bất kỳ vị trí nào trong thư mục của dự án, nhưng thường sẽ đặt ở thư mục gốc của repository (nơi chứa thư mục `.git`).

**Cấu trúc cơ bản của `.gitignore`:**

- Các tệp và thư mục cần loại bỏ:
  ```bash
  /node_modules/
  *.log
  *.bak
  .DS_Store
  ```
  trong đó:
  - `/node_modules/`: Loại bỏ thư mục `node_modules` (thư mục chứa các gói phụ thuộc khi làm việc với Node.js)
  - `*.log`: Loại bỏ các tệp có phần mở rộng `.log`
  - `.DS_Store`: Loại bỏ tệp `.DS_Store` (tệp hệ thống của macOS)
- Các tệp hoặc thư mục không cần phải loại bỏ: Bạn có thể sử dụng dấu chấm than (`!`) để chỉ định các tệp hoặc thư mục mặc dù đã được đưa vào `.gitignore`, nhưng bạn vẫn muốn theo dõi chúng.
  ```bash
  !important-file.txt
  ```

## 6.2. Tạo tệp `.gitignore`

Để tạo một tệp .gitignore mới trong repository Git của bạn, làm theo các bước sau:

1. **Tạo tệp `.gitignore`:**

   - Mở Git Bash (hoặc terminal).
   - Điều hướng đến thư mục dự án của bạn.
   - Tạo tệp .gitignore:
     ```bash
     touch .gitignore
     ```
   - Nếu bạn đã có tệp .gitignore, bạn chỉ cần mở nó bằng một trình soạn thảo văn bản.

2. **Chỉnh sửa `.gitignore`:**

   - Mở tệp .gitignore bằng trình soạn thảo văn bản (ví dụ: nano .gitignore, vi .gitignore, hoặc mở bằng bất kỳ trình soạn thảo nào bạn ưa thích).
   - Thêm các mẫu (patterns) cần loại bỏ vào tệp .gitignore. Ví dụ:

     ```bash
     # Node modules
     /node_modules/

     # Tệp log
     *.log

     # Tệp cấu hình của IDE (Visual Studio Code)
     .vscode/

     # Tệp hệ thống của macOS
     .DS_Store
     ```

3. **Lưu và đóng tệp `.gitignore`.**

## 6.3. Một số quy tắc cơ bản trong `.gitignore`

- **Sử dụng dấu chấm than (`!`) để ngoại lệ**: Để không bỏ qua một tệp hoặc thư mục đã được đưa vào `.gitignore`, bạn có thể sử dụng dấu chấm than.

  ```bash
  *.log         # Loại bỏ tất cả tệp .log
  !important.log # Không loại bỏ tệp important.log
  ```

- **Dùng dấu hoa thị (`*`) để đại diện cho các ký tự**: Bạn có thể sử dụng dấu sao (`*`) để đại diện cho bất kỳ chuỗi nào.

  ```bash
  *.txt   # Loại bỏ tất cả các tệp .txt
  *.bak   # Loại bỏ tất cả các tệp .bak
  ```

- **Bỏ qua toàn bộ thư mục**: Nếu bạn muốn bỏ qua toàn bộ một thư mục, bạn có thể chỉ ra tên thư mục đó với dấu gạch chéo `/` ở cuối.

  ```bash
  /build/   # Loại bỏ thư mục build/
  /dist/    # Loại bỏ thư mục dist/
  ```

- **Chỉ định các tệp ẩn**: Tệp ẩn trong Git có thể được chỉ định bằng cách thêm dấu chấm `.` ở đầu tên tệp.
  ```bash
  .env      # Loại bỏ tệp .env
  .gitignore # Loại bỏ tệp .gitignore (nếu bạn không muốn theo dõi tệp này)
  ```

## 6.4. Kiểm tra tệp `.gitignore` hoạt động

Sau khi tạo tệp `.gitignore`, bạn có thể kiểm tra xem các tệp có bị loại bỏ khỏi Git hay không. Nếu bạn đã thêm tệp vào staging area và sau đó thêm nó vào `.gitignore`, Git vẫn sẽ theo dõi tệp đó.

Để loại bỏ các tệp đã được thêm vào staging area nhưng muốn loại bỏ theo `.gitignore`, bạn cần sử dụng lệnh sau:

```bash
git rm --cached file_name
```

Ví dụ:

```bash
git rm --cached node_modules/
git commit -m "Loại bỏ node_modules khỏi Git"
```

## 6.5. Các nền tảng Git Hosting và `.gitignore`

GitHub, GitLab, và Bitbucket cung cấp các tệp `.gitignore` mẫu cho nhiều loại dự án khác nhau. Bạn có thể truy cập vào các mẫu `.gitignore` này trên các nền tảng đó hoặc tìm trên GitHub Gist các file mẫu có sẵn.

- GitHub `.gitignore` templates: [GitHub .gitignore](https://github.com/github/gitignore)

## 6.6. Lưu ý quan trọng

Tệp `.gitignore` chỉ ảnh hưởng đến các tệp chưa được theo dõi: Nếu một tệp đã được Git theo dõi (đã được commit trước đó), nó sẽ không bị ảnh hưởng bởi `.gitignore`. Để Git ngừng theo dõi tệp, bạn cần sử dụng `git rm --cached`.

Thứ tự quan trọng trong `.gitignore`: Các dòng trong tệp `.gitignore` được áp dụng theo thứ tự từ trên xuống. Điều này có nghĩa là nếu bạn loại bỏ một thư mục và sau đó đưa tệp trong thư mục đó vào danh sách ngoại lệ, tệp đó sẽ không bị loại bỏ.
