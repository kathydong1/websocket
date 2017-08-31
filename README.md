<!DOCTYPE HTML>
<html>
   <head>
   <meta charset="utf-8">
   <title>websocket</title>
   </head>
   <body>
   
      <div id="sse">
         <input type="text" name="" id="txt" value="">
      </div>
      <script type="text/javascript">
       最大特点就是，服务器可以主动向客户端推送信息，客户端也可以主动向服务器发送信息，是真正的双向平等对话，属于服务器推送技术的一种。
         （1）建立在 TCP 协议之上，服务器端的实现比较容易。
         （2）与 HTTP 协议有着良好的兼容性。默认端口也是80和443，并且握手阶段采用 HTTP 协议，因此握手时不容易屏蔽，能通过各种 HTTP 代理服务器。
         （3）数据格式比较轻量，性能开销小，通信高效。
         （4）可以发送文本，也可以发送二进制数据。
         （5）没有同源限制，客户端可以与任意服务器通信。
         （6）协议标识符是ws（如果加密，则为wss），服务器网址就是 URL。
      //npm安装websocket：npm install ws
      //创建虚拟服务器
      //创建websocket对象
          var ws = new WebSocket('ws://localhost:8080');
      //方法
          readyState
               CONNECTING：值为0，表示正在连接。
               OPEN：值为1，表示连接成功，可以通信了。
               CLOSING：值为2，表示连接正在关闭。
               CLOSED：值为3，表示连接已经关闭，或者打开连接失败
          webSocket.onopen
               实例对象的onopen属性，用于指定连接成功后的回调函数。
          webSocket.onclose
               实例对象的onclose属性，用于指定连接关闭后的回调函数。
          webSocket.onmessage
               实例对象的onmessage属性，用于指定收到服务器数据后的回调函数。
          webSocket.send()
               实例对象的send()方法用于向服务器发送数据。
          
     
      
       txt.onblur=function(){
          var ws=new WebSocket('ws://localhost:8888')
          ws.addEventListener('open',function(){
              alert('正在建立链接')
              ws.send(txt.value)
          })
          ws.onmessage=function(ev){
              console.log(ev)
              alert('接受数据成功'+ev)
          }
          ws.onclose=function(){
              alert('关闭成功')
          }
       }
   
       
     </script>
   </body>
</html>
