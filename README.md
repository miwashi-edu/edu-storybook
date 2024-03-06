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
mkdir src
touch src/index.js
npm pkg set "scripts.start"="storybook dev -p 6006"
npx sb init --builder webpack5
npm pkg set "peerDependencies"="{'react': '>=16.8.0','react-dom': '>=16.8.0'}"
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
