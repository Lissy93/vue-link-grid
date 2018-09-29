# vue-link-grid

I don't know about you, but I very regularly find that I need to display a list of links,
and usually the nicest way is in a grid, maybe with icons.
So here's a vue component that does just that. It's simple, but saves on time and duplication.

You can either use a pre-built theme, or pass your CSS/SCSS styles in.
By default, it's fully responsive, and touch-screen enabled.  

## Usage

You know the drill, install `yarn add vue-link-grid`
And then import: `import { TileSection, Tile } from 'vue-link-grid';`

You can either use `Tile`, or `TileSection` which is a group of tiles.

```
<TileSection
    :tileSectionTitle="mySectionTitle"
    :tileSectionSubTitle="mySectionSubTitle"
    :tiles = "tilesArray"
    theme="material"
    :styles="myStyles"
/>
```

```
<Tile
    v-for="tile in this.tiles"
    :key="tile.id"
    :name="tile.name"
    :description="tile.description"
    :url="tile.url"
    :icon="tile.icon"
/>
```

### `TileSection` Configuration Options

 - `tileSectionTitle`: String, Title of section
 - `tileSectionSubTitle`: String, subtitle of section
 - `tiles`: Array, array of tile objects. See below for the structure
 - `theme`: String, _optional_ name of prebuilt theme. `material`, `material-dark`...
 - `styles`: Object, _optional_ object containing JavaScript CSS style overides.

### `Tile` Configuration Options

 - `name`: String, the title of a given tile
 - `description`: String _optional_, the subtitle of a given tile
 - `url`: String, _optional_, the path of tile link on click
 - `icon`: String _optional_, the path to an image to be used


The tile data used by `TileSection` needs to be structured following for format below. _`description`, `url` and `icon` are optional_

```
"tiles": [
    {
        "id": "0",
        "name": "Tile One",
        "description": "Description of first tile",
        "url": "https://google.com",
        "icon": "https://via.placeholder.com/100/E8117F"
    },
    {
        "id": "1",
        "name": "Tile Two",
        "description": "Lorem ipsum dolar",
        "url": "https://bbc.co.uk",
        "icon": "https://via.placeholder.com/100x100"
    },
    {
        "id": "2",
        "name": "Tile Three",
        "description": "Hello World.",
        "url": "https://google.com",
        "icon": ""
    }
]
```

### Custom styles
When you add in your custom styles, you can use any of the following
classes to reference different parts of a `TileSection` or `Tile`

```
/* The specified tile section */
.tile-section.NAME-OF-THEME-theme{

    /* Heading and sub-heading of tile section */
    header.tile-section-header{

        h2.tile-section-title{

        }
        span.tile-section-sub-title{

        }
    }

    /* Wrapper for the tiles */
    .tile-wraper{
        a.tile{
            /* Image/ icon within a tile */
            img.tile-icon{

            }
            /* Tile name, and description text */
            .tile-texts{
                .tile-name{

                }
                .tile-description{

                }
            }
        }
    }
}
```


## Contributing

It'd be really cool if you'd like to contribute, either to
add a feature or theme, or to fix or improve something -
pull requests are always very welcome.

### Running locally

 - **Clone**: `git clone https://github.com/Lissy93/vue-link-grid.git && cd vue-link-grid`
 - **Project setup**: `yarn install`
 - **Compiles and hot-reloads for development**: `yarn run serve`
 - **Compiles and minifies for production**: `yarn run build`
 - **Lints and fixes files**: `yarn run lint`
 - **Run the end-to-end tests**: `yarn run test:e2e`

### Creating a new theme

To add a new themeL
 - Just add a new stylesheet into `src/styles/`, with the `-theme.scss` prefix
 - There is a theme template in `./src/styles/template-theme.scss`
 - Then import it into `src/styles/index.scss`. (e.g. `@import '../styles/hello-theme.scss';`)
 - Use your theme, by adding `theme="hello"` to your instance of `TileSection` component


## License
Licensed under MIT, (C) [Alicia Sykes](https://aliciasykes.com) 2018. [Read full License](LICENSE.md).

[![License](https://upload.wikimedia.org/wikipedia/commons/f/f8/License_icon-mit-88x31-2.svg)](LICENSE.md)