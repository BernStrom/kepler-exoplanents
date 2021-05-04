## About
A simple program built with only Node and the [csv-parse](https://csv.js.org/parse/ "CSV Parse") package, for parsing through Kepler's exoplanet archive data made available by NASA, to search for habitable planets that fits within a set of planetary environment similar to Earth. 

:point_right:&nbsp; [Link to Deno version here](https://github.com/BernStrom/nasa-habitable-planets-parser "NASA Habitable Planets Parser")

## Installation
_**Note: Before running the program, please ensure you have Node installed on your machine.**_

1. Follow the installation instructions on the Node official website: https://nodejs.org/en/
2. In your terminal, run: `node index.js`
3. You should see the program return a list of planet names that are deem habitable:

   
        [
          'Kepler-1652 b',
          'Kepler-1410 b',
          'Kepler-296 A f',
          'Kepler-442 b',
          'Kepler-296 A e',
          'Kepler-1649 b',
          'Kepler-62 f',
          'Kepler-452 b'
        ]
   
        8 habitable planets found!

## Customization
Environmental conditions for the habitable planets are customizable through the following function in the code:

        const isHabitablePlanet = (planet) => {
          return (
            planet['koi_disposition'] === 'CONFIRMED' &&
            planet['koi_insol'] > 0.36 &&
            planet['koi_insol'] < 1.11 &&
            planet['koi_prad'] < 1.6
          );
        }
The planetary habitable conditions here are set based on various public sources from both government and private space agencies. Do note that these range might differ slightly depending on the source of reference.

If you would like to review what other planetary data that are available and their legend, please refer to the `kepler_data.csv` file for more information.

For example, `koi_prad` === "Planetary Radius [Earth radii]".

## :memo: License [![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

This project is licensed under the terms of the MIT license. For more information, please refer to the license [documentation](LICENSE.md).
