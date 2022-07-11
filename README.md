# challenge
import React from 'react';
import ReactDOM from 'react-dom';
import './index.css';
import App from './App';
const express = require("express")();
const app = express();
const PORT = 8080;


ReactDOM.render(
  <React.StrictMode>
    <App />
  </React.StrictMode>,
  document.getElementById('root')
);
app.use(express.json())
app.post('/challenge/:id',(req,res) => {
  const{id} = req.params;
  const {arr} = req.body;

  var len = arr.size();
  var count = arr.replace(/[^0-9]/g,'').length;
  var str, num;
  for(var i = 0; i<len; i++)
  {
    if((arr[i] > 'a' && arr[i] < 'z' )||(arr[i] > 'A' && arr[i] < 'Z' ) )
      str.concat(arr[i]);
    else
      num.concat(arr[i]);
  }
  res.send({
    is_success: true,
    user_id: 'jessy_raj_30122000',
    count: count,
    email : '1905240@kiit.ac.in',
    roll_number:'1905240',
    numbers: num,
    alphabets: str
  })
})
