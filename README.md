# edu-storybook

> Clean storybook-demo from project, and prepare the project structure for atomic design methodology.

[Atomic Design Methodology](https://atomicdesign.bradfrost.com/chapter-2/)

## Prepare

> 

```bash
```


## Instructions

> 1. Remove demo project
> 2. Create structure for atomic design methodology.
>

```bash
cd ~
cd ws
cd storybook
rm ./src/stories/*.css # 1
rm ./src/stories/*.jsx
rm ./src/stories/*.js
rm ./src/stories/*.mdx
rm -rf ./src/stories/assets
mkdir -p ./src/components/{assets,atoms,molecules,organisms,templates,pages} # 2
```
