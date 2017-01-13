# live.fm
Live Server

- Use this command to kill all processes ps aux | grep -ie live | awk '{print $2}' | xargs kill -9 
initctl list | grep live

- Need to execute the following shell commands in mongo console
use broadcasts // this will switch to the "broadcasts" database
db.broadcasts.ensureIndex({location:"2d"}) // in the 'broadcasts' collection of the 'broadcasts' database ensure and index of type '2d' for the location field
db.broadcasts.createIndex( {location:"2d"})
db.broadcasts.find( { location: { $geoWithin: { $centerSphere: [ [ 18.535407, 73.833267 ] , 8 / 6372.8 ] } } } )
