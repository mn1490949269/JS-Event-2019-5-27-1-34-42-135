## 要求 
    
- 实现一个基础的计时器应用，点击开始按钮开始计时，点击结束按钮结束计时，并把计时的结果显示在上面的输入框中。

```html
  <!DOCTYPE html>
  <html lang="en">
  <head>
      <meta charset="UTF-8">
      <title>定时器示例</title>
  </head>
  <body>
  
  <input type="text" id="result" value="00:00:00:000" readonly><br>
  
  <input type="button" value="开始" onclick="start()">
  <input type="button" value="结束" onclick="stop()">
  <input type="button" value="重置" onclick="Reset()">
  
  <script>
    var hour,minute,second;//时 分 秒
    hour=minute=second=0;//初始化
    var millisecond=0;//毫秒
    var int;
    function Reset()//重置
    {
      window.clearInterval(int);
      millisecond=hour=minute=second=0;
      document.getElementById('result').value='00:00:00:000';
    }
  
    function start()//开始
    {
      int=setInterval(timer,50);
    }
  
    function timer()//计时
    {
      millisecond=millisecond+50;
      if(millisecond>=1000)
      {
        millisecond=0;
        second=second+1;
      }
      if(second>=60)
      {
        second=0;
        minute=minute+1;
      }
  
      if(minute>=60)
      {
        minute=0;
        hour=hour+1;
      }
      document.getElementById('result').value=hour+':'+minute+':'+second+':'+millisecond;
  
    }
  
    function stop()//暂停
    {
      window.clearInterval(int);
    }
// write your code here
      // ......
  </script>
  </body>
  </html>
```
