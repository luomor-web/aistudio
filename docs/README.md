```shell
curl -fsSL https://openclaw.ai/install.sh | bash

npm i -g openclaw
npm i -g openclaw --registry=https://registry.npmmirror.com
openclaw onboard

pnpm add -g openclaw
openclaw onboard

openclaw --help

https://openclaw.wepromo.cn/

Web UI: http://127.0.0.1:8010/                                                 │
│  Web UI (with token):                                                           │
│  http://127.0.0.1:8010/?token=fb98553bdee6c084939055200fb4f1f22e726fbc2c8aad6c  │
│  Gateway WS: ws://127.0.0.1:8010                                                │
│  Gateway: reachable                                                             │
│  Docs: https://docs.openclaw.ai/web/control-ui 

https://openclaw.wepromo.cn/?token=fb98553bdee6c084939055200fb4f1f22e726fbc2c8aad6c

disconnected (1008): pairing required

openclaw config set gateway.controlUi.basePath https://openclaw.wepromo.cn
rm -rf ~/.openclaw/extensions/feishu
openclaw gateway restart

openclaw config set gateway.controlUi.allowInsecureAuth true
openclaw gateway restart

openclaw config get gateway.controlUi

youuser ALL=(ALL) ALL
%youuser ALL=(ALL) ALL
youuser ALL=(ALL) NOPASSWD: ALL
%youuser ALL=(ALL) NOPASSWD: ALL
第一行:允许用户youuser执行sudo命令(需要输入密码).
第二行:允许用户组youuser里面的用户执行sudo命令(需要输入密码).
第三行:允许用户youuser执行sudo命令,并且在执行的时候不输入密码.
第四行:允许/用户组youuser里面的用户执行sudo命令,并且在执行的时候不输入密码.
```