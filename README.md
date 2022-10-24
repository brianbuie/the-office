# The Office

**Every line from every episode of The Office**

![Michael Scott](https://i.imgur.com/T6vZeid.gif)

Special thanks to the fans at [OfficeQuotes.net](http://www.officequotes.net/) for transcribing the episodes.

I've done my best to clean up and normalize the names and quotes, but feel free to submit an issue or PR you find any mistakes.

## Usage

`npm install the-office`

### ES5

`const quotes = require('the-office');`

### ES6

`import quotes from 'the-office'`

## Format

The data is an array of episodes, each containing info about the episode, along with an array of `scenes` and `deleted_scenes`:

```json
[
  {
    "season": 1,
    "episode": 1,
    "title": "Pilot",
    "scenes": [...],
    "deleted_scenes": [...]
  },
  {
    "season": 1,
    "episode": 2,
    "title": "Diversity Day",
    "scenes": [...],
    "deleted_scenes": [...]
  },
  ...
]
```

The `scenes` and `deleted_scenes` properties are each an array of scenes. Each scene is an array of lines:

```json
...
"scenes": [
  [
    {
      "character": "Michael",
      "line": "All right Jim..."
    },
    {
      "character": "Jim",
      "line": "Oh, I told you. I couldn't close it. So..."
    },
    ...
  ],
  [
    {
      "character": "Michael",
      "line": "[on the phone] Yes, I'd like to..."
    }
  ],
  ...
],
```

## Random Quote Example

This repo only contains the json data, so here's an example showing how you could retrieve a random quote.

```javascript
const episodes = require('the-office');

// or use lodash's _.sample()
function random(arr) {
  return arr[Math.floor(Math.random() * arr.length)];
}

function randomQuote(episodes) {
  const { scenes, season, episode, title } = random(episodes);
  const { character, line } = random(scenes.flat());
  return { character, line, season, episode, title };
}

console.log(randomQuote(episodes));
/* {
  character: 'Michael',
  line: 'Parkoooooour!',
  season: 6,
  episode: 1,
  title: 'Gossip'
} */
```
