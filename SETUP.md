# 로컬 개발 환경 설정 가이드

Windows에서 Jekyll 사이트를 로컬에서 테스트하기 위한 환경 설정 가이드입니다.

## 1단계: Ruby 설치

### RubyInstaller 다운로드 및 설치

1. [RubyInstaller 다운로드 페이지](https://rubyinstaller.org/downloads/)로 이동합니다.
2. **Ruby+Devkit** 버전을 다운로드합니다 (권장: Ruby 3.2.x 또는 3.3.x)
   - 예: `rubyinstaller-devkit-3.2.6-1-x64.exe`
3. 다운로드한 설치 파일을 실행합니다.
4. 설치 중 다음 옵션을 선택합니다:
   - ✅ "Add Ruby executables to your PATH" 체크
   - ✅ "Associate .rb and .rbw files with this Ruby installation" 체크
5. 설치 완료 후 **"Run 'ridk install'"** 옵션을 선택하여 개발 도구를 설치합니다.
6. 명령 프롬프트가 열리면 `3`을 입력하여 MSYS2와 MINGW 개발 도구를 설치합니다.

### 설치 확인

새로운 PowerShell 또는 명령 프롬프트를 열고 다음 명령어로 확인합니다:

```powershell
ruby --version
```

출력 예시: `ruby 3.2.6 (2024-xx-xx) [x64-mingw-ucrt]`

## 2단계: Jekyll 및 Bundler 설치

PowerShell에서 다음 명령어를 실행합니다:

```powershell
gem install jekyll bundler
```

설치 확인:

```powershell
jekyll --version
bundle --version
```

## 3단계: 프로젝트 의존성 설치

프로젝트 디렉토리에서 다음 명령어를 실행합니다:

```powershell
cd C:\git\Seong-Yong-Park.github.io
bundle install
```

## 4단계: 로컬 서버 실행

다음 명령어로 로컬 서버를 시작합니다:

```powershell
bundle exec jekyll serve
```

서버가 시작되면 다음 메시지가 표시됩니다:

```
Server address: http://127.0.0.1:4000/
Server running... press ctrl-c to stop.
```

브라우저에서 `http://localhost:4000`으로 접속하여 사이트를 확인할 수 있습니다.

## 문제 해결

### "gem install" 오류가 발생하는 경우

RubyInstaller의 Devkit이 제대로 설치되지 않았을 수 있습니다. 다음을 시도해보세요:

```powershell
ridk install
```

그리고 다시 `gem install jekyll bundler`를 실행합니다.

### 포트 4000이 이미 사용 중인 경우

다른 포트를 사용할 수 있습니다:

```powershell
bundle exec jekyll serve --port 4001
```

### 파일 변경이 감지되지 않는 경우

Windows에서 파일 감지 문제가 있을 수 있습니다. `_config.yml`에 다음을 추가하세요:

```yaml
force_polling: true
```

## 유용한 명령어

- **서버 중지**: `Ctrl + C`
- **빌드만 실행** (서버 없이): `bundle exec jekyll build`
- **프로덕션 모드로 실행**: `JEKYLL_ENV=production bundle exec jekyll serve`

## 참고 자료

- [Jekyll 공식 문서](https://jekyllrb.com/docs/)
- [RubyInstaller 공식 사이트](https://rubyinstaller.org/)
- [GitHub Pages 로컬 테스트](https://docs.github.com/en/pages/setting-up-a-github-pages-site-with-jekyll/testing-your-github-pages-site-locally-with-jekyll)

