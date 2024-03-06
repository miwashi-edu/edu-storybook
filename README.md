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
npm install -D rollup @rollup/plugin-babel @rollup/plugin-node-resolve @rollup/plugin-commonjs @rollup/plugin-replace @rollup/plugin-terser rollup-plugin-serve rollup-plugin-livereload
npm install -D @babel/preset-env @babel/preset-react
mkdir src
touch src/index.js
npm pkg set "scripts.build"="rollup -c"
npm pkg set "scripts.start"="rollup -c -w"
#npm pkg set "presets"="["@babel/preset-env", "@babel/preset-react"]"
npx sb init --builder webpack5
}

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

### rollup.config.js

```bash
cd ~
cd ws
cd storybook
cat > rollup.config.js << 'EOF'
import babel from '@rollup/plugin-babel';
import resolve from '@rollup/plugin-node-resolve';
import commonjs from '@rollup/plugin-commonjs';
import terser from '@rollup/plugin-terser';
import pkg from './package.json' //assert { type: 'json' };

export default {
  input: 'src/index.js',
  output: [
    { file: pkg.main, format: 'cjs' },
    { file: pkg.module, format: 'es', exports: 'named'}
  ],
  plugins: [
    resolve({
      extensions: ['.js', '.jsx'],
      dedupe: ['prop-types']
    }),
    commonjs(),
    babel({
      babelHelpers: 'bundled',
      exclude: 'node_modules/**',
      presets: ['@babel/preset-env', '@babel/preset-react']
    }),
    terser()
  ]
};
EOF
```

