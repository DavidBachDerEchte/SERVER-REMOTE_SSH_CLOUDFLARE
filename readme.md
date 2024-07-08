# Server Remote SSH Cloudflare

## Server Side

1. Go to your Server Terminal
2. Install cloudflared on your Server (Linux)
   ```bash
    wget https://github.com/cloudflare/cloudflared/releases/latest/download/cloudflared-linux-arm
    sudo cp ./cloudflared-linux-arm /usr/local/bin/cloudflared
    sudo chmod +x /usr/local/bin/cloudflared
    cloudflared -v
   ```
3. (Only the first time) Run ```cloudflared tunnel login``` in the Terminal and open the Link in a Browser window. Then Select the right domain. 
4. Run this command in your Server Terminal
   ```bash
    cloudflared tunnel create <TUNNEL NAME>
   ```
5. Now Run this ix the Terminal
   ```bash
    cloudflared tunnel route dns <TUNNEL NAME> <ssh.example.com>
   ```
6. Now Run
   ```bash
    cloudflared tunnel run <TUNNEL NAME>
   ```

## Client Side
1. Go to ```https://developers.cloudflare.com/cloudflare-one/connections/connect-networks/downloads/``` and install via Terminal cloudflared on the client device
2. In your Terminal Run ```cloudflared access ssh-config --hostname <ssh.example.com>```
3. Access your ssh-config file
4. Add the code from the Terminal that was Generated to the ssh-config file.

## Test
Now you can test your connection type into your Terminal ```<username>@<ssh.example.com>```


## Source
https://www.youtube.com/watch?v=lq7WpGJZvk4&ab_channel=Cloudflare

https://developers.cloudflare.com/cloudflare-one/connections/connect-networks/use-cases/ssh/#native-terminal

https://developers.cloudflare.com/cloudflare-one/connections/connect-networks/get-started/create-local-tunnel/

https://developers.cloudflare.com/cloudflare-one/connections/connect-networks/downloads/
