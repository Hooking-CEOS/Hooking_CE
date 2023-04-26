# 사용방법

1. clone하여 local에 파일 저장
2. chrome://extensions/ 접속
3. 우측 상단에 개발자 모드 토글하여 on
4. 압축해제된 확장 프로그램 로드 -> HOOKING_CE폴더 선택하여 업로드
5. instagram이나 developer.chrome.com페이지 접속한 후 플러그인 활성화하면 글 제목과 url 확인가능.

# 수정필요

manifest.json에서

```
"host_permissions": ["*://*/*"]
```

를

```
"host_permissions": ["https://www.instagram.com/*"]
```

으로 바꿔야할 것 같음

https://developer.chrome.com/docs/extensions/reference/commands/
단축키 추가

https://developer.chrome.com/docs/extensions/reference/contextMenus/
이건 우클릭했을 때 나오는 메뉴

https://developer.chrome.com/docs/extensions/reference/declarativeContent/
아마도 이게 웹페이지 내용 받아오는 것인듯함

<!-- {
"manifest_version": 3,
"name": "Hooking Chrome Extension",
"description": "Url & Clipboard Fetching Extension",
"version": "1.0",
"action": {
"default_popup": "popup.html",
"default_icon": "dall-e-1.png"
},
"background": {
"service_worker": "background.js"
},
"content_scripts": [
{
"js": ["content.js"],
"matches": ["*://*.instagram.com/*"]
}
],
"host_permissions": ["*://*/*"],
"permissions": ["tabs", "activeTab", "scripting"]
} -->
