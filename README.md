### DuckDuckGo AI Page

#### Usage

Install Nginx:

    sudo apt install nginx-light

Configure:

    location /country {
        proxy_pass https://duckduckgo.com/country.json;
        proxy_set_header Host duckduckgo.com;
        proxy_set_header X-Requested-With XMLHttpRequest;
        proxy_set_header Referer https://duckduckgo.com/;
    }
    
    location /status {
        proxy_pass https://duckduckgo.com/duckchat/v1/status;
        proxy_set_header Host duckduckgo.com;
        proxy_set_header X-Vqd-Accept 1;
        proxy_set_header Cache-Control no-store; 
        proxy_set_header Referer https://duckduckgo.com/;   
    }
    
    location /completions {
        proxy_pass https://duckduckgo.com/duckchat/v1/chat;
        proxy_set_header Host duckduckgo.com;
        proxy_set_header X-Vqd-4 $http_x_vqd_4;
        proxy_set_header Referer https://duckduckgo.com/;
        proxy_set_header Accept text/event-stream;
        proxy_set_header Content-Type "application/json; charset=utf-8";
    }

    

#### Screenshot

![example](https://raw.githubusercontent.com/yeziruo233/DuckDuckGo-AI-Page/refs/heads/master/screenshot.png)

#### License


    MIT License


#### Privacy Policy and Terms of Use


    please read: 
    https://duckduckgo.com/aichat/privacy-terms