# 리코멘드 Landing Page

이 프로젝트는 Vite + React 기반의 랜딩 페이지입니다.

## GitHub Pages 배포 방법 (자동 배포)

이 프로젝트는 GitHub Actions를 통해 코드를 푸시할 때마다 자동으로 배포되도록 설정되어 있습니다.

1. 이 프로젝트의 모든 코드를 GitHub 리포지토리의 `main` 브랜치에 업로드(푸시)합니다.
2. GitHub 리포지토리 페이지에서 **Settings > Pages** 메뉴로 이동합니다.
3. **Build and deployment > Source** 항목의 드롭다운 메뉴에서 **GitHub Actions**를 선택합니다.
4. 상단의 **Actions** 탭으로 이동하면 배포 과정이 표시됩니다.
5. 배포가 완료되면 `https://starding1231.github.io/-n8n-AI-/` 주소에서 확인 가능합니다.

### 빌드 오류 해결 (Native Binding 관련)
빌드 중 "Cannot find native binding" 오류가 발생하는 경우를 대비하여, 현재 설정은 `package-lock.json`과 `node_modules`를 매번 삭제하고 새로운 환경에서 의존성을 설치하도록 구성되어 있습니다. 또한 `lightningcss`와 `esbuild`를 명시적으로 추가하여 빌드 엔진이 정상적으로 작동하도록 조치했습니다.

### 주요 설정 정보
- **배포 환경**: Node.js 18
- **Base Path**: `/-n8n-AI-/` (vite.config.ts에 설정됨)


## 수동 빌드 방법

```bash
npm install
npm run build
```

빌드된 파일은 `dist` 폴더에 생성됩니다.
