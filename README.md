# git commands

### init

- cd /project/path
- git init

### configs

- git config --global user.name "ad soyad"
- git config --global user.email "mail@gmail.com"
- git config --list
- git config --list --global
- git config user.name
- git config user.email

### list changes

- git status
- git status -s

### un/stage

- git add .
- git add fileName.txt
- git add directory/fileName.txt
- git restore --staged fileName.txt

### commit

- git commit -m 'do commit process'
- git commit -m "Burası commit başlığımız" -m "Burası içeriğimizin ilk satırı" -m "Burası içeriğimizin ikinci satırı." -m "Bu da son olsun bari"
- git show commit_hash
    <details>
    belirttiğimiz commit_hash'e sahip olan commit'in ayrıntılarını gösterir.
    </details>

### branch

- git branch
    <details>
    branch'ları listeler
    </details>
- git branch --all
    <details>
    remote'daki branchler ile beraber listeler
    </details>
- git branch new-branch
    <details>
    yeni branch oluşturur.
    </details>
- git checkout branch_name
    <details>
    belirtilen branch'e geçiş yapar.
    </details>
- git checkout -b new-branch
    <details>
    branch oluşturur ve geçiş yapar.
    </details>
- git checkout -t remote_branch_name
    <details>
    remote'da oluşturulan branch'i pull ile local repoya aldıktan sonra üzerinde işlem yapabilmek için remote branch'in ismiyle aynı olan bir branch oluşturur ve yapılan işlemleri pull ettiğimizde remote'daki branch'i günceller
    </details>
- git branch -d deleted_branch
    <details>
    branch'i siler.
    </details>
- git branch -D deleted_branch
    <details>
    büyük D, silmeye zorlar (force). merge yapmadan silmek istiyorsanız force işlemi uygulamalısınız. yani yazdığınız kodları merge edip etmemenizi umursamaz. yazdıklarınız kaybolur.
    </details>

### merge

- git checkout master
    <details>
    önce master branch'ine geçiş yapıyoruz. 
    </details>
- git merge feature_branch
    <details>
    şimdi ise feature_branch'ini bulunduğumuz branch'a (master) merge ediyoruz. feature_branch'da yapılan tüm değişiklikler master branch'ine gelmiş oldu.
    </details>
- git merge --abort
    <details>
    conflict oluştuğu zaman merge işlemini iptal etmek istersek kullanabiliriz. 
    </details>

### rebase

- git rebase master
    <details>
    develop branch'ine geçip master branch'ini rebase uygulamak için kullanılır. 
    </details>
- rebase aborting
    <details>
    öncelikle "git reflog" ile rebase işleminin başlatıldığı kaydı buluyoruz. daha sonra bir önceki kaydın id'sini kopyalıyoruz. "git reset id" işlemini uygulayarak rebase işlemini iptal edilir.
    </details>

### conflict

- oluşan conflict'leri çözmek için "sourcetree" veya "vscode" kullanmak işleri daha da kolaylaştırabilir.

### reset

- git log --oneline
    <details>
    commit hash'ini almak için 
    </details>
- git reset --soft commit_hash
    <details>
    --soft parametresi yaptığınız değişiklikleri korur ve staged halde tutar. commit mesajını yanlış yazdıysanız bu işlemi uyguladıktan sonra commit mesajınızı yeniden yazıp commit edebilirsiniz. 
    </details>
- git reset --mixed commit_hash
    <details>
    --mixed parametresi ile yaptığımız commit'i geri alırız ve yaptığımız değişiklikler staged edilmemiş olarak gelir. yani "git add file_name.txt" komutuyla staged edip commit etmemiz gerekir.
    </details>
- git reset --hard commit_hash
    <details>
    --hard parametresiyle çalıştırırsanız yaptığınız tüm değişiklikleri silerek belirtilen commit'e gidersiniz. zamanda yolculuk yaptırır. kullanması tehlikelidir çünkü yaptığınız önemli bir şey varsa boşa gider. kullanırken DİKKATLİ OLUNUZ. 
    </details>
- git reset fileName.txt
    <details>
    stage edilen dosyayı unstaged eder. yani "git add fileName.txt" işleminin tam tersini yapar.
    </details>
- git reset --hard HEAD
    <details>
    yaptığımız tüm değişiklikleri geri alır. örneğin iki tane dosya üzerinde değişiklik yaptık ve bu değişiklikleri geri almak istiyoruz. o zaman bu komutu kullanabiliriz.
    </details>
- git restore fileName.txt
    <details>
    tüm değişiklikleri geri almak yerine sadece bir dosyadaki değişiklikleri geri almak isteyebiliriz. bunun için "restore" sözcüğünü kullanabilir. "git restore ." kullanarak yine tüm dosyalardaki değişiklikleri geri alabiliriz.
    </details>
- git checkout commit_hash fileName.txt
    <details>
    belirttiğimiz commit'teki dosyayı alıp şimdiki haliyle değiştirebiliriz.
    </details>

### revert commit

- git revert commit_hash
    <details>
    belirtilen commit'teki değişiklikleri geri alır ve bu işlemin yağıldığına dair yeni bir commit oluşturulur.
    </details>

### stash

- git stash
    <details>
    değişiklik yapılan ancak commit edilmeyen dosyalarımız kaydedilir. başka bir branch'e geçiş yaparken kullanmamız gerekir çünkü git bu değişikliklerin ya commit edilmesini ya da stash ile daha sonra kullanılmak üzere kaydedilmesini ister. biz commit etmeyeceğiz ve başka branch'e geçip daha sonra geri geleceğiz. bu yüzden stash kullanmak durumunda kalırız.
    </details>
- git stash push -m "mesajımı buraya yazıyorum"
    <details>
    mesaj yazarak stash işlemini uygulayabiliyoruz.
    </details>
- git stash list
    <details>
    stash uygulanan çalışmalarımızı listeler.
    </details>
- git stash apply stash_index
    <details>
    stash list ile stash index'ini alıp bu komutu çalıştırırsak kaydettiğimiz çalışmalarımız yeniden aktif hale gelecek.
    </details>
- git stash show stash_index
    <details>
    stash içerisindeki dosyaların durumunu görebiliriz.
    </details>
- git stash branch new-branch stash_index
    <details>
    branch oluşturup belirttiğimiz stash'i kullanmak için kullanılır.
    </details>
- git stash pop
    <details>
    stash işlemi uygulanan çalışmalarımızı geri alır ve stash'den siler. 
    </details>
- git stash clear
    <details>
    tüm stash'leri temizler.  
    </details>
- git stash drop stash_index
    <details>
    stash uygulanan çalışmamızı siler. 
    </details>

### remote

- git remote
- git remote -v
- git pull
- git pull origin master
- git push origin master
- git push -u origin master
- git push --force origin master
- git push origin --delete feature/register-page
- git fetch
- git fetch --all
- git fetch --all origin

### differents

- git diff fileName.txt
- git diff commit_hash

### alias

- git config --global alias.last 'log -1 HEAD'
    <details>
    "git last" komutu bundan sonra "git log -1 HEAD" görevini yerine getirecek. "git last" bize son commitin ayrıntılarını verecektir. 
    </details>

### log

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
