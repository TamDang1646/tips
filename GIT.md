# 10 Useful New Git Commands to Enhance Your Git Skills

Here are 10 useful new Git commands that you should start using to enhance your Git skills.

1. **git switch - Switch Branches**
    Before Git 2.23, `git checkout` was the main command for switching branches, but it did many other things as well. This could be confusing when you just wanted to switch branches without changing anything else. Git 2.23 introduced `git switch` as a safer and clearer option for switching branches.
    ```sh
    # Switch to another branch
    git switch feature-branch
    # Create and switch to a new branch
    git switch -c new-branch
    ```

2. **git restore - Undo Changes**
    Previously, undoing changes often used `git checkout` or `git reset`, but both of these commands could change the branch state if not careful. Git 2.23 introduced `git restore`, which helps undo changes without affecting the current branch.
    ```sh
    # Discard changes in the working directory
    git restore main.js
    # Unstage changes
    git restore --staged main.js
    ```

3. **git maintenance - Automate Repo Maintenance**
    As repos grow larger, performance can degrade. Git 2.29 introduced `git maintenance` to automate repo maintenance tasks like cleanup and optimization.
    ```sh
    # Enable automatic maintenance
    git maintenance start
    # Run maintenance tasks immediately
    git maintenance run
    ```

4. **git sparse-checkout - Efficiently Manage Large Repos**
    If you work with large monorepos, `git sparse-checkout` helps you only load the necessary directories or files, saving time and disk space.
    ```sh
    # Enable sparse-checkout mode
    git sparse-checkout init
    # Only fetch specific directories
    git sparse-checkout set services/ docs/
    ```

5. **git log --remerge-diff - Better Understand Merges**
    When merging, `git log` usually only shows which branches were merged, but doesn't clearly explain the changes added. `git log --remerge-diff` helps you understand the specific changes during the merge.
    ```sh
    git log --remerge-diff
    ```

6. **git blame --ignore-rev - Ignore Noisy Commits**
    When the team makes bulk formatting changes, `git blame` becomes less useful as every line points to the formatting commit instead of the original author. `--ignore-rev` helps you ignore these noisy commits.
    ```sh
    git blame --ignore-rev commit-hash
    # Add commit hash to ignore-revs file
    echo commit-hash >> .git-blame-ignore-revs
    # Tell Git to use this file
    git config blame.ignoreRevsFile .git-blame-ignore-revs
    ```

7. **git range-diff - Compare and Track Changes Between Commit Ranges**
    If you are working with rebase or cherry-pick, `git range-diff` helps you compare two commit ranges and show the differences between them.
    ```sh
    git range-diff
    ```

8. **git worktree - Work with Multiple Branches Simultaneously**
    If you need to work on multiple branches without constantly switching between them, `git worktree` allows you to create multiple working directories for each branch.
    ```sh
    # Add a new worktree for a specific branch
    git worktree add ../feature-branch feature-branch
    # Remove a worktree when done
    git worktree remove ../feature-branch
    ```

9. **git rebase --update-refs - Keep References in Sync**
    When performing a rebase, Git replaces old commits with new ones, often leaving branch pointers or tags referencing outdated commits. Git 2.38 introduced the `--update-refs` option to automatically handle this issue.
    ```sh
    git rebase --update-refs
    # Configure git rebase to always update specific references
    git config rebase.updateRefs true
    ```

10. **git commit --fixup and git rebase --autosquash - Fix Commits**
     When you need to fix a previous commit, `git commit --fixup` and `git rebase --autosquash` help you automatically edit and squash commits without manual intervention.
     ```sh
     # Create a fixup commit targeting a specific commit
     git commit --fixup=<commit-hash>
     # Then, during interactive rebase, automatically squash fixup commits
     git rebase -i --autosquash <base-branch>
     ```

# 10 Lệnh Git Mới Hữu Ích Để Nâng Cao Kỹ Năng Git Của Bạn

Dưới đây là 10 lệnh Git mới hữu ích mà bạn nên bắt đầu sử dụng để nâng cao kỹ năng Git của mình.

1. **git switch - Chuyển Nhánh**
    Trước Git 2.23, `git checkout` là lệnh chính để chuyển nhánh, nhưng nó còn làm nhiều việc khác. Điều này có thể gây nhầm lẫn khi bạn chỉ muốn chuyển nhánh mà không thay đổi gì khác. Git 2.23 đã giới thiệu `git switch` như một tùy chọn an toàn và rõ ràng hơn để chuyển nhánh.
    ```sh
    # Chuyển sang nhánh khác
    git switch feature-branch
    # Tạo và chuyển sang nhánh mới
    git switch -c new-branch
    ```

2. **git restore - Hoàn Tác Thay Đổi**
    Trước đây, việc hoàn tác thay đổi thường sử dụng `git checkout` hoặc `git reset`, nhưng cả hai lệnh này có thể thay đổi trạng thái nhánh nếu không cẩn thận. Git 2.23 đã giới thiệu `git restore`, giúp hoàn tác thay đổi mà không ảnh hưởng đến nhánh hiện tại.
    ```sh
    # Loại bỏ thay đổi trong thư mục làm việc
    git restore main.js
    # Hủy bỏ thay đổi đã được staged
    git restore --staged main.js
    ```

3. **git maintenance - Tự Động Bảo Trì Repo**
    Khi các repo lớn dần, hiệu suất có thể giảm. Git 2.29 đã giới thiệu `git maintenance` để tự động hóa các tác vụ bảo trì repo như dọn dẹp và tối ưu hóa.
    ```sh
    # Bật bảo trì tự động
    git maintenance start
    # Chạy các tác vụ dọn dẹp ngay lập tức
    git maintenance run
    ```

4. **git sparse-checkout - Quản Lý Repo Lớn Hiệu Quả**
    Nếu bạn làm việc với các monorepo lớn, `git sparse-checkout` giúp bạn chỉ tải các thư mục hoặc tệp cần thiết, tiết kiệm thời gian và dung lượng đĩa.
    ```sh
    # Bật chế độ sparse-checkout
    git sparse-checkout init
    # Chỉ lấy các thư mục cụ thể
    git sparse-checkout set services/ docs/
    ```

5. **git log --remerge-diff - Hiểu Rõ Hơn Về Merge**
    Khi merge, `git log` thường chỉ hiển thị nhánh nào đã được merge, nhưng không giải thích rõ ràng các thay đổi đã thêm vào. `git log --remerge-diff` giúp bạn hiểu rõ các thay đổi cụ thể trong quá trình merge.
    ```sh
    git log --remerge-diff
    ```

6. **git blame --ignore-rev - Bỏ Qua Các Commit Gây Nhiễu**
    Khi nhóm thực hiện các thay đổi định dạng hàng loạt, `git blame` trở nên ít hữu ích hơn vì mỗi dòng đều trỏ đến commit định dạng thay vì tác giả gốc. `--ignore-rev` giúp bạn bỏ qua các commit gây nhiễu này.
    ```sh
    git blame --ignore-rev commit-hash
    # Thêm commit hash vào tệp ignore-revs
    echo commit-hash >> .git-blame-ignore-revs
    # Bảo Git sử dụng tệp này
    git config blame.ignoreRevsFile .git-blame-ignore-revs
    ```

7. **git range-diff - So Sánh và Theo Dõi Thay Đổi Giữa Các Phạm Vi Commit**
    Nếu bạn đang làm việc với rebase hoặc cherry-pick, `git range-diff` giúp bạn so sánh hai phạm vi commit và hiển thị sự khác biệt giữa chúng.
    ```sh
    git range-diff
    ```

8. **git worktree - Làm Việc Với Nhiều Nhánh Đồng Thời**
    Nếu bạn cần làm việc trên nhiều nhánh mà không phải chuyển đổi liên tục giữa chúng, `git worktree` cho phép bạn tạo nhiều thư mục làm việc cho mỗi nhánh.
    ```sh
    # Thêm một worktree mới cho một nhánh cụ thể
    git worktree add ../feature-branch feature-branch
    # Xóa một worktree khi bạn đã xong
    git worktree remove ../feature-branch
    ```

9. **git rebase --update-refs - Giữ Các Tham Chiếu Đồng Bộ**
    Khi thực hiện rebase, Git thay thế các commit cũ bằng các commit mới, thường để lại các con trỏ nhánh hoặc tag tham chiếu đến các commit lỗi thời. Git 2.38 đã giới thiệu tùy chọn `--update-refs` để tự động xử lý vấn đề này.
    ```sh
    git rebase --update-refs
    # Cấu hình git rebase để luôn cập nhật các tham chiếu cụ thể
    git config rebase.updateRefs true
    ```

10. **git commit --fixup và git rebase --autosquash - Sửa Commit**
     Khi bạn cần sửa một commit trước đó, `git commit --fixup` và `git rebase --autosquash` giúp bạn tự động chỉnh sửa và squash các commit mà không cần can thiệp thủ công.
     ```sh
     # Tạo một fixup commit nhắm vào một commit cụ thể
     git commit --fixup=<commit-hash>
     # Sau đó, trong quá trình rebase tương tác, tự động squash các fixup commit
     git rebase -i --autosquash <base-branch>
     ```
     git rebase -i --autosquash <base-branch>
     ```