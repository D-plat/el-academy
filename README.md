# 이든 아카데미 (EDEN Academy)

원페이지 랜딩. 빌드 도구 없이 정적 파일만으로 동작한다.

```
index.html            페이지 전체 (CSS·JS 인라인)
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

※ 상담 신청 섹션은 요청에 따라 삭제된 상태다.

## 배포 (Cloudflare Pages)

1. GitHub 새 저장소에 이 폴더의 **내용물을 루트에** 올린다.
2. Cloudflare → Workers & Pages → Create → Pages → Connect to Git
3. Framework preset `None`, Build command 비움, Build output directory `/`
4. Save and Deploy

배포 후 `index.html` 상단의 `https://el-academy.pages.dev` 3곳(canonical, og:image, og:url)을
실제 주소로 교체한다.

## 참고

- 모든 애니메이션은 `prefers-reduced-motion`을 따른다.
