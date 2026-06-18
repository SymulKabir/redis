### Radis Database installation 

#### Radis install on Docker
```bash
docker run -d \
  --name redis \
  -p 6379:6379 \
  -v redis-data:/data \
  redis \
  redis-server --appendonly yes
  ```

#### Radis install on Ubuntu
Update packages
```bash
sudo apt update
```

Install Redis:
```bash
sudo apt install redis-server -y
```
Check version:
```bash
redis-server --version
```
Start Redis:
```bash
sudo systemctl start redis-server
```
Enable auto-start on boot:
```bash
sudo systemctl enable redis-server
```
Check status:
```bash
sudo systemctl status redis-server
```

Test Redis:
```bash
redis-cli ping
```
Expected output:
```
PONG
```
**Enable Persistence**
Open the config file:
```bash
sudo nano /etc/redis/redis.conf
```
For AOF persistence, find:
```bash
appendonly no
```
Change to:
```
appendonly yes
```

Restart Redis:
```bash
sudo systemctl restart redis-server
```








