# 🧰 MyIP - A Better IP Toolbox

<div align="center">

![IPCheck.ing Banner](https://raw.githubusercontent.com/jason5ng32/MyIP/main/public/github/gh_banner.png)

<a href="https://trendshift.io/repositories/5332" target="_blank"><img src="https://trendshift.io/api/badge/repositories/5332" alt="jason5ng32%2FMyIP | Trendshift" style="width: 250px; height: 55px;" width="250" height="55"/></a>

[![Mentioned in Awesome Self Hosted](https://awesome.re/mentioned-badge.svg)](https://github.com/awesome-selfhosted/awesome-selfhosted)

![GitHub Repo stars](https://img.shields.io/github/stars/jason5ng32/MyIP)
![GitHub forks](https://img.shields.io/github/forks/jason5ng32/myip)
![Docker Pulls](https://img.shields.io/docker/pulls/jason5ng32/myip)

[![Website](https://img.shields.io/website?url=https%3A%2F%2Fipcheck.ing&up_message=online&label=IPCheck.ing 'IPCheck.ing')](https://ipcheck.ing)
![PWA](https://img.shields.io/badge/PWA-Supported-blue)

![CodeQL](https://github.com/jason5ng32/MyIP/actions/workflows/github-code-scanning/codeql/badge.svg?branch=main)
![Docker Build and Push](https://github.com/jason5ng32/MyIP/actions/workflows/docker-image.yml/badge.svg?branch=main)

🇺🇸 [English](README.md) | 🇨🇳 [简体中文](README_ZH.md) | 🇫🇷 [Français](README_FR.md)

👉 Demo: [https://ipcheck.ing](https://ipcheck.ing)

Feel free to bookmark the demo or deploy your own.

[![Deploy with Docker](https://raw.githubusercontent.com/jason5ng32/MyIP/main/public/github/Docker.svg)](https://hub.docker.com/r/jason5ng32/myip)

</div>

## 👀 Main Features

* 🛜 **View Your IPs**: Detects and displays your local IPs, sourcing from multiple IPv4 and IPv6 providers.
* 🔍 **Search IP Information**: Provides a tool for querying information about any IP address. 
* 🕵️ **IP Information**: Presents detailed information for all IP addresses, including country, region, ASN, geographic location, and more.
* 🚦 **Availability Check**: Tests the accessibility of various websites, such as Google, GitHub, YouTube, ChatGPT, and others.
* 🚥 **WebRTC Detection**: Identifies the IP address used during WebRTC connections.
* 🛑 **DNS Leak Test**: Shows DNS endpoint data to evaluate the risk of DNS leaks when using VPNs or proxies.
* 🚀 **Speed Test**：Test your network speed with edge networks.
* 🚏 **Proxy Rule Testing**: Test the rule settings of proxy software to ensure their correctness.
* ⏱️ **Global Latency Test**: Performe lantency tests on servers located in different regions around the world.
* 📡 **MTR Test**: Perform MTR tests on servers located in different regions around the world.
* 🔦 **DNS Resolver**: Performs DNS resolution of a domain name from multiple sources and obtains real-time resolution results that can be used for contamination determination.
* 🚧 **Censorship Check**: Check if a website is blocked in some countries.
* 📓 **Whois Search**: Perform whois information search for domain names or IP addresses
* 📀 **MAC Lookup**: Query information of a physical address
* 🖥️ **Browser Fingerprints**：Multiple ways to caculate your browser fingerprint
* 📋 **Cybersecurity Checklist**：A comprehensive cybersecurity checklist with a total of 258 items

## 💪 Also

* 🌗 **Dark Mode**: Automatically toggles between dark and daylight modes based on system settings, with an option for manual switching.
* 📱 **Minimalist Mode**: A mobile-optimized mode that shortens page length for quick access to essential information..
* 📲 **PWA Supported**：Can be added as a desktop app on your phone as well as a Chrome app on your computer.
* ⌨️ **Keyboard Shortcuts**: Supports keyboard shortcuts for all functions, press `?` to view the shortcut list.
* 🌍 Based on availability test results, it indicates whether global internet access is currently feasible.
* 🇺🇸 🇨🇳 🇫🇷 English, Chinese, and French support.

## 📕 How to Use

### Deploying in a Node Environment

Make sure you have Node.js installed.

Clone the code:

```bash
git clone https://github.com/jason5ng32/MyIP.git
```

Install and build:

```bash
npm install && npm run build
```

Run:

```bash
npm start
```

The program will run on port 18966.

### Using Docker

Click the 'Deploy to Docker' button at the top to complete the deployment. Or, use the following shell:

```bash
docker run -d -p 18966:18966 --name myip --restart always jason5ng32/myip:latest
```

## 📚 Environment Variable

You can use the program without adding any environment variables, but if you want to use some advanced features, you can add the following environment variables:

| Variable Name | Required | Default Value | Description |
| --- | --- | --- | --- |
| `BACKEND_PORT` | No | `"11966"` | The running port of the backend part of the program |
| `FRONTEND_PORT` | No | `"18966"` | The running port of the frontend part of the program |
| `SECURITY_RATE_LIMIT` | No | `"0"` | Controls the number of requests an IP can make to the backend server every 60 minutes (set to 0 for no limit) |
| `SECURITY_DELAY_AFTER` | No | `"0"` | Controls the first X requests from an IP every 20 minutes that are not subject to speed limits, and after X requests, the delay will increase |
| `SECURITY_BLACKLIST_LOG_FILE_PATH` | No | `"logs/blacklist-ip.log"` | Path setting. Records the list of IPs that triggered the limit after SECURITY_RATE_LIMIT is enabled |
| `GOOGLE_MAP_API_KEY=` | No | `""` | API Key for Google Maps, used to display the location of the IP on a map |
| `ALLOWED_DOMAINS` | No | `""` | Allowed domains for access, separated by commas, used to prevent misuse of the backend API |
| `IPCHECKING_API_KEY` | No | `""` | API Key for IPCheck.ing, used to obtain accurate IP geolocation information |
| `IPINFO_API_TOKEN` | No | `""` | API Token for IPInfo.io, used to obtain IP geolocation information through IPInfo.io |
| `IPAPIIS_API_KEY` | No | `""` | API Key for IPAPI.is, used to obtain IP geolocation information through IPAPI.is |
| `IP2LOCATION_API_KEY` | No | `""` | API Key for IP2Location.io, used to obtain IP geolocation information through IP2Location.io |
| `CLOUDFLARE_API` | No | `""` | API Key for Cloudflare, used to obtain AS system information through Cloudflare |
| `MAC_LOOKUP_API_KEY` | No | `""` | API Key for MAC Lookup, used to obtain MAC address information |
| `IPCHECKING_API_ENDPOINT` | **Yes** | `""` | IPCheck.ing API endpoint |
| `VITE_GOOGLE_ANALYTICS_ID` | **Yes** | `""` | Google Analytics ID, used to track user behavior |
| `VITE_CURL_IPV4_DOMAIN` | No | `""` | Provides the IPv4 domain for the CURL API to users |
| `VITE_CURL_IPV6_DOMAIN` | No | `""` | Provides the IPv6 domain for the CURL API to users |
| `VITE_CURL_IPV64_DOMAIN` | No | `""` | Provides the dual-stack domain for the CURL API to users |

Note that if any of the CURL series environment variables are missing, the CURL API will not be enabled.

### Using Environment Variables in a Node Environment

Create environment variables:

```bash
cp .env.example .env
```

Modify `.env`, and for example, add the following:

```bash
BACKEND_PORT=11966
FRONTEND_PORT=18966
GOOGLE_MAP_API_KEY="YOUR_KEY_HERE"
ALLOWED_DOMAINS="example.com"
IPCHECKING_API="YOUR_KEY_HERE"
```

Then restart the backend service.

### Using Environment Variables in Docker

You can add environment variables when running Docker, for example:

```bash
docker run -d -p 18966:18966 \
  -e GOOGLE_MAP_API_KEY="YOUR_KEY_HERE" \
  -e ALLOWED_DOMAINS="example.com" \
  -e IPCHECKING_API="YOUR_TOKEN_HERE" \
  --name myip \
  jason5ng32/myip:latest

```

## 👩🏻‍💻 Advanced Usage

If you're using a proxy for internet access, consider adding this rule to your proxy configuration (modify it according to your client). This setup lets you check both your real IP and the IP when using the proxy:

```ini
# IP Testing
IP-CIDR,1.0.0.2/32,Proxy,no-resolve
IP-CIDR6,2606:4700:4700::1111/128,Proxy,no-resolve
DOMAIN,4.ipcheck.ing,DIRECT
DOMAIN,6.ipcheck.ing,DIRECT
# Rule Testing
DOMAIN,ptest-1.ipcheck.ing,Proxy1
DOMAIN,ptest-2.ipcheck.ing,Proxy2
DOMAIN,ptest-3.ipcheck.ing,Proxy3
DOMAIN,ptest-4.ipcheck.ing,Proxy4
DOMAIN,ptest-5.ipcheck.ing,Proxy5
DOMAIN,ptest-6.ipcheck.ing,Proxy6
DOMAIN,ptest-7.ipcheck.ing,Proxy7
DOMAIN,ptest-8.ipcheck.ing,Proxy8
```

## 😶‍🌫️ Additional Notes

When version 2.0 was released, I said that 70% of the code for this program was not written by me, but by ChatGPT. After about 90 interactions, plus some minor manual adjustments, the entire codebase was completed.

Of course, the architecture and UI still required my own design.

With the release of version 3.0 and subsequent versions, the proportion of code written with the help of ChatGPT has gradually decreased, now estimated to be between 40% and 50%. On the contrary, in this process, I went from having no knowledge of JavaScript and Vue to being able to understand most of the JS code, and I can now write some on my own.

Thanks to AI, it has given me, an unemployed product manager, a rapid opportunity to learn programming.

## 🌟 Star History

[![Star History Chart](https://api.star-history.com/svg?repos=jason5ng32/MyIP&type=Date)](https://star-history.com/#jason5ng32/MyIP&Date)

## 💖 Sponsors

As a open source project, I'm very grateful to the following sponsors for their support:

<a href="https://www.digitalocean.com/?refcode=fd2634a3981b&utm_campaign=Referral_Invite&utm_medium=Referral_Program&utm_source=badge"><img src="https://opensource.nyc3.cdn.digitaloceanspaces.com/attribution/assets/SVG/DO_Logo_horizontal_blue.svg" height="40px" title="DigitalOcean" /></a>

<a href="https://www.cloudflare.com/lp/project-alexandria/"><img src="https://cf-assets.www.cloudflare.com/zkvhlag99gkb/69RwBidpiEHCDZ9rFVVk7T/092507edbed698420b89658e5a6d5105/CF_logo_stacked_blktype.png" alt="Cloudflare Project Alexandria" title="Cloudflare Project Alexandria" height="60px" /></a>
