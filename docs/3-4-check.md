### 部署后的确认检查

- ### 管理端（server）：

  1. 使用passwd修改root账户密码，避免弱口令
  2. 使用date，确认系统时间的准确
  3. 确认防火墙已经启用，并配置了正确的端口放行，需要放行22、4433、4434端口

  ```wiki
  #centos7 检查防火墙状态
  systemctl status firewalld
  
  #centos7 检查防火墙开放端口
  firewall-cmd --list-ports
  ```

  4. 如果server能够访问外网（建议用户有限放行对情报源的访问），检查情报对接（x & tip）、官网域名和CDN域名是否通畅

  5. 如果server能够访问通知服务（syslog、邮件、webhook），检查通知是否通畅

     

- ### 节点端（Client）：

  1. 使用passwd修改root账户密码，避免弱口令

  2. 使用date确认系统时间的准确

  3. 确认防火墙已经启用，并配置了正确的端口放行，需要放行22、22122端口和节点端上启动的蜜罐服务端口（需要在server后台确认端口信息），放行方式参考上面的server端命令。
