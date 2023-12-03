---
title: 블로그를 시작해봅니다 
author: cotes
date: 2023-11-26 13:35:00 +0900
categories: [Blog, Writing]
tags: [getting started]
img_path: '/posts/20180809'
published: false
---

아 여기까지 오기도 정말 힘들었네요..

## 전제조건

기본 환경 설치를 완료하려면 [Jekyll Docs](https://jekyllrb.com/docs/installation/) 의 지침을 따르세요.
 [Git](https://git-scm.com/) 도 설치해야 합니다.

## 설치

### 새 사이트 만들기

이 테마에 대한 새 저장소를 만드는 방법에는 두 가지가 있습니다.:

- [**Chirpy Starter 사용**](#option-1-using-the-chirpy-starter) - 업그레이드가 쉽고 관련 없는 프로젝트 파일을 격리하여 글쓰기에 집중할 수 있습니다.
- [**GitHub Fork**](#option-2-github-fork) - 맞춤형 개발에는 편리하지만 업그레이드가 어렵습니다. Jekyll에 익숙하지 않고 이 프로젝트를 수정하거나 기여할 생각이 없다면 이 접근 방식은 권장되지 않습니다.

#### 옵션 1. Chirpy Starter 사용

GitHub에 로그인하고 [**Chirpy Starter**][starter] 로 이동한 후, <kbd>Use this template</kbd> > <kbd>Create a new repository</kbd> 버튼을 클릭하여 새로운 저장소를 만들고 저장소의 이름을 당신의 깃허브 `USERNAME`을 나타내는 `USERNAME.github.io`로 지정합니다.

#### 옵션 2. GitHub 포크

GitHub에 로그인하여  [fork **Chirpy**](https://github.com/cotes2020/jekyll-theme-chirpy/fork)한 다음 저장소 이름을 `USERNAME.github.io` ( 당신의 깃허브 `USERNAME`)변경합니다.

그리고 로컬 머신에서 저장소를 클론합니다. 나중에 JavaScript 파일을 빌드하려면 [Node.js][nodejs], 설치하고 다음 명령을 실행합니다.

```console
$ bash tools/init
```

> 만약 GitHub Pages에 사이트를 배포하지 않을 경우, 위 명령의 끝에 `--no-gh` 옵션을 추가하십시오..
{: .prompt-info }

이 명령은 다음을 수행합니다.

1. [latest tag][latest-tag]로 코드를 확인합니다. (기본 브랜치의 코드는 개발 중이므로 안정성을 보장하기 위해 최신 태그로 이동).
2. 비필요한 샘플 파일을 제거하고 GitHub 관련 파일을 처리합니다.
3. JavaScript 파일을 빌드하고 `assets/js/dist/`{: .filepath }에 내보내어 Git으로 추적되도록 만듭니다.
4. 위의 변경 사항을 저장하기 위해 자동으로 새로운 커밋을 만듭니다.

### 의존성 설치

처음으로 로컬 서버를 실행하기 전에 사이트의 루트 디렉토리로 이동하고 다음 명령을 실행하십시오.

```console
$ bundle
```

## 사용법

### 구성


필요에 따라 `_config.yml`{: .filepath} 파일의 변수를 업데이트하십시오. 일부는 전형적인 옵션입니다.

- `url`
- `avatar`
- `timezone`
- `lang`

### 소셜 연락처 옵션

소셜 연락처 옵션은 사이드바 아래에 표시됩니다. `_data/contact.yml`{: .filepath } 파일에서 지정된 연락처를 켜거나 끌 수 있습니다.

### 스타일시트 사용자 정의

스타일시트를 사용자 정의해야 하는 경우, 테마의 `assets/css/jekyll-theme-chirpy.scss`{: .filepath} 파일을 Jekyll 사이트의 동일한 경로로 복사하고 그 끝에 사용자 정의 스타일을 추가하십시오.

버전 `6.2.0`부터, `_sass/addon/variables.scss`{: .filepath}에 정의된 SASS 변수를 덮어쓰려면, 테마의 주 SCSS 파일 `_sass/main.scss`{: .filepath}를 Jekyll 사이트 소스의 `_sass`{: .filepath} 렉토리로 복사한 다음 새로운 파일 `_sass/variables-hook.scss`{: .filepath} 를 만들어 새 값을 할당하십시오.

### 정적 자산 사용자 정의

버전 `5.1.0` 에서 정적 자산 구성이 소개되었습니다. 정적 자산의 CDN은 파일 `_data/origin/cors.yml`{: .filepath }에 정의되어 있으며, 샤이트가 게시된 지역의 네트워크 조건에 따라 일부를 대체할 수 있습니다.

또한 정적 자산을 자체 호스팅하려면 [_chirpy-static-assets_](https://github.com/cotes2020/chirpy-static-assets#readme)를 참조하십시오.

### 로컬 서버 시작

게시 전에 사이트 내용을 미리보려면 다음 명령을 실행하십시오.

```console
$ bundle exec jekyll s
```

몇 초 후에 로컬 서비스가 _<http://127.0.0.1:4000>_ 게시됩니다.

## 배포

배포를 시작하기 전에 `_config.yml`{: .filepath} 파일을 확인하고 `url` 이 올바르게 구성되어 있는지 확인하십시오. 또한 [**project site**](https://help.github.com/en/github/working-with-github-pages/about-github-pages#types-of-github-pages-sites) 를 선호하고 사용자 정의 도메인을 사용하지 않거나, **GitHub Pages**이외의 웹 서버에서 웹 사이트에 기본 URL로 방문하려는 경우, `baseurl` 을 슬래시로 시작하는 프로젝트 이름으로 변경하십시오. ex : `/project-name`.

이제 Jekyll 사이트를 배포하는 하나의 방법을 선택할 수 있습니다.

### GitHub Actions를 사용하여 배포

준비해야 할 몇 가지 사항이 있습니다.

- GitHub Free 플랜을 사용 중이라면 사이트 저장소를 공개 상태로 유지합니다.
- 저장소에 `Gemfile.lock`{: .filepath} 파일이 커밋되어 있고 로컬 머신이 Linux를 실행 중이 아닌 경우, 사이트 루트로 이동하여 lock 파일의 플랫폼 목록을 업데이트합니다.

  ```console
  $ bundle lock --add-platform x86_64-linux
  ```

그 다음, Pages 서비스를 구성합니다.

1. GitHub에서 저장소로 이동합니다. _Settings_ 탭을 선택한 다음 왼쪽 탐색 모음에서 _Pages_ 를 클릭합니다. 그런 다음 **Source** 섹션(_Build 및  deployment_ 아래)의 드롭다운 메뉴에서 [**GitHub Actions**][pages-workflow-src] 를 선택합니다. 
![Build source](pages-source-light.png){: .light .border .normal w='375' h='140' }
![Build source](pages-source-dark.png){: .dark .normal w='375' h='140' }

2. GitHub에 커밋을 푸시하여 Actions 워크플로우를 트리거합니다. 저장소의 Actions 탭에서 Build and Deploy 워크플로우가 실행되는 것을 볼 수 있어야 합니다. 빌드가 완료되고 성공하면 사이트가 자동으로 배포됩니다.

이 시점에서 GitHub에서 제시된 URL로 이동하여 사이트에 액세스할 수 있습니다.

### 수동으로 빌드 및 배포

자체 호스팅된 서버에서는 **GitHub Actions**의 편리함을 누릴 수 없습니다. 따라서 로컬 머신에서 사이트를 빌드한 다음 사이트 파일을 서버에 업로드해야 합니다.

소스 프로젝트의 루트로 이동하고 다음과 같이 사이트를 빌드합니다.

```console
$ JEKYLL_ENV=production bundle exec jekyll b
```

출력 경로를 지정하지 않은 경우 생성된 사이트 파일은 프로젝트의 루트 디렉토리의 `_site`{: .filepath} 폴더에 위치합니다. 이제 이러한 파일을 대상 서버에 업로드해야 합니다.

[nodejs]: https://nodejs.org/
[starter]: https://github.com/cotes2020/chirpy-starter
[pages-workflow-src]: https://docs.github.com/en/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site#publishing-with-a-custom-github-actions-workflow
[latest-tag]: https://github.com/cotes2020/jekyll-theme-chirpy/tags