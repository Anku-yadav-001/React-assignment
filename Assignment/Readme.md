<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Boilerplate Code</title>
    <style>
      body{
        display: flex;
      justify-content: center;
      font-size: 50px;
      font-weight: 800;
      font-family: system-ui, -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, 'Open Sans', 'Helvetica Neue', sans-serif;

      }
        #root{
            background-color: rgb(0, 255, 238);
            border-radius: 8px;
            box-shadow: 0 0 25 green;
            overflow: hidden;
            width: 300px;
            text-align: center;
        }
        div{
            margin: 15px;
        }
        h1,h2{
          color: pink;
        }
        h1{
          font-size: 24px;
          margin-bottom: 10px;
        }
        h2{
          font-size: 18px;
          color: rebeccapurple;
        }
        button{
          background-color: yellow;
          color: black;
          border: none;
          padding: 10px 15px;
          margin: 5px;
          cursor: pointer;
          border-radius: 4px;
          font-size: 14px;
        }
        button:hover{
          background-color: aqua;
        }

    </style>
  </head>
  <body>
    <div id="root"></div>
  </body>
  <script src="https://www.unpkg.com/react@18.2.0/umd/react.development.js"></script>
  <script src="https://www.unpkg.com/react-dom@18.2.0/umd/react-dom.development.js"></script>
  <script src="https://unpkg.com/@babel/standalone/babel.min.js"></script>
  <script type="text/babel">
    // Code goes here
   
    let root=document.getElementById('root')
    let createRoot=ReactDOM.createRoot(root)
    let {useState}=React
    function RenderButton({run,setRun}){
      return <>
         
            <button onClick={()=>setRun(run+8)}>Increase by 8</button><br/>
          <button onClick={()=>setRun(run+4)}>Increase by 4</button><br/>
          <button onClick={()=>setRun(run+3)}>Increase by 3</button>
      
      </>
     
    }
    let CricketScoreboard=()=>{
    let [run, setRun]=useState(0)
    let [wickets, setWickets]=useState(0)
      return <>
        <div>
          <h1>Runs-{run}</h1>
          <h2>Wickets-{wickets}</h2>
        </div>
        <div>
          {10!=wickets?(<RenderButton run={run} setRun={setRun}/>):( <h1>The match is over and the final runs are: {run}</h1>)}
        </div>
         <div>
          <button onClick={()=>wickets<10?setWickets(wickets+1):(setWickets(wickets))}>Update Wicket</button>
        </div>
      </>
    }
    let App=()=>{
    
    return <>
       <CricketScoreboard/>
    </>
   }
 createRoot.render(<App/>)
  </script>
</html>