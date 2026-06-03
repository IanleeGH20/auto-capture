# Frankfort Capture

교정 경과를 일관된 자세로 촬영하고 날짜별로 비교하는 기록 도구 (설치형 웹앱 / PWA).
모든 사진·측정값은 사용자의 기기 안에만 저장되며 외부로 전송되지 않습니다.

## 폴더 구성
모든 파일은 저장소 루트(같은 폴더)에 두어야 합니다.

- `index.html` — 앱 본체
- `manifest.webmanifest` — PWA 매니페스트
- `sw.js` — 서비스워커 (오프라인 캐시)
- `icon-192.png`, `icon-512.png`, `icon-maskable-512.png` — 앱 아이콘

## GitHub에 올리고 배포하기 (GitHub Pages)

### 방법 A — 웹에서 (명령어 없이)
1. GitHub 가입 후 새 저장소 생성 (예: `frankfort-capture`, Public).
2. "Add file → Upload files"로 위 파일을 모두 끌어다 놓고 Commit.
3. Settings → Pages → Source: "Deploy from a branch", Branch: `main` / `/ (root)` → Save.
4. 1~2분 뒤 `https://<아이디>.github.io/frankfort-capture/` 주소 생성.

### 방법 B — git 명령어로
```bash
git init
git add .
git commit -m "Frankfort Capture PWA"
git branch -M main
git remote add origin https://github.com/<아이디>/<저장소>.git
git push -u origin main
```
이후 Settings → Pages에서 위와 같이 브랜치를 지정해 배포합니다.

## 폰에 앱으로 설치
배포된 `https://...github.io/...` 주소를 폰에서 엽니다 (HTTPS라서 카메라 사용 가능).

- Android Chrome: 메뉴(⋮) → **앱 설치** 또는 **홈 화면에 추가**
- iPhone Safari: 공유 버튼 → **홈 화면에 추가**

설치하면 아이콘으로 실행되고 전체화면으로 동작합니다.
첫 실행에는 인터넷이 필요합니다(얼굴 인식 모델을 받아 캐시함). 이후에는 오프라인 실행이 가능합니다.

## 참고
- 사진은 브라우저 저장소(IndexedDB)에 저장되므로, 해당 브라우저의 사이트 데이터를 지우면 사진도 삭제됩니다.
- 진단·치료 도구가 아닌 경과 기록 도구입니다.
