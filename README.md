# 빛틈 홈페이지 + Pages CMS

## 사이트 구성
- `/` 기존 로고·오리·물결·다크 모드·인스타그램 유지. 오리를 누르면 `/books/`로 이동.
- `/books/` 도서 목록, `/books/out-of-the-shadows/` 도서 상세.
- `/notes/` 편집자의 글, `/about/` 출판사 소개.
- 도서 및 글은 Pages CMS에서 편집해 GitHub에 저장. Jekyll이 HTML을 빌드.

## 설치·배포 (중요)
1. 현재 GitHub 저장소를 백업하고 **압축파일 안의 파일과 숨김 파일 `.pages.yml` 및 `_config.yml`을 포함해** 저장소 최상위에 올리세요.
2. GitHub 저장소 Settings → Pages → Build and deployment → Source를 **Deploy from a branch**, Branch를 `main` / `(root)`로 설정하세요. GitHub Pages 기본 Jekyll 빌드가 컬렉션을 생성합니다. (기존 Actions 워크플로가 있다면 충돌 여부 확인)
3. `https://www.vitteum.com/books/` 접속을 확인하세요.
4. https://pagescms.org/ 에 GitHub로 로그인하고 해당 저장소를 선택하세요. 루트의 `.pages.yml` 설정을 읽으면 '도서'와 '편집자의 글' 편집 메뉴가 표시됩니다. 저장하면 커밋되어 재배포됩니다.
5. CMS가 요구하는 저장소 접근 권한을 검토하고 승인하세요. 무료 플랜·기능·정확한 UI는 서비스의 현재 정책을 확인하세요.

## 게시 전 확인
- 도서 표지 이미지를 `assets/covers/`에 올리고 책의 `cover` 필드에 지정하세요.
- ISBN과 온라인 서점 구매 링크는 확인된 값만 입력하세요. 현재 비어 있습니다.
- 책 소개·목차·ABOUT의 임시 문구를 교체하세요.
- 새 책은 `_books/영문-슬러그.md`, 새 글은 `_notes/영문-슬러그.md`로 생성합니다. URL은 파일명에서 정해집니다.
- GitHub Pages에서 Jekyll을 사용하는 구조입니다. CMS는 GitHub에 콘텐츠를 저장하는 편집 도구이며, CMS 자체가 웹사이트를 호스팅하는 것은 아닙니다.
- `sitemap.xml`은 Jekyll 루프에서 생성되며 robots.txt가 이를 가리킵니다.
- 로컬 확인: Ruby 및 Bundler 설치 후 `bundle install && bundle exec jekyll serve`.
