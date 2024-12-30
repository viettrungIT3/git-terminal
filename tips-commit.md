# Commit code với `git commit`

Câu lệnh dưới đây sẽ đính kèm các title khi bạn thực hiện những thay đổi trong dự án. Nó có tác dụng với những file trong khu vực **Staging**.

```bash
git commit -m "Description"
```

> **Lưu ý** có một số terminal bắt buộc bạn phải dùng dấu nháy kép "" chứ không được dùng dấu nháy đơn ''. Còn một số terminal thì dùng cả 2 đều được.

Trong trường hợp bạn muốn đính kèm thêm description để mô tả thêm cho title thì bạn có thể dùng 2 cách

Cách 1:

```bash
git commit -m "Title" -m "Description"
```

Cách 2: Bạn gõ thiếu dấu `"` và nhấn Enter nó sẽ cho bạn xuống dòng, tiếp theo bạn sẽ gõ tiếp mô tả và kết thúc bằng dấu `"` là được.

```bash
git commit -m "Title
> Description"
```

## Commit  "SẠCH"

### Tại sao cần một **Commit** "Sạch"
* Các bạn hãy thử mở 1 project bất kỳ của bản thân lên và xem commit history của nó, mình thề là đa số sẽ phải thốt lên "mình đã commit cái quái gì vậy",...
* Vì vậy khi mà viết một **commit** "Sạch" ở hiện tại chính là giúp bạn ở tương lại (hoặc ít nhất là không chửi bạn của hiện tại), trong trong team thì nó sẽ giúp đồng nghiệp của bạn nhẹ đầu hơn.

### Cấu trúc của một **Conventional commit"

> **Conventional Commit** là một quy ước định dạng cung cấp một số bộ quy tắc để xây dựng cấu trúc của một commit có tính nhất quán giúp developer quản lý thay đổi một cách tổ chức, dễ dàng theo dõi và đánh giá các phiên bản phần mềm. 

```bash
<type>[optional scope]: <description>
[optional body]
[optional footer(s)]
```

#### Commit type: 
Thể hiện sự thay đổi mà bạn đã thực hiện

Các kiểu commit type:

| Loại Commit | Tiêu Đề                  | Mô tả                                                                                                       | Emoji  |
| ----------- | ------------------------ | ----------------------------------------------------------------------------------------------------------- |:------:|
| `feat`      | Features                 | Một tính năng mới                                                                                           | ✨     |
| `fix`       | Bug Fixes                | Sửa một lỗi                                                                                                 | 🐛     |
| `docs`      | Documentation            | Chỉ thay đổi tài liệu                                                                                       | 📚     |
| `style`     | Styles                   | Thay đổi không ảnh hưởng đến ý nghĩa của mã (khoảng trắng, định dạng, thiếu dấu chấm phẩy, v.v.)            | 💎     |
| `refactor`  | Code Refactoring         | Một thay đổi mã không sửa lỗi hoặc thêm tính năng                                                           | 📦     |
| `perf`      | Performance Improvements | Một thay đổi mã cải thiện hiệu suất                                                                         | 🚀     |
| `test`      | Tests                    | Thêm các kiểm thử thiếu hoặc sửa các kiểm thử hiện có                                                       | 🚨     |
| `build`     | Builds                   | Thay đổi ảnh hưởng đến hệ thống xây dựng hoặc các phụ thuộc bên ngoài (ví dụ: gulp, broccoli, npm)          | 🛠     |
| `ci`        | Continuous Integrations  | Thay đổi vào tệp cấu hình và kịch bản CI của chúng tôi (ví dụ: Travis, Circle, BrowserStack, SauceLabs)     | ⚙️     |
| `chore`     | Chores                   | Những thay đổi khác không sửa đổi các tệp nguồn hoặc kiểm thử                                               | ♻️     |
| `revert`    | Reverts                  | Quay lại một commit trước đó                                                                                | 🗑     |

### [optional scope]
> Cũng được dùng để phân loại commit, vùng ảnh hưởng của commit, 
>
> Và nó trả lời câu hỏi: commit này refactor|fix cái gì? được đặt trong cặp ngoặc đơn ngay sau type. 
>
> VD: feat(authentication):, fix(parser):

#### description: là mô tả ngắn về những gì sẽ bị sửa đổi trong commit đấy
1. Viết message **đơn giản** và **tập chung**
Mỗi commit đại diện cho một thay đổi hoặc sửa lỗi logic **duy nhất**