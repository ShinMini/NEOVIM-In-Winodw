# NEO VIM WINDOW POWERSHELL ENV SET UP (네오빔 윈도우 파워쉘 환경 세팅)

* 참고로 난 멍청해서 세팅하는데 다합쳐 30시간 정도 걸린 것같음
* 내부 파일 뜯고 디렉터리 맘대로 설정하다 꼬여서 ㅎㅎ

---

<br/>

# Set in Env :
---------------
- OS: Windows 11    
- Windows Command Prompt, nvim-qt, neovim-nightly(0.8.0-dev), neovim(0.6.0)
- powershell package manager : scoop

# Pre-requisite:
-----------------
- Install Windows Powershell [MS store PS](https://apps.microsoft.com/store/detail/powershell/9MZ1SNWT0N5D?hl=ko-kr&gl=kr) (powershell 다운)
- Insatll Scoop [Scoop site link](https://scoop.sh/) (스쿱 사이트 링크)
    - way to install PowerShell command (파워쉘 커멘드로 설치하는 방법)
        - Run Powershell with administor mode (파워쉘을 관리자 모드로 실행)
        - Install scoop command (powershell package manager) 
        ```PowerShell
        Set-ExecutionPolicy RemoteSigned -scope CurrentUser
        iex (new-object net.webclient).downloadstring('https://get.scoop.sh')
        ```
    - Insatll Ctags (install via scoop: `scoop install ctags`)  (neo vim libary임 , 없어도지장 x)
    - Insatll Python 2.7, Python 3.6 (with pip, virtualenv)

Optional Dependencies:
-----------------------
- Node 8.9.x, npm 5.5.x
- [Visual C++ Redistributable for Visual Studio 2015](https://www.microsoft.com/en-my/download/details.aspx?id=48145)
- [Powerline fonts](https://medium.com/@slmeng/how-to-install-powerline-fonts-in-windows-b2eedecace58)

Configurations Info:
---------------------
- Configuration files location: `%userprofile%\AppData\Local\nvim\`
    - `init.vim` : main configuration files just like `.vimrc`
    - `ginit.vim` : configuration file just for GUI version of neovim
- Built-in color scheme directory: `%userprofile%\scoop\apps\neovim\0.3.0\Neovim\share\nvim\runtime\colors`

Installation:
--------------
1. Install [neovim](https://github.com/neovim/neovim/wiki/Installing-Neovim)
    `scoop install neovim`
2. Delete default configuration files (CAUTION: backup your files if this is not a fresh installation): 
    ```console
    cd %userprofile%\AppData\Local\nvim
    del /s /q *
    for /f "delims=" %x in ('dir /b /ad .') do rd /s /q "%x"
    ````
3. Clone this repository: 
    ```console
    cd %userprofile%\AppData\Local\nvim 
    git clone https://github.com/thiamteck/nvim-windows-sample-config.git .
    ```
4. Run installation script:
    ```console
    cd %userprofile%\AppData\Local\nvim
    scripts\express_setup.bat
    ```
5. (Optional) Install neovim provider for Node.js: `npm install -g neovim`
6. Install plugin with command: `nvim +PlugInstall`


---

<br>


## Frequent errors (자주 발생하는 에러)

----------------------

### Log files viewing:
    - Highlight lines with previous matched pattern via Highlight.vim: `<C-h><C-j>`
    
### Tuned for general writing:
    - distraction free writing via [Goyo](https://github.com/junegunn/goyo.vim) & [Limelight](https://github.com/junegunn/limelight.vim)
    - grammar check with [vim-wordy](https://github.com/reedes/vim-wordy)
    - include [Markdown with Vim](https://github.com/gabrielelana/vim-markdown)
    - soft line wrap for text file and markdown file
### Enhanced UI with [NERDTree](https://github.com/scrooloose/nerdtree), [vim-airline](https://github.com/vim-airline/vim-airline)    
### Many [awesome colorscheme](https://github.com/rafi/awesome-vim-colorschemes) to choose from, and able to use different colorscheme for GUI and console mode. 
### Python auto completion with [Deoplete](https://github.com/Shougo/deoplete.nvim), and [deoplete-jedi](https://github.com/zchee/deoplete-jedi)

## nvim profile은 어디에 있나요?

- nvim init.vim, .vimrc 파일의 경우, 
- init.vim dir => C:\Users\본인\AppData\Local\nvim 에 위치
- .vimrc dir => default 생성 X, 본인이 생성해 줘야함. 
    - 보통 ~/.vimrc 로 생성 혹은, ~/vim/.vimrc 로 위치를 잡아줌. 

## 추천하는 nvim color set
[oneharlf color](https://github.com/sonph/onehalf/tree/master/vim)
절반은 검정, 절반은 하양 .. 예쁘다..
* 물론 필자는 번갈아가며 다양하게 쓰는중 
![image](https://user-images.githubusercontent.com/77220824/189599838-ad0eb148-8e03-4e75-8124-a2f529d1a5e2.png)

<br>
<br>

