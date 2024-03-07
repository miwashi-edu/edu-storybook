# edu-storybook

> Clean storybook-demo from project, and prepare the project structure for atomic design methodology.

[Atomic Design Methodology](https://atomicdesign.bradfrost.com/chapter-2/)

## Prepare

> 

```bash
echo "# Atomic Design Overview" > README.md
echo -e "\nAtomic Design is a methodology for creating design systems. It's composed of five distinct levels:" >> README.md
echo -e "\n1. **Atoms**: The basic building blocks of matter, such as HTML tags like a form label, an input or a button." >> README.md
echo -e "\n2. **Molecules**: Groups of atoms bonded together and are the smallest fundamental units of a compound. Examples include a form label, input, and button combined." >> README.md
echo -e "\n3. **Organisms**: Groups of molecules joined together to form a relatively complex, distinct section of an interface. For instance, a navigation bar." >> README.md
echo -e "\n4. **Templates**: Consist mostly of groups of organisms stitched together to form pages. It's where content structure is defined." >> README.md
echo -e "\n5. **Pages**: Specific instances of templates that show what a UI looks like with real representative content in place." >> README.md
echo -e "\nAtomic Design helps designers and developers create a consistent, scalable, and reusable design system by breaking down interfaces into a hierarchical structure." >> README.md
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
