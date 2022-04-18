### single value varibale

```JS
const name = "Teddy";
<div>{name}</div>
```

### conditional display

inline

```JS
 const i = 1;
 
 <div>{i % 2 === 0 ? "even number" : "odd number"}</div>
```

declare a function

```JS
  const checkOddorEven = (num) => {
    if (num % 2 === 0) {
      return "even";
    } else {
      return "odd";
    }
  };
 <div>{checkOddorEven(i)}</div>
```

### display a return value of function

```

  const displaySum = (array) => {
    let sum = 0;
    for (let num of array) {
      sum = sum + num;
    }
    return sum;
  };
  
<div>{displaySum([1, 2, 3])}</div>
```

### Array.map

```
  let students = [
    { name: "teddy", color: "red" },
    { name: "enson", color: "orange" },
    { name: "wilson", color: "yellow" }
  ];

        {students.map((student, i) => (
          <div style={{ backgroundColor: student.color }} key={i}>
            {student.name}
          </div>
        ))}
```

### onClick

```
  let count = 0;
  <div>{count}</div>
        <button onClick={() => ((count = count + 1), console.log({ count }))}>
```

array.push

```
        <button
          onClick={() => {
            students.push({ name: "peter", color: "green" })
            console.log(students)
          }}
        >
          Add Student
        </button>
```

```
<div>
    <toolbar>
        <button></button>
    </toolbar>

<input></input>
</div>
```

### Call api

```JS

import "./styles.css";
import React, { useState, useEffect } from "react";
export default function App() {
  const [playgrounds, setPlaygrounds] = useState([]);
  useEffect(() => {
    let getData = async () => {
      const response = await fetch(
        "https://api.data.gov.hk/v1/historical-archive/get-file?url=http%3A%2F%2Fwww.lcsd.gov.hk%2Fdatagovhk%2Ffacility%2Ffacility-cpr.json&time=20220106-0938"
      );
      const data = await response.json();
      console.log(data);
      setPlaygrounds(data);
    };
    getData();
  }, []);
  return (
    <div className="App">
      <div style={{ border: "1px solid black" }}>
        <h1>Varibale display</h1>
        {playgrounds.map((playground, i) => (
          <div key={i}>{playground.Name_cn}</div>
        ))}
      </div>
    </div>
  );
}

```
