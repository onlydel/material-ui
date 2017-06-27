## Required Knowledge 필수 지식

We recommend that you get to know [React](http://facebook.github.io/react/)
before diving into Material-UI.
Material-UI is a set of React components,
so understanding how React fits into web development is important.

Material-UI로 들어가기 전에 [React](http://facebook.github.io/react/)를
아는 것이 좋습니다.
Material-UI는 React 컴포넌트 집합이므로 React가 웹 개발에 어떻게 적용되는지
이해하는 것이 중요합니다.

If you're already familiar with single page applications (SPAs) and Node,
feel free to skip this section and
head straight to the [installation](#/get-started/installation) part.

단일 페이지 응용 프로그램 (SPA) 및
Node에 이미 익숙한 경우이 섹션을 건너 뛰고
[설치](#/get-started/installation) 부분으로 바로 이동하세요.

Otherwise, what follows is a brief introduction to SPAs and Node.
You'll find this helpful, especially if you have limited prior experience
with web development,
or if your experience only consists of "traditional" websites built using
HTML, CSS and some JavaScript.

아래는 SPA 및 Node에 대한 간략한 소개입니다.
이 기능은 특히 웹 개발 경험이 제한적이거나 HTML, CSS 및 일부 JavaScript를 사용하여 작성된
"전통적"웹 사이트로만 이루어진 경우 유용합니다.

### Single Page Applications

A long(?) time ago, websites were built using static pages in HTML,
with CSS used for styling,
and JavaScript used to support user interactions or for animations.
Most client interactions, especially those that acted on data,
involved complete server round-trips:
data from the client was sent to the server where it was processed,
and then the result was sent back to the client.
Moreover, most of this communication was "blocking".
That is, during these round-trips, the client was busy and could not be interacted with.

옛날 옛적(?)에, 웹 사이트는 HTML의 정적 페이지와 스타일을 지정하는데 사용된 CSS 및 사용자 상호 작용이나 애니메이션을 지원하는데 사용되는 JavaScript를 사용하여 제작되었습니다. 대부분의 클라이언트 상호 작용, 특히 데이터에 영향을주는 클라이언트 상호 작용은 완전한 서버 왕복과 관련이 있습니다. 클라이언트의 데이터가 처리 된 서버로 전송 된 다음 결과가 클라이언트로 다시 전송되었습니다. 더욱이 이 통신의 대부분은 "차단"되었습니다. 즉, 이러한 왕복 중 클라이언트가 사용 중이었고 상호 작용할 수 없었습니다.

With the advent of asynchronous server calls (AJAX),
the client could now do other things while
it sent data to the server and awaited a response.
However, most client interactions still needed server round-trips,
and websites just didn’t
feel as fluid and responsive as, say, native desktop apps. That's why SPAs came into being.

비동기 서버 호출 (AJAX)의 출현으로 클라이언트는 이제 데이터를 서버로 보내고 응답을 기다리는 동안 다른 일을 할 수있었습니다. 그러나 대부분의 클라이언트 상호 작용에는 여전히 서버 왕복이 필요했으며 웹 사이트는 네이티브 데스크톱 응용 프로그램처럼 유동적이고 반응이 좋지 않았습니다. 그래서 SPA가 생겨났습니다.

An SPA is a "website" that essentially consists of a single page.
That is, the whole website lives in a single file (usually a JavaScript file)
that is sent from the server to the client once.
Most of the logic to handle client interactions lives in that single file.
Hence, everything that's necessary to provide a fluid, responsive, and fast web
experience is present in the browser’s memory.
This web programming architecture has gained tremendous traction in the last decade,
with many popular JavaScript presentation frameworks geared towards SPAs:
- [Angular](https://angularjs.org)
- [Ember](http://emberjs.com/)
- [Backbone](http://backbonejs.org)
- [React](http://facebook.github.io/react/)

SPA는 본질적으로 단일 페이지로 구성된 "웹 사이트"입니다. 즉, 전체 웹 사이트는 서버에서 클라이언트로 한 번 전송되는 단일 파일 (일반적으로 JavaScript 파일)에 있습니다. 클라이언트 상호 작용을 처리하는 대부분의 논리는 단일 파일에 있습니다. 따라서 유동적이고 반응이 빠르며 빠른 웹 경험을 제공하는 데 필요한 모든 것이 브라우저의 메모리에 있습니다. 이 웹 프로그래밍 아키텍처는 지난 10 년 동안 SPA를위한 많은 JavaScript 프리젠 테이션 프레임 워크를 통해 엄청난 호응을 얻었습니다.
- [Angular](https://angularjs.org)
- [Ember](http://emberjs.com/)
- [Backbone](http://backbonejs.org)
- [React](http://facebook.github.io/react/)


Including all of the code for a website in a single file creates significant code organization
challenges.
Thankfully, there are several tools that allow us to break up our code into smaller
modules (similar to breaking down an object-oriented application into different classes
and interfaces) that can be bundled together later.
This is where Node comes into play.

웹 사이트 코드를 모두 하나의 파일에 포함시키는 것은 코드 조직의 중요한 과제를 야기합니다. 고맙게도, 나중에 함께 묶을 수있는 작은 모듈 (객체 지향 응용 프로그램을 여러 클래스와 인터페이스로 분리하는 것과 비슷한)로 코드를 분해 할 수있는 몇 가지 도구가 있습니다. 이것은 Node가 나오는 곳입니다.

### Node

At its core, [Node](https://nodejs.org) is a program written in C++ that allows us
to run JavaScript in the shell (yes, your terminal, not the browser).
To do this, It uses Chrome’s V8 JavaScript engine.
Hence, Node is essentially a runtime environment.

핵심적으로 Node는 C ++로 작성된 프로그램으로 쉘 (예 : 브라우저가 아닌 터미널)에서 JavaScript를 실행할 수있게 해줍니다. 이를 위해 Chrome의 V8 JavaScript 엔진을 사용합니다. 따라서 Node는 본질적으로 런타임 환경입니다.

When it was first created, Node was primarily targeted towards developing web servers in
JavaScript.
This was somewhat radical since JavaScript has traditionally been restricted to the client.
However, over time, web developers recognized the benefits of using Node for tooling and
dependency management, and created projects like:
- [Grunt](http://gruntjs.com/)
- [Gulp](http://gulpjs.com/)
- [Browserify](http://browserify.org)
- [Webpack](http://webpack.github.io)

처음 만들어 졌을 때, Node는 주로 자바 스크립트로 웹 서버를 개발하는 것을 목표로 삼았습니다. JavaScript는 전통적으로 클라이언트에만 국한되어 왔기 때문에 다소 과격했습니다. 그러나 시간이 지남에 따라 웹 개발자는 도구 및 종속성 관리를 위해 노드를 사용할 때의 이점을 인식하고 다음과 같은 프로젝트를 만들었습니다.
- [Grunt](http://gruntjs.com/)
- [Gulp](http://gulpjs.com/)
- [Browserify](http://browserify.org)
- [Webpack](http://webpack.github.io)

As Node became popular, independent developers and organizations wrote scripts
(that ran using Node) to do almost everything web apps-related.
Of course, the whole community could benefit from these "custom Node scripts."
This called for some kind of package repository where anybody could upload their Node scripts, and other developers
could use these scripts in their own projects.

Node가 대중화되면서 독립적 인 개발자와 조직은 거의 모든 웹 앱 관련 작업을 수행하기 위해 노드를 사용하여 실행 한 스크립트를 작성했습니다. 물론 전체 커뮤니티가 이러한 "사용자 정의 노드 스크립트"를 활용할 수 있습니다. 이것은 누군가가 자신의 Node 스크립트를 업로드 할 수있는 일종의 패키지 저장소를 요구했고, 다른 개발자들은 자신의 프로젝트에서이 스크립트를 사용할 수있었습니다.

[Node Package Manager](https://www.npmjs.com/), better known as “npm,” does exactly that.
npm is a command line tool that, among other things, can be used to incorporate external JavaScript into one's own project.
Material-UI, for instance, is available as a package through npm.
This means that you can include Material-UI in your project by simply running
`npm install material-ui` from your project’s directory,
and then using the components of Material-UI that you need.

"npm"이라고 더 잘 알려진 [Node Package Manager](https://www.npmjs.com/)는 정확히 그 역할을 수행합니다. npm은 다른 것들 중에서도 외부 JavaScript를 자신의 프로젝트에 통합하는 데 사용할 수있는 명령 줄 도구입니다. 예를 들어 Material-UI는 npm을 통해 패키지로 제공됩니다. 즉, 프로젝트 디렉토리에서 `npm install material-ui`를 실행 한 다음 필요한 Material-UI의 구성 요소를 사용하여 Material-UI를 프로젝트에 포함시킬 수 있습니다.

That's it for a quick introduction!
If you feel like you need more of Node, we recommend that you consult
some quick tutorials online before jumping into Material-UI.
This [blog post](http://openmymind.net/2012/2/3/Node-Require-and-Exports/) and
[video](https://www.youtube.com/watch?v=pU9Q6oiQNd0) are good starting points.

빠른 소개입니다. Node가 더 필요하다고 생각되면 Material-UI로 이동하기 전에 온라인에서 빠른 자습서를 참조하는 것이 좋습니다. 이 [블로그 게시물](http://openmymind.net/2012/2/3/Node-Require-and-Exports/)과 [비디오](https://www.youtube.com/watch?v=pU9Q6oiQNd0)는 좋은 출발점입니다.
