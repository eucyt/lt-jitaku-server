---
marp: true
theme: gaia
_paginate: true
---
<style>
@import url('https://fonts.googleapis.com/css2?family=M+PLUS+1+Code&display=swap');
section {
    font-family: 'M PLUS 1 Code', monospace;
}
section.title {
    justify-content: center;
}

section figure:first-child{
    margin-left: 20px !important;
}
</style>


<!--
_class: lead
_paginate: false
_header: ""
-->
# ぼくの自宅サーバー育成日記
---

# サーバー2台時代

![bg left:35% contain](img/physical-v1.drawio.png)

- サーバー2台構成でProxmox Cluster
- ストレージはNAS(openmediavault)で用意
- 前段にReverseProxyを用意。それを経由して自宅ネットワークへ接続

---

# HA構成・Ceph時代

![bg left:40% contain](img/physical-v2.drawio.png)

- サーバー3台構成でProxmox Cluster
  - → HA構成へ
- ストレージはCeph Clusterで用意
  - ~~Cephのご機嫌取りはここから~~
- しばらくこの構成のままで運用

---

# Kubernetes Migration

![bg left:40% contain](img/k9s.png)

- Proxmox Cluster上にVMを6台構築
  - Control plane 3台
  - Worker Node 3台
- ほとんどをVM,CTからKubernetesに移行

---

# 現在の構成

![bg left:60% contain](img/physical-v3.drawio.png)

- Region 2（一人暮らし）へ大移動
- Reverse proxyからCloudflare tunnelsへ
- CephからTeraStationへ
- 4台+VPN1台構成へ

---

![bg contain](img/proxomox.png)

---

# 載せているアプリケーション

- 自作アプリケーションのバックエンド
  - [MyNote](https://mynote.euchi.jp/)
  - [MyTalk](https://mytalk.euchi.jp/)
  - MyPaper
- マイクラサーバー
- Grafana, Prometheus
- SwitchBot
- SoftEther ...

