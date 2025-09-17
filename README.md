# python-argo-modal

## 必要的变量——在 action 仓库机密中设置

### Modal的变量

- **MODAL_TOKEN_ID** = modal api token 的 ID         // 必须
- **MODAL_TOKEN_SECRET** = modal api token 的秘钥    // 必须
- **MODAL_USER_NAME** = modal 账号的用户名            // 必须
- **MODAL_APP_NAME** = modal 项目名                  // 不填则使用默认

### 节点所需变量

- **UUID** = 82ab6c19-b0c4-4d2a-93d1-af0687edfe76    // 不填则使用内置默认uuid
- **ARGO_DOMAIN** = argo 域名                        // 必须，model必须使用固定隧道，临时隧道不通
- **ARGO_AUTH** = eyxxxxxxxxxxxxxxxxxxxxxxxxxxx     // 必须，model必须使用固定隧道，临时隧道不通
- **NEZHA_SERVER** = 哪吒 agent 域名，v1为 域名:端口  // 可选
- **NEZHA_KEY** = 哪吒 agent 的 key                  // 可选
- **NEZHA_PORT** = 哪吒 agent 的 端口，仅v0需要       // 可选
- **CFIP** = cf.090227.xyz                          // 优选域名或IP，可选，不填则使用默认
- **CFPORT** = 443                                  // 优选域名或优选IP的端口，可选，不填则使用默认
- **BOT_TOKEN** = TG 机器人 Token                   // 可选
- **CHAT_ID** = TG 机器人或频道 ID                   // 可选

## 保活

项目24小时后会自动关闭，关闭的项目无法再唤醒，保活逻辑采用重部署方式

### 保活方式1：action 定时任务

每天凌晨2点重部署，取消将工作流中定时触发器的 `#` 号注释，即可启用

### 保活方式2：uptime+webhook 启动 action

具体教程：<https://blog.811520.xyz/post/2025/09/250916-uptime-action/>
