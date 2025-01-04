> Note: You will need [modern fonts](https://github.com/ryanoasis/nerd-fonts) to be able to view `Flags`
> - Specify `--ipv4 | --ipv6` or similar for `ipv4|ipv6` only data
---
- #### Simple (`text`) : [/](https://ip.quickso.cn/) `-->` [https://ip.quickso.cn/](https://ip.quickso.cn/)
> Returns plain `IPv4 | IPv6`
```bash
curl -qfsSL "https://ip.quickso.cn"
```
---
- #### Detailed (`csv`) : [/csv](https://ip.quickso.cn/csv) `-->` [https://ip.quickso.cn/csv](https://ip.quickso.cn/csv)
> Returns csv `IPv4 | IPv6`, `GeoInfo` & `User-Agent`
```bash
!#Using: curl + column
curl -qfsSL "https://ip.quickso.cn/csv" | column -ts ','
```
> <details><summary><code>Example Response</code></summary>
>
>```
> ip           city       country  flag  region     latitude   longitude  org         timezone           user-agent   readme
> 18.227.3.14  São Paulo  BR       🇧🇷    São Paulo  -23.53350  -46.63590  Amazon.com  America/Sao_Paulo  curl/7.88.1  https://github.com/muzihuaner/ip.quickso.cn
>```
> </details>
---
- #### Detailed (`html`) : [/html](https://ip.quickso.cn/html) `-->` [https://ip.quickso.cn/html](https://ip.quickso.cn/html)
> Returns HTML `IPv4 | IPv6`, `GeoInfo` & `User-Agent`
> <details><summary><code>Example Response</code></summary>
>
> ![image](https://github.com/muzihuaner/ip.quickso.cn/assets/58171889/39b9dd85-a2f0-4eb1-90c7-961ba6bc98f2)
> 
> </details>
---
- #### Detailed (`json`) : [/json](https://ip.quickso.cn/json) `-->` [https://ip.quickso.cn/json](https://ip.quickso.cn/json)
> Returns json `IPv4 | IPv6`, `GeoInfo` & `User-Agent`
```bash
!#Using: curl + https://github.com/jqlang/jq
curl -qfsSL "https://ip.quickso.cn/json" | jq '.'
```
> <details><summary><code>Example Response</code></summary>
>
> ```json
> {
> "ip": "18.227.3.14",
> "city": "São Paulo",
> "country": "BR",
> "flag": "🇧🇷",
> "region": "São Paulo",
> "latitude": "-23.53350",
> "longitude": "-46.63590",
> "org": "Amazon.com",
> "timezone": "America/Sao_Paulo",
> "user-agent": "curl/7.88.1",
> "readme": "https://github.com/muzihuaner/ip.quickso.cn"
> }
> ```
> </details>
---
- #### Detailed (`text`) : [/text](https://ip.quickso.cn/text) `-->` [https://ip.quickso.cn/text](https://ip.quickso.cn/text)
> Returns text `IPv4 | IPv6`, `GeoInfo` & `User-Agent`
```bash
curl -qfsSL "https://ip.quickso.cn/text"
```
> <details><summary><code>Example Response</code></summary>
>
> ```bash
> ip=18.227.3.14
> city=São Paulo
> country=BR
> flag=🇧🇷
> region=São Paulo
> latitude=-23.53350
> longitude=-46.63590
> org=Amazon.com
> timezone=America/Sao_Paulo
> user-agent=curl/7.88.1
> readme=https://github.com/muzihuaner/ip.quickso.cn
> ```
> </details>
---
- #### Detailed (`xml`) : [/xml](https://ip.quickso.cn/xml) `-->` [https://ip.quickso.cn/xml](https://ip.quickso.cn/xml)
> Returns xml `IPv4 | IPv6`, `GeoInfo` & `User-Agent`
```bash
!#Using: curl + https://github.com/sibprogrammer/xq
curl -qfsSL "https://ip.quickso.cn/xml" | xq
```
> <details><summary><code>Example Response</code></summary>
>
> ```xml
> <?xml version="1.0" encoding="UTF-8"?>
> <data>
>   <ip>18.227.3.14</ip>
>   <city>São Paulo</city>
>   <country>BR</country>
>   <flag>🇧🇷</flag>
>   <region>São Paulo</region>
>   <latitude>-23.53350</latitude>
>   <longitude>-46.63590</longitude>
>   <org>Amazon.com</org>
>   <timezone>America/Sao_Paulo</timezone>
>   <user-agent>curl/7.88.1</user-agent>
>   <readme>https://github.com/muzihuaner/ip.quickso.cn</readme>
> </data>
> ```
> </details>
---
- #### Detailed (`yaml`) : [/yaml](https://ip.quickso.cn/yaml) `-->` [https://ip.quickso.cn/yaml](https://ip.quickso.cn/yaml)
> Returns yaml `IPv4 | IPv6`, `GeoInfo` & `User-Agent`
```bash
!#Using: curl + https://github.com/mikefarah/yq
curl -qfsSL "https://ip.quickso.cn/yaml" | yq '.'
```
> <details><summary><code>Example Response</code></summary>
>
> ```yaml
> ip: "18.227.3.14"
> city: "São Paulo"
> country: "BR"
> flag: "🇧🇷"
> region: "São Paulo"
> latitude: "-23.53350"
> longitude: "-46.63590"
> org: "Amazon.com"
> timezone: "America/Sao_Paulo"
> user-agent: "curl/7.88.1"
> readme: "https://github.com/muzihuaner/ip.quickso.cn"
> ```
> </details> 
---
#### Deploy (Note to Self)
```bash
!# Install Wrangler: https://developers.cloudflare.com/workers/wrangler/install-and-update/
npm install "wrangler@latest" -g

!# Clone Source
git clone --filter="blob:none" "https://github.com/muzihuaner/ip.quickso.cn"
cd "./ip.quickso.cn"
code "./ip.quickso.cn"

!# Deploy
npm install ; wrangler login
wrangler deploy

!# Dashboard >> Workers & Pages >> ip-api >> Settings >> Custom Domains >> Add: ip.quickso.cn
```
