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
openclaw gateway restart
```