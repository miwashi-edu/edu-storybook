# edu-storybook

> Clean storybook-demo from project, and prepare the project structure for atomic design methodology.

[Atomic Design Methodology](https://atomicdesign.bradfrost.com/chapter-2/)

# Atomic Design Overview
Atomic Design is a methodology for creating design systems. It's composed of five distinct levels:  
1. **Atoms**: The basic building blocks of matter, such as HTML tags like a form label, an input or a button.  
2. **Molecules**: Groups of atoms bonded together and are the smallest fundamental units of a compound. Examples include a form label, input, and button combined.  
3. **Organisms**: Groups of molecules joined together to form a relatively complex, distinct section of an interface. For instance, a navigation bar.  
4. **Templates**: Consist mostly of groups of organisms stitched together to form pages. It's where content structure is defined.  
5. **Pages**: Specific instances of templates that show what a UI looks like with real representative content in place.  
Atomic Design helps designers and developers create a consistent, scalable, and reusable design system by breaking down interfaces into a hierarchical structure.  

## Prepare

> 

```bash
cd ~
cd ws
cd storybook
echo "# edu-components" > README.md
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
