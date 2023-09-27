# 💻 Terminal

<figure><img src="../.gitbook/assets/image.png" alt=""><figcaption></figcaption></figure>

as we like to make everything more easy for our community, in this article we will explain how you can get your terminal to be like this one.

### Install OhMyZsh

we start by installing zsh and ohMyZsh packages to add their features to our terminal&#x20;

<pre class="language-bash"><code class="lang-bash">sudo apt-get -y install git curl wget
<strong>sudo apt-get -y install zsh
</strong>sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
</code></pre>

now zsh and OhMyZsh are installed successfully, we will add some plugins to make it easier to use the terminal.

### Install OhMyZsh Plugins

we will add 2 plugins `syntax-highlighting` and `zsh-autosuggestions` these 2 plugins make the code and command on the terminal highlighted and the code you right will be saved to your terminal it will auto-complete it for you

```bash
git clone https://github.com/zsh-users/zsh-syntax-highlighting.git ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-syntax-highlighting
echo "source ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-syntax-highlightingzsh-syntax-highlighting.zsh" >> ${ZDOTDIR:-$HOME}/.zshrc
git clone https://github.com/zsh-users/zsh-autosuggestions ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-autosuggestions
```

now you need to allow this plugin on OhMyZsh config

```bash
sudo nano ~/.zshrc
```

search about plugins and add this

```bash
plugins=( 
    git
    zsh-syntax-highlighting
    zsh-autosuggestions
)
```

### Install Power Fonts

to make OhMyZsh work with icons you need to install this font&#x20;

```bash
sudo apt-get install fonts-powerline
```

and you can download it from [here](https://github.com/romkatv/powerlevel10k#manual-font-installation)

### Install PowerLevel10k Theme

now it's time to make your terminal look pro just install powerlevel10k theme

```bash
git clone --depth=1 https://github.com/romkatv/powerlevel10k.git ${ZSH_CUSTOM:-$HOME/.oh-my-zsh/custom}/themes/powerlevel10k
```

now change the main theme on the OhMyZsh config

```bash
sudo nano ~/.zshrc
```

Now, searching for the theme can change it

```bash
ZSH_THEME="powerlevel10k/powerlevel10k"
```

now close your terminal and open it again to restart zsh and after that start your config

```bash
p10k configure
```

after config your theme you will see the new theme.
