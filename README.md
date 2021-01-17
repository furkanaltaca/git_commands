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
### branch listeleme
- git branch
- git branch --all
### branch oluşturma
- git branch new-branch
### branch'e geçiş yapmak
- git checkout new-branch
### branch oluşturup aynı zamanda o branch'e geçiş yapmak
- git checkout -b new-branch
### branch silmek
- git branch -d silinecek_branch
- git branch --delete silinecek_branch => -d ve --delete aynıdır. merge işlemini yapmadıysanız uyarı alırsınız. merge yapmadan silmek istiyorsanız force işlemi uygulamalısınız. bir sonraki işlem bunun için.
- git branch -D silinecek_silinecek_branch => büyük D, silmeye zorlar (force). yani yazdığınız kodları merge edip etmemenizi umursamaz. yazdıklarınız kaybolup gider.
### branch merge işlemi
- git checkout master && git merge feature_branch
### git reset işlemi
- git log --oneline => commit hash'ini almak için 
- git reset --soft commit_hash => --soft parametresi yaptığınız değişiklikleri korur ve staged halde tutar. commit mesajını yanlış yazdıysanız bu işlemi uyguladıktan sonra commit mesajınızı yeniden yazıp commit edebilirsiniz.
- git reset --mixed commit_hash => --mixed parametresi ile yaptığımız commit'i geri alırız ve yaptığımız değişiklikler staged edilmemiş olarak gelir. yani "git add file_name.txt" komutuyla staged edip commit etmemiz gerekir. 
- git reset --hard commit_hash => --hard parametresiyle çalıştırırsanız yaptığınız tüm değişiklikleri silerek belirtilen commit'e gidersiniz. zamanda yolculuk yaptırır. kullanması tehlikelidir çünkü yaptığınız önemli bir şey varsa boşa gider. kullanırken DİKKATLİ OLUNUZ. 
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