# UDPclient-connect-UDPserver

UDP Client:<br>

host='0.0.0.0'<br>
port=50003<br>

client=socket.socket(socket.AF_INET,socket.SOCK_DGRAM) <br>
print 'Ready to send message to server..'<br>
client.sendto(b'Hello server... I sent message for you')<br>
client.close()<br>


UDP Server:<br>
ip=''<br>
port=50003<br>
server=socket.socket(socket.AF_INET,socket.SOCK_DRGAM)<br>
server.bind((ip,port))<br>

while True:<br>
  data=server.recvform(4096)＃接受UDP的套接字     套接字用（IP地址：端口號）表示<br>   
  if not data: break<br>
  print 'Received data from client:'<br>
  print repr(data)<br>

server.close()<br>



!!OPEN Terminal!! [打開兩個terminal]<br>
--第一個terminal--<br>
cd ~/桌面 「輸入你自己存放的地方」<br>
pthon udpserver.py<br>


--第二個terminal--<br>
cd ~/桌面<br>
python udpclient.py<br>

server端顯示的是：<br>
Received data from client:'Hello server...I sent message for you',('127.0.0.1',48061)<br>

client端顯示的是：<br>
Ready to send message to server<br>

