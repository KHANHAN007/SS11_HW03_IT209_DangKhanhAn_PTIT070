# Báo cáo Gradle Dependency Caching

## Cấu hình

Bước `actions/setup-java@v5` sử dụng Java 17, Temurin và `cache: 'gradle'`.

## Kết quả thực tế

Chưa đo trên GitHub Actions. Điền sau khi hai lần push đã hoàn tất.

| Tiêu chí | Lần chạy 1 | Lần chạy 2 |
|---|---|---|
| Setup Java | 0s | 6s |
| Run tests | 41s | 17s |
| Tổng thời gian job | 52s | 29s |
| Cache hit/miss | Miss | Hit |
| Link Actions | https://github.com/KHANHAN007/SS11_HW03_IT209_DangKhanhAn_PTIT070/actions/runs/38284180591 | https://github.com/KHANHAN007/SS11_HW03_IT209_DangKhanhAn_PTIT070/actions/runs/38284662512 |

## Log khôi phục cache

Cache restored from key: setup-java-Linux-x64-gradle-8402aa9eaa393fa7c97b1311cc3ec7fb39987da72dc261b1e2e134142232c79c


## Nhận xét

Cache tái sử dụng dependency đã tải. So sánh thời gian thực tế của hai lần chạy; thời gian job còn phụ thuộc runner và chi phí khôi phục cache.
