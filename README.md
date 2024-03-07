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
npm install -D @babel/preset-env @babel/preset-react
npm pkg set "scripts.build"="rollup -c --bundleConfigAsCjs"
npm pkg set "name"="@wacoco/component-library",
npm pkg set "main"="dist/index.cjs.js",
npm pkg set "module"="dist/index.esm.js",
```


## Files

### rollup.config.cjs

```bash
cd ~
cd ws
cd storybook
cat > ./src/components/atoms/Button.jsx << 'EOF'
// Button.js or Button.jsx

import React from 'react';
import PropTypes from 'prop-types';

const Button = ({ onClick, children, type = 'button', className }) => (
  <button type={type} className={`button ${className}`} onClick={onClick}>
    {children}
  </button>
);

Button.propTypes = {
  onClick: PropTypes.func,
  children: PropTypes.node.isRequired,
  type: PropTypes.oneOf(['button', 'submit', 'reset']),
  className: PropTypes.string
};

Button.defaultProps = {
  onClick: () => {},
  className: ''
};

export default Button;
EOF
```
