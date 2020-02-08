# 如何选择IPv6网段

此指南针对于提供`/128`的野蛮VPN，提供`/64`及更小的文明VPN请高强度Relay（中继），获取全球唯一单播地址`2001:0000::/23`，，，
> [其实应该是`2001:0200::/23`](https://www.iana.org/assignments/ipv6-unicast-address-assignments/ipv6-unicast-address-assignments.xhtml)
---
在特殊环境（IPv6通过家里到学校的连接）下，选择IPv6网段有如下建议：

## unique local address (ULA)
**优选**
* 网段：`fc00::/7`
> The address block fc00::/7 is divided into two parts, fc00::/8 and fd00::/8.
> The block fc00::/8 is undefined...
* 示例：`fd11:4514:1919:810::/64`
> 上述摘自维基百科 [Unique local address](https://en.wikipedia.org/wiki/Unique_local_address)
* 特点：作为IPv4不通时的次选
* 注意：Windows表示为“”
* 优选原因：打开常用网站时直接走宽带，仅IPv6网络才使用，避免无谓的代理

## IANA Reserved
**次选**
* 网段：[**任君挑选**](https://www.iana.org/assignments/ipv6-address-space/ipv6-address-space.xhtml)
* 示例：`c123::/64`
* 示例2：`d456::/64`
* **示 例 1 1 4 5 1 4 ：`114:514:1919:810::/64`**
* 特点：优先连接
* 次选原因：所有网站优先代理

## Link local address
**禁选**
* 网段：`fe80::/10`
* 示例：`fe80:114:514:1919::/64`
* 特点：无法连接
