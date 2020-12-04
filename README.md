# NeoG Camp - markFive

_Built with [Tailwind](https://tailwindcss.com/) ver 1.4.6. Using it for the first time in this project. Refer to [personal reference notes here]()._

The NeoG Camp is an initiative taken up by Tanay Pratap to introduce young minds to learn skills that are in-demand in the software industry in structured manner with the end goal of successfully mentoring a handful of motivated individuals and enable them to break into the industry.

The camp takes a bootcamp style approach with weekly coding sessions live streamed on YouTube where core concepts are explained in a practical manner by building something. Participants are required to then build something that demonstrates their understanding of the concepts.

## markFive

This repository is the second assignment of the camp to be submitted in the third week.

### Requirements

### Development Process

This project is the first time I used the Tailwind CSS Framework and will be maintaining a few notes for future reference.

#### Understand the Workflow

We will use `node` to set up the Tailwind CSS Framework. The `src` folder will contain a `style.css` file which will have the configuration for TailwindCSS along with any custom CSS that you want to add.

We will then run the command `tailwindcss build src/styles.css -o public/styles.css` to generate the required CSS. The `src/style.css` is where the configuration is stored and the resulting CSS file is generated at `public/styles.css`. The generated CSS is then applied to any of the HTML files in the `public` folder.

#### Steps

- run `npm init -y` to set up `package.json` file.
- `npm install tailwindcss` to install the framework in `node_modules`. Please note that `tailwind` is a different npm package. I installed `tailwind` instead of `tailwindcss` and couldn't figure out why nothing worked for an hour before I realised the typo.
- \*I edited the dependencies to denote `"tailwindcss": "^1.4.6"`. I didn't get the preprocessor workflow of `ver 2.0`.
- Set up the folder structure :
  - create `src/styles.css`
  - create `public/`folder
  - create a `style.css` and `index.html` file in the `public` folder
  - build your HTML page in `index.html` and link the `style.css` of the public folder in it to load styles
- Add the following code to the `src/style.css` file:

```css
@tailwind base;
@tailwind components;
@tailwind utilities;
```

- Configure `package.json` `scripts:` and add command `"build-css": "tailwindcss build src/styles.css -o public/styles.css"`
- Run `npm run build-css` command to generate the required CSS in the
