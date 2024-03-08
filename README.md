# edu-storybook

> Creating our first components.

## Prepare

> Before continuing decide the name for the component library.

```bash
```


## Instructions

```bash
cd ~
cd ws
cd storybook
npm install -D rollup @rollup/plugin-babel @rollup/plugin-node-resolve @rollup/plugin-commonjs @rollup/plugin-replace @rollup/plugin-terser rollup-plugin-serve rollup-plugin-livereload
npm install -D @rollup/plugin-image
npm install -D rollup-plugin-postcss
npm install -D @babel/preset-env @babel/preset-react
npm pkg set "scripts.build"="rollup -c --bundleConfigAsCjs"
npm pkg set "name"="@wacoco/component-library",
npm pkg set "main"="dist/index.cjs.js",
npm pkg set "module"="dist/index.esm.js",
```

## Files

### ./src/index.js

```bash
cd ~
cd ws
cd storybook
cat > ./src/index.js << EOF
import {LogoImage} from './components/atoms/LogoImage'; 
export default LogoImage;
EOF
```

### rollup.config.js

```bash
cd ~
cd ws
cd storybook
cat > rollup.config.js << EOF
import babel from '@rollup/plugin-babel';
import resolve from '@rollup/plugin-node-resolve';
import commonjs from '@rollup/plugin-commonjs';
import terser from '@rollup/plugin-terser';
import pkg from './package.json' assert { type: "json" };
import image from '@rollup/plugin-image';
import postcss from 'rollup-plugin-postcss';

export default {
    input:'src/index.js',
    output: [
        { file: pkg.main, format: 'cjs' },
        { file: pkg.module, format: 'es', exports: 'named'}
    ],
    plugins: [
        postcss({
            // Plugin options, like extensions or modules
            extensions: ['.css'],
        }),
        babel({
            babelHelpers: 'bundled',
            exclude: 'node_modules/**',
            presets: ['@babel/preset-env','@babel/preset-react']
          }),
          resolve({
            extensions: ['.js', '.jsx'],
            dedupe: ['prop-types']
          }),
          commonjs(),
          image(),
          terser()
    ],
    external: Object.keys(pkg.peerDependencies)
  };
EOF
```

### Nice to have additions to package.json

```json
"peerDependenciesMeta": {
  "react": {
    "optional": true
  }
}

"bugs": {
  "url": "https://github.com/user/repo/issues"
}


"homepage": "https://example.com/project-homepage"

"files": [
  "dist",
  "lib",
  "README.md"
]

"keywords": ["react", "ui-components", "educational"]

"engines": {
  "node": ">= 14.0.0"
}

"contributors": [
  "Name <email@example.com> (https://example.com)"
]

"publishConfig": {
  "access": "public"
}

"private": true
```

