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
- Edit the `index.html` and add the utility classes as needed

##### Configuring TailwindCSS

- Run `npx tailwindcss init --full` to generate the `tailwind.config.js` file. The `--full` flag generates the file with all the default values.
- The `tailwind.config.js` just `module.exports` a very large object containing all the configuration settings. Alterations to the theme can be done my modifying the the `theme{ property: "value", ... }` object. By default it contains all the settings that TailwindCSS gives you out of the box. If the need arises, you can edit this object and add your settings. **Note: Modifying the default settings is not recommended**
- Run `npm run build-css` again to recompile and generate the a new CSS file with the modified settings.
- The correct way to make modifications to the configs is by creating a separate `tailwind.config.js` that will extend the default settings. the steps to do so are as follows:

  - Rename the `tailwind.config.js` to `tailwind-default.config.js` or anything else as the renamed file will not be used. Tailwind will use the default settings under the hood.
  - Run `npx tailwindcss init` (this time without the `--full` flag) to generate a new
  - The new config file will now `module.export` an object which contains a sub-set of properties that the complete config file had. It could look something like this:

  ```javascript
  module.exports = {
    purge: [],
    theme: {
      extend: {},
    },
    variants: {},
    plugins: [],
  };
  ```

  - Now we can make modifications/additions that we like. For example, we want to add two colors that we want to use in out project called `primary` and `secondary`. We could add those colors in the `theme.extend.colors` object as follows:

  ```javascript
  extend: {
        colors: {
          primary: "#3399CC",
          secondary: "#EFA536",
        },
      }
  ```
