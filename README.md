
## Setup an EC2
```
Spin up a new EC2 machine

Install dependencies on EC2 machine

Setting up the inbound and outbound rules

Setting up GitHub on EC2

Creating Jobs to host your app Launching and testing your app
```

## Setup environment
```
sudo apt install nodejs

sudo apt-get update

clone the frontend code from Github

npm install react-scripts

npm install react-router-dom --save
```

## Setup Nginx
```
sudo apt install nginx

to check: sudo systemctl status nginx.service
```
<img src="https://p1-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/6f2cd7d31dd34fec89bd0b767d489634~tplv-k3u1fbpfcp-jj-mark:0:0:0:0:q75.image#?w=1346&h=328&s=91673&e=png&b=010101" alt="螢幕截圖 2024-03-27 下午9.28.29.png" width="90%" />

配置文件：
```
sudo vi my-app.conf
```
my-app.conf：
```
server{
        listen 80;
        listen [::]:80;
        server_name ;

        location / {
                #include /etc/nginx/sites-enabled/*;
                proxy_pass http://localhost:3000;
        }
}
```
关联系统配置文件
```
sudo ln /home/ubuntu/FYP-Full-stack-Aphasia-AI-Web-App-Development-based-on-React-and-FASTAPI/my-app.conf /etc/nginx/sites-enabled/ [-f如果源文件存在需要覆盖]

sudo nginx -t

sudo systemctl restart nginx.service
```

## Setup Inbound rules
Edit security -> Inbound rules

<img src="https://p9-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/0ce21303d1b445e9bcc1fed533cf3c4f~tplv-k3u1fbpfcp-jj-mark:0:0:0:0:q75.image#?w=1285&h=315&s=56634&e=png&b=fdfdfd" alt="螢幕截圖 2024-03-27 下午9.40.13.png" width="90%" />

## 运行
`npm run build`
