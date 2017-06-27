## Installation

Material-UI is available as an [npm package](https://www.npmjs.org/package/material-ui).

Material-UI는 [npm 패키지](https://www.npmjs.org/package/material-ui)로 제공됩니다.


### react-tap-event-plugin

Our components use [react-tap-event-plugin](https://github.com/zilverline/react-tap-event-plugin)
to listen for touch / tap / clickevents.
This dependency is temporary and will go away once the official React version is released.
Until then, be sure to inject this plugin at the start of your app.

우리의 구성 요소는 터치 / 탭 / 클릭이벤트를 듣기 위해 [react-tap-event-plugin](https://github.com/zilverline/react-tap-event-plugin)을 사용합니다.
이 종속성은 일시적이며 공식 React 버전이 출시되면 사라집니다. 그때까지 앱 시작시 이 플러그인을 삽입해야합니다.


```js
import injectTapEventPlugin from 'react-tap-event-plugin';

// Needed for onTouchTap
// http://stackoverflow.com/a/34015469/988941
injectTapEventPlugin();
```

`react-tap-event-plugin` provides `onTouchTap()` to all React Components.
It's a mobile-friendly `onClick()` alternative for components in Material-UI, especially useful for the buttons.

`react-tap-event-plugin`은 모든 React 구성 요소에 `onTouchTap()`을 제공합니다. 머티리얼 UI의 구성 요소에 대한 모바일 친화적 인 `onClick()` 대체 기능으로 특히 버튼에 유용합니다.


### Roboto Font

Material-UI was designed with the [Roboto](http://www.google.com/fonts/specimen/Roboto)
font in mind.
So be sure to include it in your project.
Here are [some instructions](http://www.google.com/fonts#UsePlace:use/Collection:Roboto:400,300,500)
on how to do so.

Material-UI는 [Roboto](http://www.google.com/fonts/specimen/Roboto)
글꼴을 염두에두고 고안되었습니다.
따라서 프로젝트에 반드시 포함 시키십시오.
그렇게하는 [방법에 대한 지침](http://www.google.com/fonts#UsePlace:use/Collection:Roboto:400,300,500)이 있습니다.

### ES Compiling

The examples in this documentation use the ```stage-1``` features of the ECMAScript specification. Be sure if you are testing these examples in your own project that you have the proper plugins installed in your compiler. Here are [some instructions](http://babeljs.io/docs/plugins/preset-stage-1/) on how to install the plugin for Babel.

이 문서의 예제는 ECMAScript 사양의 ```stage-1``` 기능을 사용합니다.
컴파일러에 적절한 플러그인이 설치되어 있는 자신의 프로젝트에서 이 예제를 테스트하고 있는지 확인하십시오.
다음은 Babel용 플러그인을
[설치하는 방법에 대한 설명](http://babeljs.io/docs/plugins/preset-stage-1/)입니다.
