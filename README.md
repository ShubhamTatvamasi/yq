# yq

Install yq:
```bash
VERSION=$(curl -s https://github.com/mikefarah/yq/releases/latest | grep -o "v[0-9]\.[0-9]*\.[0-9]*")
BINARY=yq_linux_amd64

sudo wget https://github.com/mikefarah/yq/releases/download/${VERSION}/${BINARY} -O /usr/local/bin/yq
sudo chmod +x /usr/local/bin/yq
```

Fix yml files:
```bash
find . -type f -name '*.yml' -exec \
  bash -c 'yq e -i {}' \;
```
