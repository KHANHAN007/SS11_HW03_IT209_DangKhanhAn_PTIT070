# Spring Boot - Gradle Dependency Cache Demo

Project cho bài IT209 Session 11 Exercise 3, dùng Java 17 và Gradle Wrapper.

## Chạy trên Mac

```bash
export JAVA_HOME=$(/usr/libexec/java_home -v 17)
chmod +x gradlew
./gradlew test bootJar
./gradlew bootRun
```

API: `http://localhost:8080/health`, trả JSON có `status: UP`.

## Tạo repository và push lần đầu

Chạy tại thư mục chứa README này:

```bash
git init
git branch -M main
git add .
git commit -m "init: Spring Boot with Gradle caching CI"
gh auth switch -u KHANHAN007
gh repo create KHANHAN007/SS11_HW03_IT209_DangKhanhAn_PTIT070 --public --source . --remote origin --push
```

Vào GitHub Actions, chờ job đầu tiên thành công hoàn toàn để cache được lưu.

## Push lần thứ hai

```bash
git commit --allow-empty -m "ci: verify Gradle cache restoration"
git push
```

Trong Actions, ghi lại thời gian Setup Java, Run tests và tổng job cho cả hai lần. Tìm thông báo khôi phục cache ở lần hai.

Điền kết quả thực tế vào `homework/session_11/ex3/report.md`, sau đó commit và push báo cáo.

Workflow cần nằm ở `.github/workflows/ci.yml` tại gốc repository để GitHub tự chạy. Không chuyển toàn bộ project vào một thư mục con sau khi tạo repository.
