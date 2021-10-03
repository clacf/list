port: 7890
socks-port: 7891
allow-lan: true
mode: Rule
log-level: info
external-controller: 127.0.0.1:9090
proxies:
- name: "http"
  type: http
  server: 173.82.120.152
  port: 3128
  username: pxuser
  password: 0K^x5h0U
- name: "http_back"
  type: http
  server: 173.82.120.152
  port: 5027
proxy-groups:
  - name: Proxies
    type: select
    proxies:
      - http
      - http_back
rules:
 - MATCH,Proxies
