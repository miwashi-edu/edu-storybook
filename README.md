# edu-storybook



## Prepare

```bash
```


## Instructions

```bash
```


## Files

### file

```bash
cat > file << 'EOF'

EOF
```

### rollup.config.js

```bash
cat > rollup.config.js << 'EOF'
import babel from 'rollup-plugin-babel';
import resolve from '@rollup/plugin-node-resolve';
import commonjs from '@rollup/plugin-commonjs';
import replace from '@rollup/plugin-replace';
import { terser } from 'rollup-plugin-terser';
import serve from 'rollup-plugin-serve';
import livereload from 'rollup-plugin-livereload';

export default {
  input: 'src/index.js',
  output: {
    file: 'dist/bundle.js',
    format: 'iife',
    sourcemap: true
  },
  plugins: [
    resolve(),
    commonjs(),
    babel({
      exclude: 'node_modules/**',
      presets: ['@babel/preset-env', '@babel/preset-react']
    }),
    replace({
      'process.env.NODE_ENV': JSON.stringify('development')
    }),
    serve({
      open: true,
      contentBase: ['', 'public'],
      host: 'localhost',
      port: 3000
    }),
    livereload({ watch: 'dist' }),
    process.env.NODE_ENV === 'production' && terser()
  ]
};
EOF
```

