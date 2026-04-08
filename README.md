# Digital-Clock-App-with-React-Js

⏰ React Digital Clock App

A simple and elegant Digital Clock application built using React.js. This project demonstrates how to work with time, state updates, and side effects using React Hooks.

🚀 Features
🕒 Real-time clock display
🔄 Automatically updates every second
⚡ Fast and responsive UI
🎯 Built with React Hooks (useState, useEffect)


🛠️ Technologies Used
React.js
JavaScript (ES6+)
HTML5
CSS3

💡 How It Works
The current time is stored using React's useState hook
useEffect hook is used to update the time every second
setInterval runs every 1000ms (1 second) to refresh the clock
React automatically re-renders the UI when the state updates

DigitalClockJSX

```
import React, {useState, useEffect}  from 'react'

function DigitalClock(){

    const [time, setTime] = useState(new Date())

    useEffect(() =>{
        const intervalId = setInterval(() => {
            setTime(new Date)
        }, 1000)

        return () => {
            clearInterval(intervalId)
        }
    },[])

    const formatTime = () => {
        let hours = time.getHours();
        const minutes = time.getMinutes();
        const seconds = time.getSeconds();
        const meridiem = hours >= 12 ? 'PM' : "AM"

        hours = hours % 12 || 12;

        return `${padZero(hours)}: ${padZero(minutes)}: ${padZero(seconds)} ${meridiem}`
    }

    function padZero(number){
        return (number < 10 ? "0" : "") + number
    }

    return(
        <div className='clock-container'>
            <div className='clock'>
                <span>{formatTime()}</span>
            </div>
        </div>
    )
}

export default DigitalClock

```

index.css

```
body{
  background-image: url(https://cdn.wallpapersafari.com/11/97/jl57Gf.jpg);
  background-position: center;
  background-repeat: no-repeat;
  background-size: cover;
  background-attachment: fixed;
  margin: 0;
  display: flex;
  justify-content: center;
  min-height: 100vh;
  align-items: center;
}

.clock-container{
  backdrop-filter: blur(5px);
  width: 100vw;
  padding: 10px 0;
}


.clock{
  color: white;
  font-size: 6rem;
  font-weight: bold;
  font-family: monospace;
  text-align: center;
  text-shadow: 3px 3x 5px hsla(hsl(0, 0%, 0%));
}

```

App.jsx

```
import DigitalClock from "./DigitalClock"

function App() {
  return (
    <>
      <DigitalClock/>
    </>
  )
}

export default App

```


main.jsx
```

import { StrictMode } from 'react'
import { createRoot } from 'react-dom/client'
import './index.css'
import App from './App.jsx'

createRoot(document.getElementById('root')).render(
  <StrictMode>
    <App />
  </StrictMode>,
)
```
<img width="1487" height="708" alt="DigitalClock" src="https://github.com/user-attachments/assets/f2fd6883-dbe9-4cdc-b867-2a6a16a38fa7" />

