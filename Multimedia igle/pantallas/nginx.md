```
worker_processes  1;

  

error_log  logs/error.log debug;

  

events {

    worker_connections  1024;

}

  

rtmp {

    server {

        listen 1935;

        chunk_size 4096;

  

        application camara {

            live on;

            record off;

  

            hls on;

            hls_path C:/Users/matias.martinez/nginx_temp/hls/camara;

            hls_fragment 5s;

        }

  

        application letras {

            live on;

            record off;

  

            hls on;

            hls_path C:/Users/matias.martinez/nginx_temp/hls/letras;

            hls_fragment 5s;

        }

  

        application countdown {

            live on;

            record off;

  

            hls on;

            hls_path C:/Users/matias.martinez/nginx_temp/hls/countdown;

            hls_fragment 5s;

        }

    }

}

  

http {

    server {

        listen 8080;

  

        location /hls {

            types {

                application/vnd.apple.mpegurl m3u8;

                video/mp2t ts;

            }

            alias C:/Users/matias.martinez/nginx_temp/hls/;

            add_header Cache-Control no-cache;

            add_header Access-Control-Allow-Origin *;

        }

    }

}
```