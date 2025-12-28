# General Info


### Can I use port forwarding on my home router to make my physical machine accessible on the internet like a machine on hostinger(Docker compose)?
- Yes, but with important limitations. Dynamic IP, CG-NAT, ISP Port Blocking, Security Risks.
- CG-NAT
  - Open router admin → WAN / Internet IP
  - Compare with whatismyip
  - Same IP	You have real public IP, Different IP	🚨 CG-NAT (no port forwarding possible)
- http://<your-public-ip>:8080 - nothing should be visible as no service is running and if you forward the port then -> 

## Hosting your site.
- You can host your site using various sites like(netlify, vercel, github, render) and others.
- Vscode portforwarding can also be used.
- Github codespaces can also be used.
- In cmd "ngrok http <port>" - port of localhost where you app is running can be used.

#### Using ngrok/ Cloudflare Tunnel / Tailscale / ZeroTier
- Install ngrok
- Connect ngrok to your account
- Start local server
- Expose it with ngrok
- ngrok http <port>

#### Hosting your local directory
- you can use live server using vscode and then ngrok
- you can also use npm i -g serve (this will be used to create a local server)
-  serve . (creates a server accessible on the network), to access on the internet you can use ngrok to forward this local network

#### Port forwarding using Vscode
- In VScode open ctrl+shift+p -> Forward a Port -> port number to forward -> give it a name.
## Windows
- winget upgrade - how many software needs update
- winget upgrade --all - will update.


### Option A: Ngrok (or similar tunneling)

- Ngrok runs a **client** on your server.  
- This client initiates an **outbound connection** to Ngrok’s cloud server (which has a public IP).  
- Now, when someone accesses the Ngrok public URL:
  1. The request hits Ngrok’s **cloud server**.  
  2. The cloud server **forwards the request through the existing tunnel** back to your server.  
- Your server **never needed a public IP**, because the connection was initiated **outbound** from inside your network.  

**Key point:** The connection is always initiated from your local network to the cloud. The outside user **never connects directly** to your local IP.  

---

### Option B: Twingate

- Twingate also uses a similar principle but in a more **structured, secure way**:  
  1. You run a **Twingate connector** on your local network.  
  2. The connector establishes a **secure, persistent outbound connection** to Twingate’s cloud.  
  3. When a remote user wants access, their Twingate client **authenticates**, and the cloud **routes traffic through that secure tunnel** to your server.  
- Again, your server **never needs a public IP**. Only devices **authenticated with Twingate** can reach it.


## Github

- open repo press . to open it in vscode or change url github.com to github.dev
- open repo edit url instead of github type gitingest.

## localhost
- [What REALLY Happens When You Type Localhost?](https://youtu.be/PwNJXUdMkVY)
