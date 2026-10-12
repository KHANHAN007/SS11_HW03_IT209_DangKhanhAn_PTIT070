# Bài 5 - Test Gradle và Build/Push Docker Image

- Sinh viên: Đặng Khánh An - PTIT070
- Workflow: `.github/workflows/ci.yml` tại gốc repository.
- Dockerfile: `Dockerfile` tại gốc repository.

## Luồng CI

Job `test` thiết lập Java 17, khôi phục Gradle cache và chạy `./gradlew test bootJar --no-daemon`. JAR được lưu thành artifact.

Job `docker-build` khai báo `needs: test`, tải JAR, đăng nhập GHCR bằng Repository Secret `REGISTRY_TOKEN`, rồi build và push bằng `docker/build-push-action@v5`.

Image: `ghcr.io/khanhan007/ss11-hw05-springboot:latest`.

Các job dùng runner riêng nên cần upload/download artifact để chuyển JAR. Job publish chỉ chạy với push hoặc workflow_dispatch; pull request chỉ chạy test.

## Minh chứng cần bổ sung

1. Chụp sơ đồ hai job thành công, lưu `workflow-success.png` trong thư mục này.
2. Sửa assertion trong test từ `UP` thành `DOWN`, commit và push. Chụp job test failed và docker-build skipped, lưu `workflow-skipped.png`.
3. Sửa assertion về `UP`, commit và push lại để nhánh main kết thúc ở trạng thái thành công.

Chưa có ảnh hoặc kết quả chạy trên GitHub cho phiên bản workflow mới. Chỉ bổ sung kết quả thực tế sau khi chạy.
