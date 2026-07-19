# Web testing / Web 应用测试

优先建立请求流和信任边界，再做输入验证。常见检查面：认证与会话、访问控制、输入处理、错误处理、业务流程、文件处理、跨域与安全响应头、依赖与配置。

证据应包含最小化请求/响应、角色、测试对象、时间和影响。避免发送会改变状态或触及真实数据的 payload；需要验证写操作时使用专用测试对象并准备回滚。

English retrieval keywords: HTTP, API, authentication, session, authorization, IDOR/BOLA, input validation, SSRF, file upload, security headers.
