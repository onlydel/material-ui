## Usage <br /> 사용법

Beginning with v0.15.0, Material-UI components require a theme to be provided. The quickest way to get up and running is by using the `MuiThemeProvider` to inject the theme into your application context. Following that, you can use any of the components as demonstrated in our documentation.

v0.15.0부터, Material-UI component에는 테마를 지정해주어야 합니다. 시작하고 실행하는 가장 빠른 방법은 `MuiThemeProvider`를 사용하여 응용 프로그램 컨텍스트에 테마를 삽입하는 것입니다. 그런 다음 설명서에 나와있는 구성 요소 중 하나를 사용할 수 있습니다.

Here is a quick example to get you started:

다음은 시작하기 위한 간단한 예입니다:


**./App.js**
```jsx
import React from 'react';
import ReactDOM from 'react-dom';
import MuiThemeProvider from 'material-ui/styles/MuiThemeProvider';
import MyAwesomeReactComponent from './MyAwesomeReactComponent';

const App = () => (
  <MuiThemeProvider>
    <MyAwesomeReactComponent />
  </MuiThemeProvider>
);

ReactDOM.render(
  <App />,
  document.getElementById('app')
);
```

**./MyAwesomeReactComponent.js**
```jsx
import React from 'react';
import RaisedButton from 'material-ui/RaisedButton';

const MyAwesomeReactComponent = () => (
  <RaisedButton label="Default" />
);

export default MyAwesomeReactComponent;
```

Please refer to each component's documentation page to see how they should be imported.

import 방법을 보려면 각 component의 설명서 페이지를 참조하십시오.

Notice that in the above example, we used:

위의 예제에서는 다음과 같이 사용했습니다.
```js
import RaisedButton from 'material-ui/RaisedButton';
```

instead of

이렇게 사용하는 대신에 말입니다.
```js
import {RaisedButton} from 'material-ui';
```

This will make your build process faster and your build output smaller.
For a complete mapping of Material-UI components to `import`,
see [`/src/index.js`](https://github.com/callemall/material-ui/blob/master/src/index.js) inside the Material-UI npm package root directory.

이렇게하면 빌드 프로세스가 빨라지고 빌드 출력이 더 작아집니다.
`import`할 Material-UI components의 전체 매핑은 Material-UI npm 패키지 루트 디렉토리의
[`/src/index.js`](https://github.com/callemall/material-ui/blob/master/src/index.js)를 참조하십시오.


### Customization <br/> 사용자 정의

We have implemented a default theme to render all Material-UI components.
Styling components to your liking is simple and hassle-free.
This can be achieved in the following two ways:
- [With the theme](#/customization/themes), you can use a custom theme to style components.
- [With the inline style](#/customization/styles), you can override individual
component styles via the style property.

모든 Material-UI components를 렌더링하기 위해 기본 테마를 구현했습니다. 원하는대로 components를 스타일링하는 것은 간단하고 번거롭지 않습니다. 이것은 다음 두 가지 방법으로 수행 할 수 있습니다.
- [테마를 사용하여](#/customization/themes), 사용자 정의 테마를 사용하여 components를 스타일화할 수 있습니다.
- [인라인 스타일을 사용하여](#/customization/styles), style 속성을 통해 개별 component 스타일을 재정의 할 수 있습니다.
