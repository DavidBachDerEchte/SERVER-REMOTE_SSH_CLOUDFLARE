### Raspi Remote SSH Cloudflare

## Raspiberry Side

1. Go to your Raspi Terminal
2. Install cloudflared on your Raspi
   ```bash
    wget https://github.com/cloudflare/cloudflared/releases/latest/download/cloudflared-linux-arm
    sudo cp ./cloudflared-linux-arm /usr/local/bin/cloudflared
    sudo chmod +x /usr/local/bin/cloudflared
    cloudflared -v
   ```
3. Run this command into your Raspi Terminal
   ```bash
    cloudflared tunnel create <TUNNEL NAME>
   ```
4. Now Run this into the Terminal
   ```bash
    cloudflared tunnel route dns <TUNNEL NAME> <ssh.example.com>
   ```
5. Now Run
   ```bash
    cloudflared tunnel run <TUNNEL NAME>
   ```

## Client Side
1. Go to ```https://developers.cloudflare.com/cloudflare-one/connections/connect-networks/downloads/``` and install via Terminal cloudflared on the client device
2. In your Terminal Run ```cloudflared access ssh-config --hostname <ssh.example.com>```
3. Access your ssh-config file
4. Add the code from the Terminal that was Generated
