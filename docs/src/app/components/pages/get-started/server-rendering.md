## Server Renderingj <br /> 서버 렌더링

When using Material-UI with server rendering, we must use the same environment for the server and the client.
This has two technical implications.

Material-UI를 서버 렌더링과 함께 사용할 때는 서버와 클라이언트에 동일한 환경을 사용해야합니다.
여기에는 두 가지 기술적으로 함축된 의미가 있습니다.

### Autoprefixer <br /> 자동 접두사

First, Material-UI has to use the same user agent for the auto prefixer.
On the client side, the default value is `navigator.userAgent`.
But on the server side, the `navigator` is `undefined`. You need to provide it to Material-UI.

첫째, Material-UI는 자동 접두사에 대해 동일한 사용자 에이전트를 사용해야합니다.
클라이언트 측에서 기본값은 `navigator.userAgent`입니다.
하지만 서버 쪽에서 `navigator`는 `undefined`이므로 Material-UI에 제공해 주어야 합니다.

The `userAgent` can take one of the following values:
- a regular user agent like
`'Mozilla/5.0 (Macintosh; Intel Mac OS X 10_11_2) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/48.0.2564.82 Safari/537.36'`
- `'all'` to prefix for all user agents
- `false` to disable the prefixer

`userAgent`는 다음 값 중 하나를 취할 수 있습니다.
- 일반적인 사용자는 에이전트는 다음과 같습니다.
`'Mozilla/5.0 (Macintosh; Intel Mac OS X 10_11_2) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/48.0.2564.82 Safari/537.36'`
- `'all'` 은 모든 사용자 에이전트에 접두어로 사용
- `false` 는 접두어를 사용하지 않음

We rely on the [muiTheme](/#/customization/themes) context to spread the user agent to all of our component.
For instance, you can provide it like this:

우리는 모든 components에 사용자 에이전트를 전파하기 위해 [muiTheme](/#/customization/themes) 컨텍스트에 의존합니다. 예를 들어 다음과 같이 제공 할 수 있습니다.

```js
import React from 'react';
import getMuiTheme from 'material-ui/styles/getMuiTheme';
import MuiThemeProvider from 'material-ui/styles/MuiThemeProvider';
import {green100, green500, green700} from 'material-ui/styles/colors';

const muiTheme = getMuiTheme({
  palette: {
    primary1Color: green500,
    primary2Color: green700,
    primary3Color: green100,
  },
}, {
  avatar: {
    borderColor: null,
  },
  userAgent: req.headers['user-agent'],
});

const Main = () => (
  <MuiThemeProvider muiTheme={muiTheme}>
    <div>Hello world</div>
  </MuiThemeProvider>
);

export default Main;
```

### process.env.NODE_ENV

You also need to use the **same** `process.env.NODE_ENV` between the client side and server side.
Otherwise, the checksums won't match.

또한 클라이언트 측과 서버 측간에 **동일한** `process.env.NODE_ENV`를 사용해야합니다. 그렇지 않으면 체크섬이 일치하지 않습니다.

We run some style integrity check in the development environment.
So in production, make sure you are setting `process.env.NODE_ENV` to `'production'`
in order to **speed-up** the style computation.

우리는 개발 환경에서 몇 가지 스타일 무결성 검사를 실행합니다. 프로덕션에서는 스타일 계산 **속도를 높이기** 위해 `process.env.NODE_ENV`를 `'production'`으로 설정해야합니다.
