```javascript

// Objects

var dictionary = {
  key1: "value1",
  key2: "value2",
};


function messWithDict(targetDict, key, value) {
  // Add to an object
  dictionary[key] = value;
  console.log(dictionary);
  return dictionary;
};


messWithDict(dictionary, "phone", "00398293");

// Arrays

salaries = [1, 2, 3, 4, 5, 6, 7, 8, 9];

function sumArray(array) {
  // Sum the elements of an array
  var sum = 0;
  for(i = 0; i < array.length; ++i) {
    sum += array[i];
  };
  console.log("Sum: " + sum);
  return sum;
};

sumArray(salaries);


// Doing maths with array of objects

var gpsPoints = [
  {
    lat: 28.5, 
    lng: 3.4
  },
  {
    lat: 28.9, 
    lng: 4.1
  },
];
  
function navigator(p1, p2) {
  console.log('lat dif' + (p2.lat - p1.lat));
  console.log('lng dif' + (p2.lng - p1.lng));
  return
  };
  
navigator(gpsPoints[1], gpsPoints[0]);

// Functions tied to objects' properties are methods

var heights = [];

heights.push(175, 180, 184.5);
heights.pop();
heights.push(170);
heights.reverse();

// Let's define our own method using the `this` keyword


var gridPoints = [
  {
    x: 28.5, 
    y: 3.4
  },
  {
    x: 28.9, 
    y: 4.1
  },
];

gridPoints.euclidean = function() {
  var org = this[0];
  var des = this[1];
  var dif_x = des.x - org.x;
  var dif_y = des.y - org.y;
  return Math.sqrt((dif_x * dif_x) + (dif_y * dif_y));
};

gridPoints.euclidean()





function gpsPoint(x, y) {
  this.x = x;
  this.y = y;
};

var point1 = new gpsPoint(21, 3.5);

```