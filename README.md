# Theia Cloud IDE

Theia Cloud IDE installation scripts.

## Setup

### Requirements

Node.js and Yarn:

```sh
curl -sL https://deb.nodesource.com/setup_12.x | sudo -E bash -
sudo apt install -y nodejs
sudo npm i -g corepack
```

Additional tools and libraries:

```sh
sudo apt install build-essential pkg-config \
    libx11-dev libxkbfile-dev libsecret-1-dev
```

### Installation

```sh
git clone https://github.com/ecanuto/theia-cloud.git /opt/theia
cd /opt/theia
yarn setup
```

Install systemd service:

```sh
sudo ln -s /opt/theia/lib/theia@.service /etc/systemd/system/theia@.service

systemctl daemon-reload
systemctl enable theia@$USER
systemctl start theia@$USER
```
