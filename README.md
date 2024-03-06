# edu-storybook

> Create a project for component development.

## Prepare

```bash
```


## Instructions

```bash
cd ~
cd ws
mkdir storybook && cd storybook
npm init -y
npm install react react-dom
npm install --save-dev webpack webpack-cli
#npm install -D @babel/preset-env @babel/preset-react
mkdir src
touch src/index.js
npm pkg set "scripts.start"="npx run storybook"
#npm pkg set "presets"="["@babel/preset-env", "@babel/preset-react"]"
npx sb init --builder webpack5
```


## Files

### file

```bash
cd ~
cd ws
cd storybook
cat > file << 'EOF'

EOF
```
