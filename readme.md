# Amtrak

## Disclaimer
This library and it's creator have no relation to Amtrak. Amtrak and the Atmrak Logo are trademarks of The National Railroad Passenger Corporation (NRPC). The API endpoint used is not intended for use outside of [Amtrak's Train Tracking map](https://www.amtrak.com/track-your-train.html). 

## Don't be an A\*\*
- Please refrain from spamming the API, as that is an a\*\*hole move. The API returns an object with everything in it, so there is ***literally no reason*** to spam the API. 
- If you want to keep your application with the most up to date, I would simply update once per minute (central server) or every 5 to 10 minutes (individual clients).
- In the future, I plan on hosting my own free API which will serve the same data as the Amtrak API, just with some added benefits, such as pulling information for specific trains and stations. I plan on allowing this library to interact with said API, so stay tuned.

## Installation
It'n an NPM package lol:

`npm install amtrak`

## Documentation

(Documentation moved to docs.md)

## TS Examples
As this library was written in TypeScript, it is naturally easy to use it:
### Fetching All Data
```ts
import { fetchTrainData } from 'amtrak';

//fetches data, cleans it, and then prints to terminal
fetchTrainData().then((trainData) => {
	console.dir(trainData, { depth: null })
})
```
### Fetching All Trains
```ts
import { fetchAllTrains } from 'amtrak';

//fetches all trains and then prints to terminal
fetchAllTrains().then((trainData) => {
	console.dir(trainData, { depth: null })
})
```
### Fetching Single Trains
```ts
import { fetchTrain } from 'amtrak';

//fetches all trains with the number 20 (crescent) and then prints to terminal
fetchTrain(20).then((trainData) => {
	console.dir(trainData, { depth: null })
})
```
### Fetching All Stations
```ts
import { fetchAllStations } from 'amtrak';

//fetches all stations and then prints to terminal
fetchAllStations().then((stationData) => {
	console.dir(stationData, { depth: null })
})
```
### Fetching Single Stations
```ts
import { fetchStation } from 'amtrak';

//fetches all station data for CHI (chicago) and then prints to terminal
fetchStation('CHI').then((stationData) => {
	console.dir(stationData, { depth: null })
})
```

## JS Example
And of course, as the TS is compliled to JS, you can use that as well. The only real difference between the two is how you (generally) import, so everything lese is the same. The only difference here is that you can import *from* in ts, but you require the whole module is js.
```js
const amtrak = require("amtrak");
amtrak.fetchTrainData().then((trainData) => {
    console.dir(trainData, { depth: null })
});
```

(wait they're like the same lmao)

## Contributing
I don't currently have any official contributing templates, but please make sure to add some testing code to `testing/src/testAll.ts`. Anything you add should take one of the existing types and return a modified version of it or a new type which you define in `src/types/types.ts`.