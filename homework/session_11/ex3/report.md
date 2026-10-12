# Báo cáo Gradle Dependency Caching

- Họ tên: Đặng Khánh An
- Mã sinh viên: PTIT070
- Môn học: IT209
- Workflow: `.github/workflows/ci.yml` tại gốc repository.

## Cấu hình

Bước `actions/setup-java@v5` sử dụng Java 17, Temurin và `cache: 'gradle'`.

## Kết quả thực tế

Chưa đo trên GitHub Actions. Điền sau khi hai lần push đã hoàn tất.

| Tiêu chí | Lần chạy 1 | Lần chạy 2 |
|---|---|---|
| Setup Java | Chưa đo | Chưa đo |
| Run tests | Chưa đo | Chưa đo |
| Tổng thời gian job | Chưa đo | Chưa đo |
| Cache hit/miss | Chưa kiểm tra | Chưa kiểm tra |
| Link Actions | Chưa có | Chưa có |

## Log khôi phục cache

Dán dòng log thực tế của lần chạy thứ hai vào đây.

## Nhận xét

Cache tái sử dụng dependency đã tải. So sánh thời gian thực tế của hai lần chạy; thời gian job còn phụ thuộc runner và chi phí khôi phục cache.
