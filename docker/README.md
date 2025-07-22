# openfreemap
My hosting attempt of OpenFreeMap

## TODO
- Use alping for docker image when done to slim it down?

## Development & Debug
Use `tools/docker-compose.yml` for debug purpose.

## References
[Open Free Map](https://openfreemap.org/)

## Test
```bash
curl -sI https://ofm.lab.localhost:8080/monaco | sort
curl -sI https://ofm.lab.localhost:8080/monaco/19700101_old_version_test | sort
curl -sI https://ofm.lab.localhost:8080/monaco/19700101_old_version_test/14/8529/5975.pbf | sort
curl -sI https://ofm.lab.localhost:8080/monaco/19700101_old_version_test/9999/9999/9999.pbf | sort
```
 ________________________________________________

https://github.com/Overv/openstreetmap-tile-server
  https://hub.docker.com/r/overv/openstreetmap-tile-server/

https://medium.com/@rajitha.mail48/create-a-docker-image-of-an-offline-open-street-map-server-9fdedd433cc8


apt update && apt install openssh-server && /usr/sbin/openssh -D
/etc/init.d/ssh start
ssh-keygen -t ed25519 -C "your_email@example.com"
cp /root/.ssh/id_ed25519.pub ~/.ssh/authorized_keys

python3 -m venv py_envs
source /checkout/openfreemap/py_envs/bin/activate
pip install -e .
./init-server.py http-host-static 127.0.0.1 -y
\ No newline at end of file
./init-server.py http-host-static 127.0.0.1 -y


monaco 20250719_231000_pt

Downloading btrfs: monaco 20250719_231000_pt
  downloading https://btrfs.openfreemap.com/areas/monaco/20250719_231000_pt/tiles.btrfs.gz into /data/ofm/http_host/runs/_tmp/tiles.btrfs.gz


less /etc/fstab

/checkout/test/a /checkout/test/b

/checkout/test/a /checkout/test/a btrfs ro 0 0




https://github.com/moby/moby/issues/9950
@tbronchain You cannot call mount unless you have CAP_SYS_ADMIN, which is not available in the default container config. You'd need to docker run --cap-add SYS_ADMIN



data/ofm/http_host/runs/monaco/20250720_231000_pt/tiles.btrfs /mnt/ofm/monaco-20250720_231000_pt btrfs loop,ro 0





## TODO
- Start nginx
- mount files




http://localhost:8080/styles/liberty.json



```conf
server {
    listen 80;
    server_name localhost;

    location / {
        default_type text/plain;
        return 200 'Hello, World!';
    }
}
```

http://localhost/styles/liberty

curl -sI http://localhost/monaco | sort
