# The Office

This repository contains every episode of the office split into individual JSON files. Special thanks to the fans at [OfficeQuotes.net](http://www.officequotes.net/) for transcribing the episodes.

I've done my best to clean up and normalize the names and quotes, but I'm sure there are still errors.

## Usage

All episodes can be found in the `lib/` folder. Alternatively, if you're using javascript, you can `require` them in your project.

`const quotes = require('/path/to/theOffice'); // all episodes`

`const S01E01 = require('/path/to/theOffice').S01E01; // single episode`

## Schema

```
{
    "season": 1,
    "episode": 1,
    "title": "Pilot",
    "scenes": [
        [
            {
                "character": "Michael",
                "quote": "All right Jim. Your quarterlies look very good. How are things at the library?"
            },
			{
                "character": "Jim",
                "quote": "Oh, I told you. I couldn't close it. So..."
            },
		],
	],
	"deleted_scenes" : [
		[
            {
                "character": "Dwight",
                "quote": "Dwight Schrute. My father's name, also Dwight Schrute. My grandfather's name, Dweide Schrude, Amish. That's my family. I don't know where they came, the Amish, came from originally. Uh, Amland."
            },
		],
	]
}
```