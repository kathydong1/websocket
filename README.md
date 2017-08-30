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
      //创建websocket对象
       
      
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
