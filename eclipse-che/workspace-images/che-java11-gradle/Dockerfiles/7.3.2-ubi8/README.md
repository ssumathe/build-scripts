# Steps for creating che-java11-greadle docker image on POWER

1. Execute following command:
```bash
git clone https://github.com/keeganwitt/docker-gradle.git
```
2. Download following files from this page:
Dockerfile
3. Execute following commands:
```bash
mv Dockerfile docker-gradle/jdk11/Dockerfile
cd docker-gradle/jdk11/
```
4. Build the image:
```bash
docker build -t <repository> Dockerfile .
docker push <repository>/gradle-jdk11:ppc64le
```
5. Execute following commands:
 
 ```bash
git clone -b 7.3.x https://github.com/eclipse/che-devfile-registry.git
git checkout tags/7.3.2
rm -rf che-devfile-registry/arbitrary-users-patch/base_images
mv base_images che-devfile-registry/arbitrary-users-patch
```
3.Build gradle-jdk11

```bash
./build_images.sh
```
4.Tag gradle-jdk11

```bash
docker tag <image_id> <tag_name>
docker push <repository_name>
```
