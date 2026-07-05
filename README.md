import { createServer } from "node:http";

const html = `
<!DOCTYPE html>
<html>
<head>
<meta charset="UTF-8">
<title>My AI Chatbot</title>
<style>
body{
    font-family:Arial,sans-serif;
    background:#f2f2f2;
    display:flex;
    justify-content:center;
    align-items:center;
    height:100vh;
    margin:0;
}

.chat{
    width:400px;
    background:#fff;
    padding:20px;
    border-radius:10px;
    box-shadow:0 0 10px rgba(0,0,0,.2);
}

h2{
    text-align:center;
}

input{
    width:95%;
    padding:10px;
    margin:10px 0;
}

button{
    width:100%;
    padding:10px;
    background:#0078ff;
    color:white;
    border:none;
    border-radius:5px;
    cursor:pointer;
}

button:hover{
    background:#005fcc;
}

#reply{
    margin-top:20px;
    font-size:18px;
    color:#333;
}
</style>
</head>

<body>

<div class="chat">
<h2>🤖 My AI Chatbot</h2>

<input id="message" placeholder="Type your message">

<button onclick="sendMessage()">Send</button>

<p id="reply"></p>

</div>

<script>
async function sendMessage(){

const message=document.getElementById("message").value;

const response=await fetch("/chat?message="+encodeURIComponent(message));

const data=await response.json();

document.getElementById("reply").innerHTML="<b>Bot:</b> "+data.reply;

}
</script>

</body>
</html>
`;

const server = createServer((req, res) => {

    const url = new URL(req.url, `http://${req.headers.host}`);

    if(url.pathname==="/chat"){

        const message=(url.searchParams.get("message")||"").toLowerCase();

        let reply="Sorry, I don't understand.";

        if(message.includes("hi")||message.includes("hello")){
            reply="Hello! 👋 How can I help you?";
        }
        else if(message.includes("how are you")){
            reply="I'm doing great! 😊";
        }
        else if(message.includes("bye")){
            reply="Goodbye! Have a nice day!";
        }

        res.writeHead(200,{
            "Content-Type":"application/json"
        });

        res.end(JSON.stringify({reply}));

    }else{

        res.writeHead(200,{
            "Content-Type":"text/html"
        });

        res.end(html);

    }

});

server.listen(3000,()=>{
    console.log("Server running at http://localhost:3000");
});import { createServer } from "node:http";

const html = `
<!DOCTYPE html>
<html>
<head>
<meta charset="UTF-8">
<title>My AI Chatbot</title>
<style>
body{
    font-family:Arial,sans-serif;
    background:#f2f2f2;
    display:flex;
    justify-content:center;
    align-items:center;
    height:100vh;
    margin:0;
}

.chat{
    width:400px;
    background:#fff;
    padding:20px;
    border-radius:10px;
    box-shadow:0 0 10px rgba(0,0,0,.2);
}

h2{
    text-align:center;
}

input{
    width:95%;
    padding:10px;
    margin:10px 0;
}

button{
    width:100%;
    padding:10px;
    background:#0078ff;
    color:white;
    border:none;
    border-radius:5px;
    cursor:pointer;
}

button:hover{
    background:#005fcc;
}

#reply{
    margin-top:20px;
    font-size:18px;
    color:#333;
}
</style>
</head>

<body>

<div class="chat">
<h2>🤖 My AI Chatbot</h2>

<input id="message" placeholder="Type your message">

<button onclick="sendMessage()">Send</button>

<p id="reply"></p>

</div>

<script>
async function sendMessage(){

const message=document.getElementById("message").value;

const response=await fetch("/chat?message="+encodeURIComponent(message));

const data=await response.json();

document.getElementById("reply").innerHTML="<b>Bot:</b> "+data.reply;

}
</script>

</body>
</html>
`;

const server = createServer((req, res) => {

    const url = new URL(req.url, `http://${req.headers.host}`);

    if(url.pathname==="/chat"){

        const message=(url.searchParams.get("message")||"").toLowerCase();

        let reply="Sorry, I don't understand.";

        if(message.includes("hi")||message.includes("hello")){
            reply="Hello! 👋 How can I help you?";
        }
        else if(message.includes("how are you")){
            reply="I'm doing great! 😊";
        }
        else if(message.includes("bye")){
            reply="Goodbye! Have a nice day!";
        }

        res.writeHead(200,{
            "Content-Type":"application/json"
        });

        res.end(JSON.stringify({reply}));

    }else{

        res.writeHead(200,{
            "Content-Type":"text/html"
        });

        res.end(html);

    }

});

server.listen(3000,()=>{
    console.log("Server running at http://localhost:3000");
});import { createServer } from "node:http";

const html = `
<!DOCTYPE html>
<html>
<head>
<meta charset="UTF-8">
<title>My AI Chatbot</title>
<style>
body{
    font-family:Arial,sans-serif;
    background:#f2f2f2;
    display:flex;
    justify-content:center;
    align-items:center;
    height:100vh;
    margin:0;
}

.chat{
    width:400px;
    background:#fff;
    padding:20px;
    border-radius:10px;
    box-shadow:0 0 10px rgba(0,0,0,.2);
}

h2{
    text-align:center;
}

input{
    width:95%;
    padding:10px;
    margin:10px 0;
}

button{
    width:100%;
    padding:10px;
    background:#0078ff;
    color:white;
    border:none;
    border-radius:5px;
    cursor:pointer;
}

button:hover{
    background:#005fcc;
}

#reply{
    margin-top:20px;
    font-size:18px;
    color:#333;
}
</style>
</head>

<body>

<div class="chat">
<h2>🤖 My AI Chatbot</h2>

<input id="message" placeholder="Type your message">

<button onclick="sendMessage()">Send</button>

<p id="reply"></p>

</div>

<script>
async function sendMessage(){

const message=document.getElementById("message").value;

const response=await fetch("/chat?message="+encodeURIComponent(message));

const data=await response.json();

document.getElementById("reply").innerHTML="<b>Bot:</b> "+data.reply;

}
</script>

</body>
</html>
`;

const server = createServer((req, res) => {

    const url = new URL(req.url, `http://${req.headers.host}`);

    if(url.pathname==="/chat"){

        const message=(url.searchParams.get("message")||"").toLowerCase();

        let reply="Sorry, I don't understand.";

        if(message.includes("hi")||message.includes("hello")){
            reply="Hello! 👋 How can I help you?";
        }
        else if(message.includes("how are you")){
            reply="I'm doing great! 😊";
        }
        else if(message.includes("bye")){
            reply="Goodbye! Have a nice day!";
        }

        res.writeHead(200,{
            "Content-Type":"application/json"
        });

        res.end(JSON.stringify({reply}));

    }else{

        res.writeHead(200,{
            "Content-Type":"text/html"
        });

        res.end(html);

    }

});

server.listen(3000,()=>{
    console.log("Server running at http://localhost:3000");
});
