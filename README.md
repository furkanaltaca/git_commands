# git commands

### projeye git eklemek
- git init
### git configuration ayarları
- git config --global user.name "ad soyad"
- git config --global user.email "mail@gmail.com"
### git configuration'ları listeleme
- git config --list
- git config --list --global
- git config user.name
- git config user.email
### dosyaların durumuna bakmak
- git status
- git status -s
### dosyayı(ları) git'e eklemek
- git add .
- git add fileName.txt
- git add directory/fileName.txt
### commit işlemi
- git commit -m 'do commit process'
- git commit -m "Burası commit başlığımız" -m "Burası içeriğimizin ilk satırı" -m "Burası içeriğimizin ikinci satırı." -m "Bu da son olsun bari"
### branch oluşturma
- git branch new-branch
### branch'e geçiş yapmak
- git checkout new-branch
### branch oluşturup aynı zamanda o branch'e geçiş yapmak
- git checkout -b new-branch
### logları görüntülemek
- git log --oneline
- git log --author="John"
- git log --author="John\|Mary"
- git log --graph --oneline --decorate
- git log --pretty=oneline
- git log --pretty=short
- git log --pretty=medium
- git log --pretty=format:"%cn committed %h on %cd"
- git log --name-status
- git log --name-status --pretty=oneline
- git log --after="yesterday"
- git log --after="2014-7-1" --before="2014-7-4"
- git log -- foo.py bar.py