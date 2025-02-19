	### Proxy Commands

#### Fish Commands
```fish
set HTTP_PROXY=http://proxy_userid:proxy_password@proxy_ip:proxy_port
set HTTP_PROXY=http://165.225.76.32:80
set HTTP_PROXY=http://ambrosep:$PASSWD@appgw.gnb.st.com:8080
```

#### Bash Proxy Commands
```bash
export http_proxy="http://ambrosep:$PASS@appgw.gnb.st.com:8080"
export https_proxy="https://ambrosep:$PASS@appgw.gnb.st.com:8080"
```

#### Alternative Proxy Server
```bash
lps5.sgp.st.com:8080
```

#### Update PATH
```bash
export PATH=$PATH:"/mnt/c/ST/Tools/ispuai-2.1.1-x86_64-linux"
```

#### Proxy Command for Curl Downloads
```bash
curl --proxy http://appgw.gnb.st.com:8080 --proxy-user ambrosep:$PASS -L https://www.pyenv.run -k | fish
```

#### Proxy for APT Manager
1. Export the `http_proxy` and `https_proxy` like above:
    ```bash
    export http_proxy="http://ambrosep:$PASS@appgw.gnb.st.com:8080"
    export https_proxy="https://ambrosep:$PASS@appgw.gnb.st.com:8080"
    ```
2. Use `sudo -E` with `apt` or `apt-get`:
    ```bash
    sudo -E apt-get update
    sudo -E apt-get install <package_name>
    ```

#### Git Proxy Configuration
```bash
git config --global http.proxy http://ambrosep:$PASS@appgw.gnb.st.com:8080
```

#### PIP Proxy Configuration
Run the following commands in the command line or on each environment:
```bash
set http_proxy=http://165.225.76.32:80
set https_proxy=http://165.225.20.12:80
```

#### STM Credentials
- **Email:** premkumar.ambrose@st.com
- **Password:** 30&YdosR@GwQ

## FISH SHELL
 function fish_pip
	  set USER_temp ambrosep
	  set PORT 8080
	  set -l PW (openssl aes-256-cbc -d -in "/home/sdai/.scripts/pw.bin" -iter 20)
	  set PROXY "http://$USER_temp:$PW@appgw.gnb.st.com:$PORT/"
	  pip --proxy=$PROXY --trusted-host=pypi.python.org --trusted-host=pypi.org --trusted-host=files.pythonhosted.org install $argv
  end

# [[Proxy Password change]]
