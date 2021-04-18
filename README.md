# Complete React Developer in 2021 (w/ Redux, Hooks, GraphQL)

## Section 3: React Basics

### 14. Section Overview

<https://reactjs.org/docs/create-a-new-react-app.html>
<https://nodejs.org/en/>
<https://github.com/nvm-sh/nvm>
<https://codesandbox.io/s/new>

### 20. Create React App

<https://zhangmyihua.github.io/monsters-rolodex/>
<https://create-react-app.dev/docs/getting-started/>

```bash
buildah -f Dockerfile.localcreatereactapp bud -t node-dev-image
podman run -it --rm --name nodedev -v $(pwd):/app node-dev-image node -v
podman run -it --rm --name nodedev -v $(pwd):/app node-dev-image npm -v
podman run -it --rm --name nodedev -v $(pwd):/app node-dev-image npx create-react-app monsters-rolodex

podman run -it --rm --name nodedev -v $(pwd):/app  node-dev-image npx create-react-app monsters-rolodex 

buildah --layers=true -f Dockerfile.local bud -t monsters-rolodex-image

podman run -it --rm --name monsters-rolodex monsters-rolodex-image /bin/sh
podman run -it --rm --name monsters-rolodex -p 3000:3000 monsters-rolodex-image npm start

podman run -it --rm --name monsters-rolodex -v $(pwd):/app -p 3000:3000 monsters-rolodex-image npm start

 podman run -d --rm --name monsters-rolodex -v $(pwd)/public:/monsters-rolodex/public -v $(pwd)/src:/monsters-rollodex/src -p 3000:3000 -e CHOKIDAR_USEPOLLING=true monsters-rolodex-image npm start


 ---
 podman run --name mynginx1 -p 8080:80 -d nginx

 // this works
 podman run --name mynginx2 --mount type=bind,source=$(pwd)/content,target=/usr/share/nginx/html -p 9080:80 -d nginx

// this works as well
podman run -dit --volume $(pwd)/src:/dest:z busybox
podman exec cb4 touch /dest/file
touch src/file2
podman exec cb4 ls /dest/
// gives file and files 2


podman run -d --rm --name monsters-rolodex --mount type=bind,source=$(pwd)/public,target=/monsters-rolodex/public --mount type=bind,source=$(pwd)/src,target=/monsters-rollodex/src -p 3000:3000 -e CHOKIDAR_USEPOLLING=true monsters-rolodex-image npm start

podman run -d --rm --name monsters-rolodex -v $(pwd)/public:/monsters-rollodex/public:Z -v $(pwd)/src:/monsters-rollodex/src:Z -p 3000:3000 -e CHOKIDAR_USEPOLLING=true monsters-rolodex-image npm start


podman run --name busybox -dit -v $(pwd)/src:/dest/src:z -v $(pwd)/public:/dest/public busybox
podman exec busybox ls /dest/

// this works
podman run -it --rm --name monsters-rolodex -v $(pwd)/public:/monsters-rolodex/public:z -v $(pwd)/src:/monsters-rolodex/src:z -p 3000:3000 -e CHOKIDAR_USEPOLLING=true monsters-rolodex-image ls /monsters-rolodex

podman run -d --rm --name monsters-rolodex -v $(pwd)/public:/monsters-rolodex/public:z -v $(pwd)/src:/monsters-rolodex/src:z -p 3000:3000 -e CHOKIDAR_USEPOLLING=true monsters-rolodex-image npm start


/mnt/d/dev/CompleteReactDeveloperIn2021/Section3-React-Basics/monsters-rolodex

mkdir build

podman run -d --rm --name monsters-rolodex -v $(pwd)/public:/monsters-rolodex/public:z -v $(pwd)/src:/monsters-rolodex/src:z -v $(pwd)/build:/monsters-rolodex/build:z -p 3000:3000 -e CHOKIDAR_USEPOLLING=true monsters-rolodex-image npm run build


```

### 24. Class Components

<https://reactjs.org/docs/react-component.html>

```bash
cd /mnt/d/dev/CompleteReactDeveloperIn2021/Section3-React-Basics/monsters-rolodex
podman run -d --rm --name monsters-rolodex -v $(pwd)/public:/monsters-rolodex/public:z -v $(pwd)/src:/monsters-rolodex/src:z -p 3000:3000 -e CHOKIDAR_USEPOLLING=true monsters-rolodex-image npm start

```

### 25. Thinking In JSX

### 26. Dynamic Content

state, Map , key

Anytime you use the map() function inside of render, or you have a list of the same jsx elements one after another, they need a key attribute

```react
this.state.monsters.map(monster => 
                <h1 key={monster.id}>{monster.name}</h1>)
```

### 28. Single Page Application

<https://jsonplaceholder.typicode.com/users>
<https://www.w3schools.com/whatis/whatis_json.asp>

### 29. Fetching content

Lifecycle Methods, componentDidMount, fetch

```bash
cd /mnt/d/dev/CompleteReactDeveloperIn2021/Section3-React-Basics/monsters-rolodex
podman run -d --rm --name monsters-rolodex -v $(pwd)/public:/monsters-rolodex/public:z -v $(pwd)/src:/monsters-rolodex/src:z -p 3000:3000 -e CHOKIDAR_USEPOLLING=true monsters-rolodex-image npm start
```

### 32. Card List Component

CSS Grid, components, props children
<https://css-tricks.com/snippets/css/complete-guide-grid/>
<https://gridbyexample.com/what/>

### 34. Card Component

<https://robohash.org/1?set=set2>

### 36. State vs Props

### 37. SearchField State

setState second argument -> callback
<https://reactjs.org/docs/react-component.html#setstate>

### 38. React Events

<https://www.w3schools.com/jsref/event_onchange.asp>
<https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Building_blocks/Events>
<https://reactjs.org/docs/events.html>

### 39. Filtering State

Destructuring `const { monsters, searchField } = this.state;`

<https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Destructuring_assignment#object_destructuring>

### 41. Search Box Component

functional component

### 43. Class Methods and Arrow Functions

<https://reactjs.org/docs/handling-events.html>

Use arrow functions on any class methods you define and aren't part of React (i.e. render(), componentDidMount()).


set this context
`this.handleChange = this.handleChange.bind(this);`
or
`handleChange = (e) => {`

```bash
cd /mnt/d/dev/CompleteReactDeveloperIn2021/Section3-React-Basics/monsters-rolodex
podman run -d --rm --name monsters-rolodex -v $(pwd)/public:/monsters-rolodex/public:z -v $(pwd)/src:/monsters-rolodex/src:z -p 3000:3000 -e CHOKIDAR_USEPOLLING=true monsters-rolodex-image npm start
```

### 47. Optional: Connecting With SSH To Github

<https://docs.github.com/en/github/getting-started-with-github/about-remote-repositories>
<https://docs.github.com/en/enterprise/2.15/user/articles/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent>

### 48. Deploying Our App

<https://github.com/ZhangMYihua/monsters-rolodex-complete>
<https://fonts.google.com/?query=bigelow+rules&selection.family=Bigelow+Rules>
<https://dev.to/yuribenjamin/how-to-deploy-react-app-in-github-pages-2a1f>

```bash
cd /mnt/d/dev/CompleteReactDeveloperIn2021/Section3-React-Basics/monsters-rolodex
podman run -d --rm --name monsters-rolodex -v $(pwd)/public:/monsters-rolodex/public:z -v $(pwd)/src:/monsters-rolodex/src:z -p 3000:3000 -e CHOKIDAR_USEPOLLING=true monsters-rolodex-image npm start

buildah --layers=true -f Dockerfile.local bud -t monsters-rolodex-image

podman run -it --rm --name monsters-rolodex -v $(pwd)/public:/monsters-rolodex/public:z -v $(pwd)/src:/monsters-rolodex/src:z -p 3000:3000 -e CHOKIDAR_USEPOLLING=true monsters-rolodex-image npm run deploy

https://ericsoucy.github.io/CompleteReactDeveloperIn2021-Section3-React-Basics/index.html
```

### 50. React and ReactDOM

<https://unpkg.com/react@17.0.2/umd/react.development.js>
<https://unpkg.com/react-dom@17.0.2/umd/react-dom.development.js>

### 51. Latest React Package Updates

```bash
cd /mnt/d/dev/CompleteReactDeveloperIn2021/Section3-React-Basics/monsters-rolodex
podman run -it --rm --name monsters-rolodex -v $(pwd)/public:/monsters-rolodex/public:z -v $(pwd)/src:/monsters-rolodex/src:z -p 3000:3000 -e CHOKIDAR_USEPOLLING=true monsters-rolodex-image npm list react react-dom react-scripts
```

### 52. Revisiting VirtualDOM + Unidirectional Data Flow

```bash
cd /mnt/d/dev/CompleteReactDeveloperIn2021/Section3-React-Basics/monsters-rolodex
podman run -d --rm --name monsters-rolodex -v $(pwd)/public:/monsters-rolodex/public:z -v $(pwd)/src:/monsters-rolodex/src:z -p 3000:3000 -e CHOKIDAR_USEPOLLING=true monsters-rolodex-image npm start


```

### 53. Asynchronous setState

setState IS ASYNC
use (prevState, prevProps)
inject props in constructor

```react
this.setState(
      (prevState, prevProps) => {
        return {
          meaningOfLife: prevState.meaningOfLife + prevProps.increment,
        };
      },
      () => {
        console.log(this.state.meaningOfLife);
      }
    );
```

### 54. Introducing Lifecycle Methods

<https://github.com/ZhangMYihua/lifecycles-lesson>

### 55. React Lifecycle Methods - Mounting

at first display:
```
constructor!
render!
componentDidMount!
```

update text button:
```
shouldComponentUpdate! {text: "_hello_hello"}
render!
componentDidUpdate!
```
Toggle lifecycles button:
```
componentWillUnmount!
or
constructor!
render!
10 componentDidMount!
``` 


![lifecycles](./lifecycles-lesson/React%20lifecycle%20methods%20diagram.png)

<https://projects.wojtekmaj.pl/react-lifecycle-methods-diagram/>