# YouTube ReVanced (RVX) 빌드 가이드

이 가이드는 **Obtainium**을 통해 필수 앱의 설치와 업데이트를 관리하고, **RVX Manager**로 유튜브를 직접 빌드하는 방법을 안내합니다.

> **참고:** 각 패치(기능)에 대한 상세 설명은 [RVX Features 문서](https://kazimmt.github.io/rvx-features/yt-rvx-features/)를 참고하세요.

---

## 0. 준비: Obtainium 설치 (업데이트 관리자)
가장 먼저 설치해야 할 앱입니다. 이후 설치할 MicroG나 Manager를 GitHub에서 직접 가져와 설치하고, **최신 버전 업데이트 알림**까지 관리해 줍니다.

- **다운로드 링크:** [Obtainium Releases (Latest)](https://github.com/ImranR98/Obtainium/releases/latest)

### 📂 어떤 파일을 받아야 하나요?
링크에서 본인의 기기 사양에 맞춰 아래 중 하나를 다운로드하여 설치하세요.

1. **통합 버전 (Universal) ✅**
   - **파일명:** `app-release.apk`
   - **설명:** 모든 아키텍처를 포함하여 용량은 크지만, 기기 호환성을 탈 필요 없이 확실하게 설치됩니다.

2. **64-bit (Arm64)**
   - **파일명:** `app-arm64-v8a-release.apk`
   - **설명:** 일반적인 스마트폰(64비트 환경)을 위한 파일입니다.

3. **32-bit (Armeabi-v7a)**
   - **파일명:** `app-armeabi-v7a-release.apk`
   - **설명:** 32비트 환경의 기기를 위한 파일입니다.

---

## 1. 필수 앱 등록 및 설치 (via Obtainium)
GmsCore(MicroG)와 RVX Manager를 Obtainium에 등록하여 설치합니다.

### 1-1. Obtainium에 소스 추가하기
1. **Obtainium** 앱 실행 → 하단 **+ 앱 추가(Add App)** 클릭.
2. 아래의 **GitHub 주소**를 각각 복사하여 입력창에 넣고 **추가(Add)**를 누릅니다.

**① GmsCore (구글 로그인 필수 서비스)**
```
https://github.com/ReVanced/GmsCore
```

**② RVX Manager (패치 및 빌드 도구)**
```
https://github.com/inotia00/revanced-manager
```

### 1-2. 앱 설치 시 주의사항 (중요)
소스 추가 후 목록에서 **설치(Install)**를 누를 때, **GmsCore**는 파일 선택에 주의해야 합니다.

- **일반 사용자:** 파일명에 `hw`가 **없는** 파일을 설치하세요. (예: `app.apk`)
- **화웨이 사용자:** 파일명에 `hw`가 **포함된** 파일을 설치하세요. (예: `app-hw.apk`)

---

## 2. GmsCore (MicroG) 설정
설치된 GmsCore 앱을 열어 필수 설정을 진행합니다.

### 2-1. 구글 로그인
1. 앱 실행 → **Google Accounts**.
2. `+ Add Google Account`를 눌러 구글 계정 로그인.

### 2-2. 배터리 최적화 끄기 (필수)
영상이 중간에 멈추거나 무한 로딩되는 현상을 방지합니다.
1. 앱 실행 → **애플리케이션 정보** (또는 기기 설정의 앱 정보).
2. **배터리(Battery)** 항목 진입.
3. 설정을 **'제한 없음(Unrestricted)'**으로 변경.

---

## 3. RVX Manager 설정
설치된 Manager 앱을 열어 빌드 환경을 설정합니다.

### 3-1. 기본 설정 (Settings)
Manager 앱 하단 **설정(Settings)** 메뉴로 이동하여 변경하세요.

1. **권장 앱 버전 요구(Require suggested app version)**: `OFF` (끔)
2. **Pre-release 사용(Use Pre-release)**: `ON` (켬)

### 3-2. 소스(Sources) 변경
**설정(Settings)** → **소스(Sources)** 메뉴에서 사용하려는 버전에 맞춰 텍스트를 수정합니다.

**Inotia00 (표준/안정적)**
```
inotia00
```

**Anddea (다기능/커스텀)**
```
anddea
```

> **주의:** `패치 조직`과 `통합 조직` 두 곳 모두 입력해야 하며, 입력 후 `확인`을 누르고 앱을 반드시 **재시작**해야 적용됩니다.

---

## 4. YouTube 순정 APK 준비
**주의:** Play 스토어 버전은 패치할 수 없습니다. 반드시 APKMirror 파일을 사용하세요.

1. **RVX Manager** → **패처(Patcher)** → **앱 선택(Select an app)** → **YouTube**.
2. 상단의 **[권장(Suggested) 버전]** 번호를 확인합니다.
3. **APKMirror** 사이트에서 해당 버전의 **`nodpi` APK**를 다운로드합니다. (설치는 하지 마세요!)

> **💡 버전 선택 가이드**
>
> - **일반적인 경우:** Manager가 띄워주는 **'권장(Suggested)'** 버전을 사용하세요.
> - **썸네일 기능 필요 시:** 탐색 바 미리보기가 꼭 필요하다면 **v19.16.39** 버전을 권장합니다. (최신 버전은 구글 제약으로 해당 기능 불가)

---

## 5. 빌드 및 패치 (Build)

1. Manager 우측 하단 **기기 저장소(Storage)** 클릭 → 다운로드한 순정 APK 선택.
2. **선택된 패치(Selected patches)** 클릭 → `Default` 버튼 클릭 (기본 추천 패치 적용).
3. **(선택 사항)** 아이콘과 이름을 취향에 맞게 설정합니다. (아래 팁 참고)
4. `선택 완료(Done)` → `패치(Patch)` 버튼 클릭.

> **🎨 꿀팁: 아이콘과 이름 설정 (Custom Branding)**
> 패치 목록에서 `Custom branding` 관련 항목을 체크/해제하여 앱의 스타일을 정할 수 있습니다.
>
> - **`Custom branding icon` & `Custom branding name`**
>   - ✅ **체크 시:** ReVanced 전용 아이콘과 이름("YouTube ReVanced")으로 변경됩니다.
>   - ⬜ **해제 시:** 순정 YouTube 아이콘과 이름("YouTube")을 그대로 유지합니다. (일반 유튜브처럼 보이고 싶을 때 추천)

---

## 6. 저장 및 설치 (Install)

패치가 완료되면 바로 설치하지 말고 **저장**부터 하세요.

1. **APK 저장 (필수):** 좌측 하단 **저장(Save)** 버튼(💾) 클릭.
   - *오류 발생 시나 재설치 시 다시 빌드할 필요 없이 이 파일을 사용하면 됩니다.*
2. **설치:** 우측 하단 **설치(Install)** 버튼 클릭.
