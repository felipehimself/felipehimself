**Record Collection**

You are given an object literal representing a part of your musical album collection. Each album has a unique id number as its key and several other properties. Not all albums have complete information.

You start with an updateRecords function that takes an object literal, records, containing the musical album collection, an id, a prop (like artist or tracks), and a value. Complete the function using the rules below to modify the object passed to the function.

1. Your function must always return the entire record collection object.
2.If prop isn't tracks and value isn't an empty string, update or set that album's prop to value.
3.If prop is tracks but the album doesn't have a tracks property, create an empty array and add value to it.
4.If prop is tracks and value isn't an empty string, add value to the end of the album's existing tracks array.
5.If value is an empty string, delete the given prop property from the album.

**Note**: A copy of the recordCollection object is used for the tests.


After ```updateRecords(recordCollection, 5439, "artist", "ABBA")```, ```artist``` should be the string ```ABBA```

After ```updateRecords(recordCollection, 5439, "tracks", "Take a Chance on Me")```, ```tracks``` should have the string ```Take a Chance on Me``` as the last element.

After ```updateRecords(recordCollection, 2548, "artist", "")```, ```artist``` should not be set

After ```updateRecords(recordCollection, 1245, "tracks", "Addicted to Love")```, ```tracks``` should have the string ```Addicted to Love``` as the last element.

After ```updateRecords(recordCollection, 2468, "tracks", "Free")```, ```tracks``` should have the string ```1999``` as the first element.

After ```updateRecords(recordCollection, 2548, "tracks", "")```, ```tracks``` should not be set

After ```updateRecords(recordCollection, 1245, "albumTitle", "Riptide")```, ```albumTitle``` should be the string ```Riptide```

**My solution:**


```var recordCollection = {
  2548: {
    albumTitle: 'Slippery When Wet',
    artist: 'Bon Jovi',
    tracks: ['Let It Rock', 'You Give Love a Bad Name']
  },
  2468: {
    albumTitle: '1999',
    artist: 'Prince',
    tracks: ['1999', 'Little Red Corvette']
  },
  1245: {
    artist: 'Robert Palmer',
    tracks: []
  },
  5439: {
    albumTitle: 'ABBA Gold'
  }
};

// Altere apenas o código abaixo desta linha
function updateRecords(records, id, prop, value) {
  if (prop !== "tracks" && value.length !== 0){
    records[id][prop] = value
  }
  else if (prop == "tracks" && records[id].hasOwnProperty("tracks") == false){
    records[id][prop] = [value]
    }

  else if (prop == "tracks" && value.length !== 0) {
    records[id][prop].push(value)
  }

  else if (value.length == 0){
    delete records[id][prop]
  }
  
  return records;
}

updateRecords(recordCollection, 5439, "artist", "ABBA")
console.log(recordCollection)```
