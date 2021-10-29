# Shell_02

### bash vs zsh

1. CD + Tab
    > bash
    ```r
    mhj@mhj-IdeaPad:~$ cd 
    .cache/    .local/    .steam/    .zoom/     문서/
    .config/   .mozilla/  .swt/      Documents/ 바탕화면/
    .dbus/     .p2/       .tooling/  KakaoTalk/ 비디오/
    .eclipse/  .pki/      .vscode/   gitRepo/   사진/
    .gnupg/    .presage/  .wakatime/ 공개/      음악/
    .kde/      .ssh/      .wine/     다운로드/  템플릿/
    ```
    If you want to find where to __Change Directory__(cd) in __bash__, type __cd__ and hit 'Tab' __twice__. Then the ones above will be printed out. Also, the hidden files can be seen. 

    > zsh
    ```r
    mhj-IdeaPad% cd
    Documents/  공개/       바탕화면/   사진/       
    KakaoTalk/  비디오/     문서/       템플릿/     
    gitRepo/    다운로드/   음악/ 
    ```
    If you want to find where to __Change Directory__(cd) in __zsh__, type __cd__ and hit 'Tab' __once__. Then the ones above will be printed out. But, it don't show the hidden files.

2. PWD + CD + Tab

    > bash
    ```r
    mhj@mhj-IdeaPad:~$ pwd
    /home/mhj
    mhj@mhj-IdeaPad:~$ cd /home/mhj
    mhj@mhj-IdeaPad:~$ cd /home/mhj/gitRepo/
    ```
    To change directory in __bash__, to use the automatic completion function, it works like this:
    ```r
    cd /h + Tab -> cd /home/
    cd /home/m + Tab -> cd /home/mhj/ 
    cd /home/mhj/g + Tab -> cd /home/mhj/gitRepo/
    ```
    So type the initial word of directory and hit 'Tab' one by one. Bash will automatically complete writing directory name. 

    > zsh 
    ```r
    mhj-IdeaPad% pwd     
    /home/mhj
    mhj-IdeaPad% cd /home/mhj/gitRepo/
    ```
    To change directory in __zsh__, to use the automatic completion function, it works like this:
    ```r
    cd /h/m/g + Tab -> cd /home/mhj/gitRepo/
    ```
    Type all the initial word of directory where you want to change, and hit 'Tab' just once. It will automatically complete writing it. So __zsh__ is more convenient than __bash__.

3. CD - Change Directory at once

    > zsh
    ```r
    mhj-IdeaPad% cd /home/mhj/gitRepo 
    mhj-IdeaPad% cd gitRepo KakaoTalk 
    ~/KakaoTalk
    mhj-IdeaPad% pwd
    /home/mhj/KakaoTalk
    ```
    __zsh__ can do like this, but __bash__ can't. 

    > bash
    ```r
    mhj@mhj-IdeaPad:~/gitRepo$ cd
    mhj@mhj-IdeaPad:~$ cd /home/mhj/gitRepo/
    mhj@mhj-IdeaPad:~/gitRepo$ pwd
    /home/mhj/gitRepo
    mhj@mhj-IdeaPad:~/gitRepo$ cd gitRepo KakaoTalk
    bash: cd: 인자가 너무 많음
    mhj@mhj-IdeaPad:~/gitRepo$ pwd
    /home/mhj/gitRepo
    ```
    Error occurs. 

### Conclusion

There a lot of Shells, so that we can choose the Shell we want to control Kernel. It is why Shell and Kernel is divided. 

![Shell&Kernel](https://github.com/MinhoJJang/Linux_study/blob/main/14-17_Shell/Shell%26Kernel2.jpeg)


![Shell&Kernel](https://github.com/MinhoJJang/Linux_study/blob/main/14-17_Shell/Shell%26Kernel3.jpeg)