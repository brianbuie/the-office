# The Office

This repository contains every episode of the office split into individual JSON files. Special thanks to the fans at [OfficeQuotes.net](http://www.officequotes.net/) for transcribing the episodes.

I've done my best to clean up and normalize the names and quotes, but I'm sure there are still errors. Feel free to submit a PR if you find any mistakes.

## Usage

All episodes can be found in the `lib/` folder. 

If you're using javascript, you can install using `npm install the-office` and then `require` them in your project.

`const quotes = require('the-office'); // all episodes`

`const theBestEpisode = require('the-office')[51]; // single episode`

`const neverAgain = require('the-office/lib/S06E11'); // by name`

## Schema

Every episode has an array of scenes. Each scene is an array of objects with the properties `character` and `line`. Stage directions (`[...]`) are still included in some of the spoken lines.

```
{
    "season": 1,
    "episode": 1,
    "title": "Pilot",
    "scenes": [
        [
            {
                "character": "Michael",
                "line": "All right Jim. Your quarterlies look very good. How are things at the library?"
            },
			{
                "character": "Jim",
                "line": "Oh, I told you. I couldn't close it. So..."
            },
		],
	],
	"deleted_scenes" : [
		[
            {
                "character": "Dwight",
                "line": "Dwight Schrute. My father's name, also Dwight Schrute. My grandfather's name, Dweide Schrude, Amish. That's my family. I don't know where they came, the Amish, came from originally. Uh, Amland."
            },
		],
	]
}
```