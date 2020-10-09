# Today I learned 

This file keeps track of my everyday learning process. Github format is pretty convenient to write down code examples and links to resources.

## 09.10.2020
#### Shebang with ts-node
To make `.ts` file executable we should write shebang line this way: `#!/usr/bin/env -S ts-node -r tsconfig-paths/register`  

## 08.10.2020
#### Typeorm migrations
Using `synchronize: true` in typeorm config is risky, because it can lead to data loss. Safe way to migrate data are [migrations](https://github.com/typeorm/typeorm/blob/master/docs/migrations.md).
You can work with migrations via cli tool like `typeorm migration:generate` and `typeorm migration:run` but the problem here is that this scripts require standalone config files.
I like to keep typeorm config in main environment file, so we need to create script that programmatically generates and runs migrations.

Luckily, it's not so hard using `connection.driver.createSchemaBuilder`
https://github.com/footballista/ftb-backend/tree/master/migrations/scripts

#### yargs
npm [yargs](https://www.npmjs.com/package/yargs) - useful tool to work with command line arguments:
```
const argv = require('yargs')
  .usage('Usage: $0 -width [num] -height [num]')
  .alias('w', 'width')
  .alias('h', 'height')
  .alias('s', 'scale')
  .demandOption(['w', 'h'])
  .default('scale', 1)
  .describe('w', 'square width')
  .describe('h', 'square height')
  .describe('s', 'result scale')
  .argv;
```
Cool examples are [here](https://github.com/yargs/yargs/blob/HEAD/docs/examples.md)

Seems like a good practice to wrap your command into class that implements yargs.CommandModule interface.

#### chalk 
npm [chalk](https://www.npmjs.com/package/chalk) - a nice nad powerful tool for console output formatting. 
