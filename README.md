# edu-storybook

> Create a simple project for component development.  
> We base it on React and Webpack.

## Prepare

```bash
```


## Instructions

> 1. Create a project folder
> 2. Make it to a Node project
> 3. Add react dependencies so that "npx storybook init" will be able to determine project type.
> 4. Add webpack dependencies so that "npx storybook init" will be able to determine build system.
> 5. Add peer dependencies (requirements) for comsumers of components.
> 6. add scripts in package.json for starting storybook with "npm start"
> 7. initialize storybook with webpack.

```bash
cd ~
cd ws
rm -rf storybook
mkdir storybook && cd storybook # 1
npm init -y # 2
npm install react react-dom # 3
npm install --save-dev webpack webpack-cli # 4
npm pkg set peerDependencies.react=">=16.8.0" peerDependencies.react-dom=">=16.8.0" # 5
mkdir src
touch src/index.js
npm pkg set "scripts.start"="storybook dev -p 6006" # 6
npx sb init --builder webpack5 # 7
```


## Files
