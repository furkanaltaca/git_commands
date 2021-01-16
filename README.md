# git_commands

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
### branch oluşturma:
- git branch new-branch
### branch'e geçiş yapmak
- git checkout new-branch
### branch oluşturup aynı zamanda o branch'e geçiş yapmak
- git checkout -b new-branch
### logları görüntülemek
- git log --graph --oneline --decorate
- git log --pretty=format:"%cn committed %h on %cd"
- git log --after="yesterday"
- git log --after="2014-7-1" --before="2014-7-4"
- git log --author="John"
- git log --author="John\|Mary"
- git log -- foo.py bar.py
