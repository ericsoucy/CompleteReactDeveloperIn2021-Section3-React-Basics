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
