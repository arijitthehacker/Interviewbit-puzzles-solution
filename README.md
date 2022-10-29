# Interviewbit-puzzles-solution
My Solutions to the Interviewbit Questions.

const doors = [{ignoreMe: true}]

for (let i = 1; i <= 100; i++) 
    doors.push({door: i, open: false})


// first monkey will open each door
doors.map(door => door.open = !door.open)

// from second monkey and on...

// foreach monkey from 2 to 100
for (let i = 2; i <= 100; i++) {
    for (let j = i; j <= 100; j+=i) {
        doors[j].open = !doors[j].open
    }
}

const output = doors.filter(door => door.open)
console.log("output => ", output)

/*

output =>  [
  { ignoreMe: true, open: true },
  { door: 1, open: true },       
  { door: 4, open: true },       
  { door: 9, open: true },       
  { door: 16, open: true },      
  { door: 25, open: true },      
  { door: 36, open: true },      
  { door: 49, open: true },      
  { door: 64, open: true },      
  { door: 81, open: true },      
  { door: 100, open: true }      
]

So, the doors that are open at the end are = 1, 4, 9, 16, 25, 36, 49, 64, 81, 100 😎
*/
