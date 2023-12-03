---
title: Favicon 사용자 정의
author: cotes
date: 2023-11-29 00:34:00 +0900
categories: [Blog, Writing]
tags: [favicon]
published: false
---

[**Chirpy**](https://github.com/cotes2020/jekyll-theme-chirpy/)의 [favicons](https://www.favicon-generator.org/about/)은 `assets/img/favicons/`{: .filepath}디렉토리에 위치합니다. 여러분은 여러분만의 이미지로 대체하고 싶을 것입니다. 다음 섹션에서는 기본 파비콘을 생성하고 대체하는 방법을 안내합니다.

## 파비콘 생성

512x512 또는 그 이상의 크기로 정사각형 이미지 (PNG, JPG 또는 SVG)를 준비한 다음 온라인 도구 [**Real Favicon Generator**](https://realfavicongenerator.net/)로 이동하고 <kbd>Select your Favicon image</kbd>버튼을 클릭하여 이미지 파일을 업로드하십시오.

다음 단계에서는 웹 페이지가 모든 사용 시나리오를 표시합니다. 기본 옵션을 유지하고 페이지 맨 아래로 스크롤한 다음 <kbd>Generate your Favicons and HTML code</kbd> 버튼을 클릭하여 파비콘을 생성합니다.

## 다운로드 및 교체

생성된 패키지를 다운로드하고 압축을 푼 후 다음 두 파일을 삭제하십시오:

- `browserconfig.xml`{: .filepath}
- `site.webmanifest`{: .filepath}

그런 다음 나머지 이미지 파일 (`.PNG`{: .filepath} and `.ICO`{: .filepath})을 Jekyll 사이트의 `assets/img/favicons/`{: .filepath} 디렉토리에 있는 원본 파일을 덮어씁니다. Jekyll 사이트에 이 디렉토리가 아직 없다면 디렉토리를 만들어주세요.

다음 표는 여러분이 파비콘 파일에 대한 변경 사항을 이해하는 데 도움이 될 것입니다:

| File(s)             | From Online Tool                  | From Chirpy |
|---------------------|:---------------------------------:|:-----------:|
| `*.PNG`             | ✓                                 | ✗           |
| `*.ICO`             | ✓                                 | ✗           |

>  ✓는 유지, ✗는 삭제를 의미합니다.
{: .prompt-info }

다음으로 사이트를 빌드할 때, 파비콘은 사용자 정의 버전으로 교체될 것입니다.