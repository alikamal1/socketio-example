# websockets-example
a simple websockets example

<img width="400" height="400" src="https://raw.githubusercontent.com/alikamal1/websockets-example/master/screenshot.PNG">

## Server Side
Socket setup to express server variable
```javascript
var io = socket(server);
```

socket listen on client connection event and pass socket params which refer to client browser
```javascript
io.on('connection', function (socket) {

});
```

socket refer to the connection that establised and now it can listen to a channel
```javascript
socket.on('chat', function (data) {
        
});
```

sockets refer to all connect clients, emit data on a channel
```javascript
io.sockets.emit('chat', data);
```

broadcast a data to a channel to all clients except orginal socket client
```javascript
socket.broadcast.emit('typing', data);
```

## Client Side
connect client browser to socket server
```javascript
var socket = io.connect('http://localhost:4000');
```

client browser emit data to a channel
```javascript
socket.emit('chat', {
        message: message.value,
        username: username.value
});
```

client browser listening to channel
```javascript
socket.on('typing', function (data) {

});
```

## Project Setup
```
npm install
npm run dev-start
```
