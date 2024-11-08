---
title: 깃헙 블로그 build시 Can't find stylesheet to import. 오류 수정
description: 
date: 2024-11-08 16:19:00 +09:00
categories: [Blogging, Error]
tags: [블로그 오류]
---

앞서 commit comment문제를 해결하고 push에 성공하면 다음 오류를 만나 된다.

![빌드오류 로그](/assets/img/post/2024-11-08/2024-11-08_build_error_missing_file.jpg){:style="border:1px solid #eaeaea; border-radius: 7px; padding: 0px;" }

```
Error: Can't find stylesheet to import.
  ╷
1 │ @import 'dist/bootstrap';
  │         ^^^^^^^^^^^^^^^^
  ╵
  main.bundle.scss 1:9                                                                             @import
  /home/runner/work/zukajama.github.io/zukajama.github.io/assets/css/jekyll-theme-chirpy.scss 1:9  root stylesheet 
```

즉 github blog jekyll Chirpy 테마의 리소스 build시 bootstrap.scss 파일이 없어서 import 할수 없다고 나는 오류이다.

이것은 내가 다운받아 설치한 깃헙 블로그의 gitignore 파일에서 다음과 같이 해당 폴더를 주석처리하여 저장소에 없는 파일을 추가로 push 하여 해결했다.

![gitignore 파일수정](/assets/img/post/2024-11-08/2024-11-08_fix_gitignore.jpg){:style="border:1px solid #eaeaea; border-radius: 7px; padding: 0px;" }

