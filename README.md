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
mkdir -p ./src/components/atoms/LogoImage/
touch ./src/components/atoms/LogoImage/LogoImage.jsx
touch ./src/components/atoms/LogoImage/LogoImage.module.css
touch ./src/components/atoms/LogoImage/index.js
```


## Files

### ./src/components/atoms/LogoImage/index.js

```bash
cd ~
cd ws
cd storybook
cat > ./src/components/atoms/LogoImage/index.js << 'EOF'
//for bundling
export {default as LogoImage} from "./LogoImage"

//for storybook
export {default} from "./LogoImage"
EOF
```

### ./src/components/atoms/LogoImage/LogoImage.module.css

```bash
cd ~
cd ws
cd storybook
cat > ./src/components/atoms/LogoImage/LogoImage.module.css << 'EOF'
.logoStyle {
  fill: #123456; /* Example fill color */
}
EOF
```

### ./src/components/atoms/LogoImage/LogoImage.jsx

```bash
cd ~
cd ws
cd storybook
cat > ./src/components/atoms/LogoImage/LogoImage.jsx << 'EOF'
import React from 'react';

const LogoImage = ({ className = '', colorMode = 'color' }) => {
  // Define colors for each path; adjust these colors as needed.
  const colors = colorMode === 'color' ? ['#e63946', '#f1faee', '#a8dadc', '#457b9d', '#1d3557'] : ['#000000', '#000000', '#000000', '#000000', '#000000'];

  return (
    <svg
      version="1.0"
      xmlns="http://www.w3.org/2000/svg"
      width="512pt"
      height="512pt"
      viewBox="0 0 512.000000 512.000000"
      preserveAspectRatio="xMidYMid meet"
      className={className}
    >
      <g transform="translate(0.000000,512.000000) scale(0.100000,-0.100000)" stroke="none">
        <path fill={colors[0]} d="M2797 4253 c-10 -9 -9 -871 1 -876 5 -2 1097 107 1120 112 1 1 2 149 2 330 l0 330 -42 6 c-52 7 -1042 105 -1061 105 -8 0 -17 -3 -20 -7z" />
        <path fill={colors[1]} d="M2045 3969 c-259 -26 -571 -57 -695 -69 -124 -11 -240 -23 -258 -26 l-32 -6 2 -437 3 -436 715 -71 c393 -40 736 -74 763 -76 l47 -5 0 588 0 589 -37 -1 c-21 -1 -249 -23 -508 -50z" />
        <path fill={colors[2]} d="M3545 3264 c-401 -41 -736 -76 -742 -79 -10 -3 -13 -135 -13 -610 0 -475 3 -607 13 -610 14 -6 1375 -142 1462 -147 l60 -3 0 760 0 760 -25 2 c-14 1 -353 -32 -755 -73z" />
        <path fill={colors[3]} d="M320 1970 l0 -942 83 6 c74 6 2152 116 2184 116 11 0 13 133 13 744 l0 743 -62 7 c-35 4 -227 27 -428 51 -201 24 -671 80 -1045 124 -374 45 -695 83 -712 86 l-33 6 0 -941z" />
        <path fill={colors[4]} d="M2797 1763 c-10 -9 -9 -1251 1 -1257 5 -3 116 6 248 20 131 13 307 30 389 38 83 8 257 25 388 37 l237 24 0 507 0 507 -32 5 c-18 3 -107 13 -198 21 -91 9 -248 25 -350 35 -102 11 -282 28 -400 40 -118 11 -229 23 -246 25 -17 3 -33 2 -37 -2z" />
      </g>
    </svg>
  );
};

export default LogoImage;

EOF
```

### ./src/stories/LogoImage.stories.jsx

```bash
cd ~
cd ws
cd storybook
cat > ./src/stories/LogoImage.stories.jsx << 'EOF'
import React from 'react';
import Logo from '../components/molecules/Logo';

export default {
    title: 'Components/Atoms/Logo',
    component: Logo,
    argTypes: {
        colorMode: {
            control: 'radio',
            options: ['color', 'bw'],
        },
    },
};

const Template = (args) => <Logo {...args} />;

export const Default = Template.bind({});
Default.args = {
    colorMode: 'bw',
};
EOF
```
