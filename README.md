# Smart QR (Android WebView App)

[https://nanalab.kr/qr](https://nanalab.kr/qr) 페이지를 전체화면으로 띄우는 안드로이드 WebView 앱입니다.

## 주요 기능

- **전체화면(Immersive Fullscreen)**: 상태바/내비게이션바 및 노치(Cutout) 영역까지 꽉 차는 전체화면 지원
- **QR 코드 이미지 다운로드**: 웹페이지에서 QR 코드를 탭해 다운로드할 때(`data:image/...`) Android `Pictures/SmartQR` 갤러리에 바로 저장
- **네트워크 오류 화면**: 오프라인/연결 오류 시 깔끔한 안내 화면과 **다시 시도** 버튼 제공
- **뒤로가기 지원**: 웹페이지 히스토리가 있으면 이전 페이지로 이동, 없으면 뒤로 버튼 2회 터치 시 종료
- **앱 아이콘**: Smart QR 브랜드 컬러(`#8B5CF6` → `#EC4899`) 기반 Adaptive Icon 및 해상도별(`mdpi`~`xxxhdpi`) 아이콘 포함

## GitHub Actions로 APK 빌드하는 방법 (Android Studio 불필요)

1. GitHub에 새 저장소(Repository)를 만듭니다.
2. 이 폴더의 모든 파일을 GitHub 저장소의 `main` 브랜치에 푸시합니다.
   ```bash
   git init
   git add .
   git commit -m "Initial Smart QR Android WebView app"
   git branch -M main
   git remote add origin https://github.com/<내계정>/<저장소이름>.git
   git push -u origin main
   ```
3. GitHub 저장소 상단의 **Actions** 탭으로 이동합니다.
   - `main` / `master` 브랜치에 푸시되면 자동으로 빌드가 시작됩니다.
   - 수동 실행하려면 **Build Android APK** 워크플로우에서 **Run workflow**를 누르면 됩니다.
4. 빌드가 완료되면 해당 워크플로우 실행 페이지 하단의 **Artifacts** 섹션에서 **`SmartQR-debug-apk`**를 다운로드하고 압축을 풀어 `app-debug.apk`를 안드로이드 기기에 설치하세요.
   - `SmartQR-debug-apk` (`app-debug.apk`): 테스트 서명이 포함되어 있어 안드로이드 폰에 바로 설치 가능
   - `SmartQR-release-unsigned-apk` (`app-release-unsigned.apk`): 스토어 배포용으로 별도 서명이 필요한 미서명 릴리스 APK
