## 1) 실행 환경
- OS: macOS Sequoia 15.7.4
- Shell: bash
- Docker 엔진: OrbStack
- Docker: version 28.5.2
- Git: version 2.53.0

## 2) 수행 체크리스트
- [x] 터미널 기본 조작 및 폴더 구성
- [x] 권한 변경 실습
- [x] Docker 설치/점검
- [x] hello-world 실행
- [x] Dockerfile 빌드/실행
- [x] 포트 매핑 접속(2회)
- [x] 바인드 마운트 반영
- [x] 볼륨 영속성
- [x] Git 설정 + VSCode GitHub 연동

## 3) 수행 로그(발췌)
### 터미널 명령어
$ pwd
```
tkdgjs01196630@c5r2s4 ~ % pwd
/Users/tkdgjs01196630
```
$ ls -al
```
tkdgjs01196630@c5r2s4 ~ % ls -al
total 8
drwxr-x---+ 18 tkdgjs01196630  tkdgjs01196630   576 Aug 11 15:01 .
drwxr-xr-x   7 root            admin            224 Aug 11 14:33 ..
-r--------   1 tkdgjs01196630  tkdgjs01196630     8 Aug 11 14:33 .CFUserTextEncoding
drwxr-xr-x   5 tkdgjs01196630  tkdgjs01196630   160 Aug 11 15:01 .docker
drwxr-xr-x  10 tkdgjs01196630  tkdgjs01196630   320 Aug 11 15:01 .orbstack
drwxr-xr-x   3 tkdgjs01196630  tkdgjs01196630    96 Aug 11 15:01 .ssh
drwx------+  2 tkdgjs01196630  tkdgjs01196630    64 Aug 11 14:34 .Trash
drwxr-xr-x   5 tkdgjs01196630  tkdgjs01196630   160 Aug 11 14:36 .vscode
drwx------+  3 tkdgjs01196630  tkdgjs01196630    96 Aug 11 14:33 Desktop
drwx------+  3 tkdgjs01196630  tkdgjs01196630    96 Aug 11 14:33 Documents
drwx------+  3 tkdgjs01196630  tkdgjs01196630    96 Aug 11 14:33 Downloads
drwx------@ 78 tkdgjs01196630  tkdgjs01196630  2496 Aug 11 15:02 Library
drwx------   3 tkdgjs01196630  tkdgjs01196630    96 Aug 11 14:33 Movies
drwx------+  3 tkdgjs01196630  tkdgjs01196630    96 Aug 11 14:33 Music
drwx------   4 tkdgjs01196630  tkdgjs01196630   160 Aug 11 15:01 OrbStack
drwx------+  4 tkdgjs01196630  tkdgjs01196630   128 Aug 11 14:33 Pictures
drwxr-xr-x+  4 tkdgjs01196630  tkdgjs01196630   128 Aug 11 14:33 Public
-rw-r--r--   1 tkdgjs01196630  tkdgjs01196630     0 Aug 11 14:43 README.md
```
$ cd
```
tkdgjs01196630@c5r2s4 ~ % cd codyssey 
tkdgjs01196630@c5r2s4 codyssey % 
```
$ mkdir
```
tkdgjs01196630@c5r2s4 ~ % mkdir codyssey
tkdgjs01196630@c5r2s4 ~ % ls
codyssey        Downloads       Music           Public
Desktop         Library         OrbStack        README.md
Documents       Movies          Pictures
```
$ cp
```
tkdgjs01196630@c5r2s4 ~ % cp test.txt codyssey/
tkdgjs01196630@c5r2s4 ~ % cd codyssey 
tkdgjs01196630@c5r2s4 codyssey % ls
test.txt
```
$ mv
```
tkdgjs01196630@c5r2s4 ~ % mv codyssey mv_test         
tkdgjs01196630@c5r2s4 ~ % ls
Desktop         Library         mv_test         Public
Documents       Movies          OrbStack        README.md
Downloads       Music           Pictures
```

$ rm
```
tkdgjs01196630@c5r2s4 ~ % rm -rf codyssey
tkdgjs01196630@c5r2s4 ~ % ls
Desktop         Library         OrbStack        README.md
Documents       Movies          Pictures        test.txt
Downloads       Music
```
$ cat
```
tkdgjs01196630@c5r2s4 ~ % cat test.txt 
hello world
```
$ touch
```
tkdgjs01196630@c5r2s4 ~ % touch touch_test.txt
tkdgjs01196630@c5r2s4 ~ % cat touch_test.txt 
tkdgjs01196630@c5r2s4 ~ % 
```
$ chmod
변환 전
```
tkdgjs01196630@c5r2s4 codyssey % ls -al
total 0
drwxr-xr-x   4 tkdgjs01196630  tkdgjs01196630  128 Aug 11 15:27 .
drwxr-x---+ 21 tkdgjs01196630  tkdgjs01196630  672 Aug 11 15:27 ..
drwxr-xr-x   2 tkdgjs01196630  tkdgjs01196630   64 Aug 11 15:27 ch_dir
-rw-r--r--   1 tkdgjs01196630  tkdgjs01196630    0 Aug 11 15:25 touch_test.txt
```
변환 후
```
tkdgjs01196630@c5r2s4 codyssey % chmod 777 touch_test.txt 
tkdgjs01196630@c5r2s4 codyssey % chmod 700 ch_dir 
tkdgjs01196630@c5r2s4 codyssey % ls -al
total 0
drwxr-xr-x   4 tkdgjs01196630  tkdgjs01196630  128 Aug 11 15:27 .
drwxr-x---+ 21 tkdgjs01196630  tkdgjs01196630  672 Aug 11 15:27 ..
drwx------   2 tkdgjs01196630  tkdgjs01196630   64 Aug 11 15:27 ch_dir
-rwxrwxrwx   1 tkdgjs01196630  tkdgjs01196630    0 Aug 11 15:25 touch_test.txt
```
### Docker
