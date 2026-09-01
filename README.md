# 이엘 아카데미 (EL Academy)

원페이지 랜딩. 빌드 도구 없이 정적 파일만으로 동작한다.

```
index.html            페이지 전체 (CSS·JS 인라인)
_headers              Cloudflare Pages 캐시·보안 헤더
assets/hero.webp      01 히어로
assets/card1~4.webp   05 4단 카드
assets/human.webp     03 결국 사람
assets/space1~2.webp  06 공간
assets/logo.webp      투명 로고
assets/og.jpg         공유 미리보기 1200×630
assets/favicon-*      파비콘 32 / 180 / 192
```

## 섹션 순서

1. 히어로 — AI가 빠르게 변하는 시대, 나는 준비되어 있을까요?
2. 무엇이 대체되고, 무엇이 사라지고 있을까요?
3. 기술이 아무리 발전해도, 성장해야 하는 것은 결국 사람입니다
4. 브랜드 — 배우고 성장하며 진짜 나를 찾고 더 나은 미래를 준비하는 곳
5. 01~04 카드
6. 이곳은 어떤 공간입니다 / 함께하는 과정

상담 신청 섹션은 요청에 따라 삭제된 상태다.

---

## 배포 (GitHub + Cloudflare Pages)

### 1. GitHub

이 폴더의 **내용물을 저장소 루트에** 올린다. (`el-academy-site` 폴더째로 올리면 경로가 밀려서 안 뜬다)

저장소 이름: `el-academy`

### 2. Cloudflare Pages

1. Cloudflare 대시보드 → **Workers & Pages** → **Create** → **Pages** → **Connect to Git**
2. 저장소 `el-academy` 선택
3. 프로젝트 이름: **`el-academy`** ← 이게 주소가 된다
4. 빌드 설정
   - Framework preset: **None**
   - Build command: **(비움)**
   - Build output directory: **`/`**
5. **Save and Deploy**

→ https://el-academy.pages.dev

이후 `main`에 push할 때마다 자동 배포된다. PR을 올리면 미리보기 URL도 자동 생성.

### 3. 커스텀 도메인

프로젝트 → **Custom domains** → 도메인 입력 → 안내되는 CNAME 등록. SSL은 자동.

---

## 수정 메모

- 프로젝트 이름을 `el-academy` 말고 다른 걸로 하면 `index.html` 상단 메타 태그 3곳
  (`canonical`, `og:image`, `og:url`)의 `el-academy.pages.dev`도 같이 고쳐야
  카카오톡·페이스북 공유 미리보기가 뜬다.
- 애니메이션은 전부 `prefers-reduced-motion`을 따른다.
- `_headers`에 따라 이미지는 1년 캐시된다. 같은 파일명으로 교체하면 반영이 늦으니
  `hero-2.webp`처럼 이름을 바꾸고 `index.html` 경로도 함께 고치는 편이 확실하다.
