##  STEP 1 – BACKEND CONFIGURATION

**Ubuntu update**
sudo apt update
sudo apt upgrade

**Install nodejs in server**
curl -fsSL https://deb.nodesource.com/setup_18.x | sudo -E bash -
sudo apt-get install -y nodejs
node -v 
npm -v

  **Application Code Setup**

       mkdir Todo
       cd Todo
       npm init
        ls

  **Install ExpressJS**

         npm install express
         touch index.js

Install the dotenv module
        
        npm install dotenv
        vim index.js
Copy, paste and save the following codes and quit

const express = require('express');
require('dotenv').config();

const app = express();

const port = process.env.PORT || 5000;

app.use((req, res, next) => {
res.header("Access-Control-Allow-Origin", "\*");
res.header("Access-Control-Allow-Headers", "Origin, X-Requested-With, Content-Type, Accept");
next();
});

app.use((req, res, next) => {
res.send('Welcome to Express');
});

app.listen(port, () => {
console.log(`Server running on port ${port}`)
});


Open the server with this command

    node index.js

Open TCP port 5000 and access server from the browser using the remote server IP address

http://<PublicIP-or-PublicDNS>:5000






