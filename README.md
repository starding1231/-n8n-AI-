# 리코멘드 Landing Page

이 프로젝트는 Vite + React 기반의 랜딩 페이지입니다.

## 🚀 GitHub Pages 완벽 배포 가이드 (최종 해결책)

`/docs` 폴더를 직접 업로드하는 방식은 파일 동기화 오류와 GitHub의 Jekyll 처리 과정에서 404 에러(`dir_chdir0`)가 자주 발생합니다. 이를 **GitHub Actions**를 이용한 자동 배포 방식으로 전환하여 문제를 근본적으로 해결했습니다.

### 1단계: 변경사항을 GitHub에 반영하기
1. AI Studio 우측 상단의 **`Export to GitHub`**를 클릭하여 현재 모든 파일(`.github` 폴더 및 `package-lock.json` 포함)을 저장소에 엎어쓰세요.
2. 깃허브 저장소에 `.github/workflows/deploy.yml` 파일이 생겼는지 확인합니다.

### 2단계: GitHub Pages 설정 변경 (매우 중요)
1. 자신의 GitHub 리포지토리 페이지에서 **Settings > Pages** 메뉴로 들어갑니다.
2. **Build and deployment > Source** 옵션을 찾아 **`GitHub Actions`**로 변경합니다. (기존 "Deploy from a branch"에서 반드시 바꿔야 합니다!)
3. 설정을 바꾸면 별도의 branch나 folder 선택 없이 자동으로 배포 프로세스가 시작됩니다.

### 3단계: 배포 상태 확인
- 상단의 **Actions** 탭을 누르면 `Deploy to GitHub Pages` 워크플로우가 돌아가는 것을 볼 수 있습니다.
- 초록색 체크 표시가 뜨면 배포가 완료된 것입니다.
- 배포 주소: `https://starding1231.github.io/n8n-AI/` (또는 본인의 저장소 설정 주소)

---

### 이미지 및 빌드 설정 안내
- **상대 경로**: `vite.config.ts`에서 `base: './'`로 설정되어 있어 저장소 이름이 바뀌어도 이미지가 깨지지 않습니다.
- **이미지 사용**: `src/assets/images`에 원본을 두고 React에서 `import`하여 사용하세요.
- **자동 빌드**: 이제 저장소에 소스 코드만 올리면 GitHub가 알아서 빌드(dist 생성)하고 배포하므로 로컬 빌드 오류 걱정이 없습니다.

### 개발 및 로컬 테스트
```bash
# 개발 서버 실행 (AI Studio 환경 동일)
npm run dev

# 로컬 빌드 테스트
npm run build
```
