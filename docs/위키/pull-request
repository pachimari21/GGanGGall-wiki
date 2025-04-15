---
title: Github로 위키에 작성한 문서 추가하기
icon: file-added
---
# Github로 위키에 작성한 문서 추가하기

다른 사용자가 위키 레포지토리에 문서를 추가하고 Pull Request를 통해 기여하는 방법 설명.

## 목차
- [사전 준비](#사전-준비)
- [저장소 포크하기](#저장소-포크하기)
- [로컬에서 작업하기](#로컬에서-작업하기)
- [문서 추가하기](#문서-추가하기)
- [변경사항 커밋 및 푸시하기](#변경사항-커밋-및-푸시하기)
- [Pull Request 생성하기](#pull-request-생성하기)
- [Pull Request 검토 및 병합](#pull-request-검토-및-병합)
- [자주 묻는 질문](#자주-묻는-질문)

---

## 사전 준비

Pull Request를 통해 위키에 기여하기 위한 필수 준비 사항:

1. GitHub 계정 보유
2. Git 기본 지식 (clone, commit, push 등의 명령어 이해)
3. 마크다운(.md) 문법 기본 이해

## 저장소 포크하기

1. GitHub에서 위키 레포지토리 페이지 방문
2. 오른쪽 상단의 "Fork" 버튼 클릭
   ![Fork 버튼 이미지](/images/fork-button.png)
3. 필요한 경우 포크 옵션 설정 후 "Create fork" 버튼 클릭
4. 이제 본인의 GitHub 계정에 원본 저장소의 복사본 생성 완료

## 로컬에서 작업하기

1. 포크한 저장소를 로컬 컴퓨터에 클론:
   ```bash
   git clone https://github.com/YOUR-USERNAME/REPOSITORY-NAME.git
   cd REPOSITORY-NAME
   ```

2. 원본 저장소를 원격 저장소로 추가(선택 사항이지만 권장):
   ```bash
   git remote add upstream https://github.com/ORIGINAL-OWNER/REPOSITORY-NAME.git
   ```

3. 작업할 새 브랜치 생성:
   ```bash
   git checkout -b add-new-docs
   ```
   - 브랜치 이름은 추가할 문서 내용을 반영하도록 작성 권장

## 문서 추가하기

1. 적절한 폴더 위치에 새 마크다운 파일 생성:
   ```bash
   touch docs/new-document.md
   ```

2. 문서 작성 시 위키의 서식 가이드라인 준수:
   - 올바른 제목 구조 사용 (# 대제목, ## 소제목 등)
   - 필요한 경우 프론트매터 추가
   ```markdown
   ---
   label: 문서 제목
   icon: file
   order: 100
   ---

   # 문서 제목

   내용 시작...
   ```

3. 이미지나 기타 자료를 추가할 경우, 적절한 폴더에 배치:
   ```bash
   mkdir -p static/images/my-document/
   ```

## 변경사항 커밋 및 푸시하기

1. 변경사항 확인:
   ```bash
   git status
   ```

2. 변경사항을 스테이징 영역에 추가:
   ```bash
   git add docs/new-document.md
   # 또는 모든 변경사항 추가
   git add .
   ```

3. 커밋 생성:
   ```bash
   git commit -m "Add documentation for XYZ feature"
   ```
   - 커밋 메시지는 명확하고 서술적으로 작성

4. 변경사항을 포크한 저장소로 푸시:
   ```bash
   git push origin add-new-docs
   ```

## Pull Request 생성하기

1. GitHub의 포크한 저장소 페이지로 이동
2. "Compare & pull request" 버튼 클릭
   - 또는 "Pull requests" 탭으로 이동 후 "New pull request" 클릭
3. Pull Request 설명 작성:
   - 제목: 변경사항을 간결하게 설명
   - 본문: 
     - 무엇을 변경했는지
     - 왜 변경했는지
     - 관련 이슈가 있다면 언급 (#이슈번호 형식)
4. "Create pull request" 클릭

### Pull Request 작성 예시

```
제목: 환경 설정 문서 추가

본문:
- 개발 환경 설정에 관한 새 문서 추가
- 윈도우, 맥, 리눅스 환경 설정 방법 포함
- #42 이슈 해결

문서는 마크다운 서식 가이드라인에 따라 작성함
```

## Pull Request 검토 및 병합

1. 저장소 관리자가 Pull Request 검토
2. 필요한 경우 요청된 변경사항 반영:
   ```bash
   # 변경사항 수정 후
   git add .
   git commit -m "Address review feedback"
   git push origin add-new-docs
   ```
3. 모든 검토가 완료되면 저장소 관리자가 PR 병합
4. 병합 후 브랜치 정리:
   ```bash
   git checkout main
   git pull upstream main
   git push origin main
   git branch -d add-new-docs  # 로컬 브랜치 삭제
   ```

## 자주 묻는 질문

### Q: 포크한 저장소를 최신 상태로 유지하는 방법?
A: 원본 저장소의 변경사항을 가져오는 방법:
```bash
git checkout main
git pull upstream main
git push origin main
```

### Q: Pull Request 후 추가 변경이 필요한 경우?
A: 같은 브랜치에 변경사항을 커밋하고 푸시하면 자동으로 PR에 반영됨.

### Q: 충돌이 발생했을 때 해결 방법?
A: 
1. 원본 저장소의 최신 변경사항 가져오기
   ```bash
   git checkout main
   git pull upstream main
   ```
2. 작업 브랜치로 돌아가 리베이스 또는 병합
   ```bash
   git checkout add-new-docs
   git rebase main
   # 또는
   git merge main
   ```
3. 충돌 해결 후 계속 진행
   ```bash
   git add .
   git rebase --continue  # 리베이스 사용 시
   git push -f origin add-new-docs  # 강제 푸시 필요
   ```

---

이 가이드를 통해 위키 레포지토리에 문서를 추가하고 Pull Request를 생성하는 과정 이해 가능. 문서 작성 시 위키의 스타일 가이드와 기존 문서 형식 참고 권장.
