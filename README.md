# MagicSniffer

> We have posted an article about this on [sdl.moe](https://sdl.moe/): [原神 2.8 KCP 验证密钥交互流程解析与流量解密](https://sdl.moe/post/magic-sniffer/)

As everyone knows, RSA is the most secure way to encrypt data, but RSA could not prevent **MAGIC** from `WindSeedClientNotify`.

MagicSniffer is a amazing tool could help you decrypt GI traffic by **MAGIC** of `WindSeedClientNotify`.

## Usage

1. Install

```shell
npm install
```

2. Edit `config.json`, locate your GI traffic file.

3. Run

```shell
node app.js
```

## Credit

- [Crepe-Inc/Iridium](https://github.com/Crepe-Inc/Iridium)

## Usage

Search and mod:

- `plainLoginHead` to `4567` + `PlayerLoginReq` HEX CmdId
- `plainWindSeedHead` to `4567` + `PlayerInjectFixNotify` HEX CmdId
- `plainRTTHead` to  `4567` + `WorldPlayerRTTNotify` (or any other packet always don't have Packet Head) HEX CmdId
- `packetSource` if the server's port is not `22101` or `22102`

And file:

- `plaintext.bin` for the full `PlayerInjectFixNotify` body and trailing `89AB`
- `config.json` for path of pcap file (Captured by Wireshark, format: Wireshark/tcpdump `.pcap`)
