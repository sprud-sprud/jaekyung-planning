# 재🐰경 planning

병재·혜경 결혼 준비 페이지 (Planning / 웨딩홀 / 촬영 / 비용).
GitHub Pages에 올리고, 데이터는 Firebase Firestore에 저장해요.

## 파일

| 파일 | 내용 | GitHub에 올리기 |
|---|---|---|
| `index.html` | 페이지 전체 | O |
| `firestore.rules` | Firestore 보안 규칙 (Firebase 콘솔에 붙여넣기용) | O (올려도 괜찮음) |
| `data-export.json` | 지금까지 입력한 데이터 | **X — 올리지 마세요** (`.gitignore`에 들어 있음) |

## 1. Firebase 준비 (5분)

1. https://console.firebase.google.com → **프로젝트 추가** (이름 예: `jaekyung-planning`, 애널리틱스는 꺼도 됨)
2. 왼쪽 메뉴 **Firestore Database → 데이터베이스 만들기**
   - 위치: `asia-northeast3 (서울)`
   - **프로덕션 모드**로 시작
3. Firestore **규칙** 탭 → 내용을 `firestore.rules` 파일 내용으로 바꾸고 **게시**
4. **프로젝트 설정(톱니바퀴) → 내 앱 → 웹(</>) 앱 추가** → 나오는 `firebaseConfig` 값을 복사
5. `index.html` 맨 아래 `FIREBASE_CONFIG = { ... }` 에 붙여넣기

## 2. GitHub Pages 올리기

1. GitHub에서 새 저장소 만들기 (무료 계정이면 Public)
2. `index.html`, `firestore.rules`, `README.md`, `.gitignore` 올리기
3. 저장소 **Settings → Pages → Branch: main / (root) → Save**
4. 1~2분 뒤 `https://<아이디>.github.io/<저장소이름>/` 로 열기

## 3. 처음 열 때

1. **우리 공간 만들기** 누르기 → 주소 끝에 `?k=긴비밀키` 가 붙어요
2. "공간이 비어 있어요" 화면에서 **파일 선택 → `data-export.json`** 선택하면 기존 데이터가 들어가요
3. 오른쪽 위 **링크 복사** → 남자친구에게 카톡으로 보내기 (계정 없이 바로 같이 써요)

## 보안 메모

- 데이터는 `rooms/<비밀키>/...` 아래에 저장돼요. 비밀키는 링크에만 있고 GitHub에는 없어요.
- **링크를 아는 사람은 누구나 보고 고칠 수 있으니** 둘 외에는 공유하지 마세요.
- `firebaseConfig`의 apiKey는 원래 공개돼도 되는 값이에요. 보호는 보안 규칙 + 비밀키가 해요.
- 저장소는 공개라 코드는 보이지만, 페이지에 `noindex`를 넣어 검색엔진에는 안 뜨게 했어요.
- 열 때 **비밀번호 4자리** 화면이 나와요(한 번 맞히면 그 기기에서는 기억). 이건 화면을 가리는 용도일 뿐이라, 코드를 열어보는 사람까지 막지는 못해요. 진짜 데이터 보호는 비밀키 링크가 해요.

## 홈 화면에 추가

링크(`?k=...` 포함)를 연 상태에서 **공유 → 홈 화면에 추가**를 눌러주세요. 아이콘은 흰 배경에 핑크 잎사귀예요(`apple-touch-icon.png`, `icon-192.png`).
