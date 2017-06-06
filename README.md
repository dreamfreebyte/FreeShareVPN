# FreeShareVPN

This Project is mainly for chinese people who live in mainland and want to browser google and facebook、youtube etc.
or chinese people who live foreign country want to watch video which only publish mainland.


这个项目主要是为了帮助大陆有翻墙需要的人们，或者是在海外由于版权原因不能观看，但是希望观看国内影视作品的人们。


# 为什么会有这个项目?
  作者作为一个常年单身程序员，由于工作和身体需要，经常需要翻墙使用google以及观看youtube视频以及其他不能言说的视频,最初几年尝试过PPTP、IPSEC等等标准
  VPN服务，发现大部分时候基本不可用，主要问题如下:
  
## 1、稳定性差
  我在使用标准VPN的时候，都是从linode等口碑比较好的厂商租用日本线路,linode的服务质量在业界口碑是不错的。早上的时候网速奇快，youtube视频也不在话下，但是一到下午
  或者晚上，基本的网页都很难打开，更何况看YouTube视频了。

## 2、容易被墙
  由于是业界标准VPN协议，很容易被墙掉，经常是用了一段时间，莫名的登录不上。
  
## 3、速度慢
  PPTP和IPSEC等VPN本质上不是为了解决翻墙而设计的，所以未考虑丢包率严重的问题。在用来翻墙的时候，丢包率超过5%就已经很难流畅的看Youtube视频了。
  如果超过10%，网页的打开速度都慢的要命，但是晚上高峰期的时候，到海外丢包率超过20%是常态,所以会出现到晚上不可用。
  归根结底是因为协议设计上，更多的考虑了公平，而不是速度。所以，即使是linode 日本的线路，在早上，也很难稳定的720P观看视频。  

## 4、配置和安装麻烦
  PPTP倒是不算太复杂，但是也不是太简单，手动用vi修改配置文件对非后台程序员来说，也不是件容易的事情。
  IPSec更是巨坑，本身就有多种标准，每种配置方式都差别很大，需要理解很多概念，本人过去几年经常配置，但是每次配置前都头疼。
  
  

# 设计目标
 ## 1、网络适应性强
   无论高峰期的丢包率是10%还是25%甚至30%，都能保证720甚至1080P的youtube稳定观看。由于对网络丢包率要求不高，可以租用便宜的云服务器，
   节省成本。
  
 ## 2、服务器配置简单
   最好一键启动，无需繁琐的配置,这样，切换服务器就没那么头疼了。
   
 ##多平台支持
   客户端至少支持PC和安卓(MAC暂不考虑)，同时支持linux和树莓派(放在家里当翻墙路由器)。
 
# 使用方法
 
## 1、简单使用
    假设你不准备自己架设自己的VPN，可以只安装客户端就可以了，目前支持PC(暂未放出)和Android。
    
  ###### （1）安卓   
    到Client/Android目录下，下载FreeShareVPN.apk安装，启动后，点击开始就可以了，首次点击可能会提示你授权，点击同意才能翻墙。
    
  ###### （2）PC
    等待版本吧：）
    
## 2、架设自己的VPN服务器
    这里假设你有基本的ssh登录scp和rz上传文件知识。
  ######  （1）、租用云服务器，可以从DigitalOcean或者linode租用服务器,相对便宜。
    
  ###### （2）、下载Server/UdpProxyServer.tgz， 上传到云服务器任意目录,
    
       运行命令(注意都用root权限)解压:
       tar xvvf UdpProxyServer.tgz
       
       启动:
       cd UdpProxyServer && ./start.sh
       
  ###### （3）、安装安卓客户端，启动后，输入自己的IP,点击连接，开始享受翻墙之旅吧！！
    
    
  # 联系我
    QQ 59769175
    邮件 feixuwu@hotmail.com
