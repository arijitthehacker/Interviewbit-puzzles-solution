## Question:

There are 100 doors, all closed. 
In a nearby cage are 100 monkeys.

The first monkey is let out, and runs along the doors opening every one. 
The second monkey is then let out, and runs along the doors closing the 2nd, 4th, 6th,…  - all the even-numbered doors. 
The third monkey is let out. He attends only to the 3rd, 6th, 9th,… doors (every third door, in other words), closing any that is open and opening any that is closed, and so on. 
After all 100 monkeys have done their work in this way, what state are the doors in after the last pass?

## Solution Approach: 

Consider door number 56, monkeys will visit it for every divisor it has. So 56 has 1 & 56, 2 & 28, 4 & 14, 7 & 8. So on pass 1 1st monkey will open the door, pass 2 2nd one will close it, pass 4 open, pass 7 close, pass 8 open, pass 14 close, pass 28 open, pass 56 close. For every pair of divisors the door will just end up back in its initial state. But there are cases in which the pair of divisor has same number for example door number 16. 16 has the divisors 1 & 16, 2 & 8, 4&4. But 4 is repeated because 16 is a perfect square, so you will only visit door number 16, on pass 1, 2, 4, 8 and 16… leaving it open at the end. So only perfect square doors will be open at the end.

## Answer:
 10

function openDoors() {
  let doors = {};
  for (let i = 1; i <= 100; i++) {
    doors[i] = false;
  }

  for (let j = 1; j <= 100; j++) {
    let bound = j;
    while (bound <= 100) {
      if (doors[bound] === false) {
        doors[bound] = true;
      } else {
        doors[bound] = false;
      }
      bound = bound + j;
    }
  }
  let arr = [];
  for (let i in doors) {
    if (doors[i] === true) {
      arr.push(i);
    }
  }
  return arr;
}
openDoors();
