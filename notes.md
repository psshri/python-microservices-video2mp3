# to connect to mongodb
mongosh mongodb://psshri:zxcvfdsa@192.168.49.2:30005/mp3s?authSource=admin

# to connect to postgres
psql 'postgres://psshri:zxcvfdsa@192.168.49.2:30003/authdb'

# login endpoint
curl -X POST http://192.168.49.2:30002/login -u pshekhar830@gmail.com:zxcvfdsa

JWT Token: eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6InBzaGVraGFyODMwQGdtYWlsLmNvbSIsImV4cCI6MTcwNTEzNTgzNywiaWF0IjoxNzA1MDQ5NDM3LCJhZG1pbiI6dHJ1ZX0.uSKDb92mX9V8fq5oerW_Ec7HoSSSTrltlv5lwSA8MwY

# upload endpoint
curl -X POST -F 'file=@./video.mp4' -H 'Authorization: Bearer <JWT Token>' http://192.168.49.2:30002/upload

curl -X POST -F 'file=@./video.mp4' -H 'Authorization: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6InBzaGVraGFyODMwQGdtYWlsLmNvbSIsImV4cCI6MTcwNTEzNTgzNywiaWF0IjoxNzA1MDQ5NDM3LCJhZG1pbiI6dHJ1ZX0.uSKDb92mX9V8fq5oerW_Ec7HoSSSTrltlv5lwSA8MwY' http://192.168.49.2:30002/upload


ID : 65a0fe4400edebe402723116

# download endpoint
curl --output video.mp3 -X GET -H 'Authorization: Bearer <JWT Token>' "http://192.168.49.2:30002/download?fid=<Generated fid>"

curl --output video.mp3 -X GET -H 'Authorization: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6InBzaGVraGFyODMwQGdtYWlsLmNvbSIsImV4cCI6MTcwNTEzNTgzNywiaWF0IjoxNzA1MDQ5NDM3LCJhZG1pbiI6dHJ1ZX0.uSKDb92mX9V8fq5oerW_Ec7HoSSSTrltlv5lwSA8MwY' "http://192.168.49.2:30002/download?fid=65a0fe4400edebe402723116"