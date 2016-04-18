## Docker container for A Typical Brands Magento application

1) Clone this repository
```bash
git clone git@github.com:nas1k/atb.mage.git
```
2) Load your mysql dump to seed directory
3) Run docker compose
```bash
docker-composer up
```
4) Go to mysql container and load your dump to database
```bash
docker exec -it atbmage_db_1 bash
mysql -uroot -pabcABC123 mage < dump.sql
```
5) Add host to /etc/hosts (run this command from root user)
```bash
echo `docker inspect --format '{{ .NetworkSettings.IPAddress }}' atbmage_web_1`"    local.numeproducts.com" >> /etc/hosts
```
6) Go to http://local.numeproducts.com/ from your browser
