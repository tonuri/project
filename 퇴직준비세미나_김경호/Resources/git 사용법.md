# Git 사용법

## 1. 초기 설정

```bash
# 사용자 이름 설정
git config --global user.name "홍길동"

# 이메일 설정
git config --global user.email "hong@example.com"

# 설정 확인
git config --list
```

## 2. 저장소 생성 및 복제

```bash
# 새 저장소 생성
git init

# 원격 저장소 복제
git clone https://github.com/user/repo.git
```

## 3. 기본 워크플로우

### 상태 확인

```bash
# 현재 상태 확인
git status

# 변경 내용 확인 (아직 스테이징 안 된 것)
git diff

# 스테이징된 변경 내용 확인
git diff --staged
```

### 스테이징 (add)

```bash
# 특정 파일 스테이징
git add 파일명

# 여러 파일 스테이징
git add 파일1 파일2

# 모든 변경 파일 스테이징
git add .
```

### 커밋 (commit)

```bash
# 커밋 메시지와 함께 커밋
git commit -m "변경 내용 설명"

# 스테이징 + 커밋 동시에 (추적 중인 파일만)
git commit -am "변경 내용 설명"
```

### 커밋 이력 확인

```bash
# 커밋 로그 보기
git log

# 한 줄로 요약해서 보기
git log --oneline

# 그래프로 보기
git log --oneline --graph
```

## 4. 브랜치

```bash
# 브랜치 목록 확인
git branch

# 새 브랜치 생성
git branch 브랜치명

# 브랜치 전환
git checkout 브랜치명
git switch 브랜치명

# 생성과 전환 동시에
git checkout -b 브랜치명
git switch -c 브랜치명

# 브랜치 삭제
git branch -d 브랜치명

# 브랜치 병합 (현재 브랜치에 대상 브랜치를 병합)
git merge 대상브랜치명
```

## 5. 원격 저장소

```bash
# 원격 저장소 확인
git remote -v

# 원격 저장소 추가
git remote add origin https://github.com/user/repo.git

# 원격에 푸시
git push origin 브랜치명

# 원격에서 가져오기 (병합 안 함)
git fetch origin

# 원격에서 가져오기 + 병합
git pull origin 브랜치명
```

## 6. 되돌리기

```bash
# 스테이징 취소 (파일은 유지)
git restore --staged 파일명

# 파일 변경 내용 되돌리기 (주의: 변경 내용 삭제됨)
git restore 파일명

# 마지막 커밋 메시지 수정
git commit --amend -m "수정된 메시지"

# 특정 커밋으로 되돌리기 (새 커밋 생성)
git revert 커밋해시
```

## 7. 임시 저장 (stash)

```bash
# 현재 변경 사항 임시 저장
git stash

# 메시지와 함께 임시 저장
git stash save "작업 설명"

# 임시 저장 목록 확인
git stash list

# 임시 저장 복원
git stash pop

# 특정 stash 복원
git stash pop stash@{번호}
```

## 8. 자주 쓰는 명령어 요약

| 명령어 | 설명 |
|--------|------|
| `git init` | 새 저장소 생성 |
| `git clone URL` | 원격 저장소 복제 |
| `git status` | 현재 상태 확인 |
| `git add .` | 모든 변경 파일 스테이징 |
| `git commit -m "메시지"` | 커밋 |
| `git push` | 원격에 업로드 |
| `git pull` | 원격에서 다운로드 + 병합 |
| `git branch` | 브랜치 목록 |
| `git checkout -b 이름` | 새 브랜치 생성 후 전환 |
| `git merge 이름` | 브랜치 병합 |
| `git log --oneline` | 커밋 이력 간단히 보기 |
| `git stash` | 변경 사항 임시 저장 |
