#Ruby on Rails 安裝教學


##安裝前的小提醒

若你使用 Windows 電腦，我強烈建議安裝 Linux 雙系統或是用 VM 建立一個虛擬的 Linux 環境來開發 Ruby on Rails(可用 VirtualBox 加上 Ubuntu Linux)。
由於 Ruby 語言和 Rail 架構的核心開發群都是使用 Mac 和 Linux 開發，相較之下 Ruby on Rails 對 Windows 的優化和支援會比 Linux 差很多，若是直接在 Windows 上安裝 Ruby on Rail，通常會遇到的狀況不是無法安裝，就是一些相關的 dependencies 或是 gem 與 windows 不相容，會讓你遇上一些無法解決的問題，引響你的開發和學習進度。

##Linux 安裝教學，請依照以下的安裝法：

1. 先安裝一些 Ruby 的 dependencies：

```
sudo apt-get update
sudo apt-get install git-core curl zlib1g-dev build-essential libssl-dev libreadline-dev libyaml-dev libsqlite3-dev sqlite3 libxml2-dev libxslt1-dev libcurl4-openssl-dev python-software-properties libffi-dev
```

2. 設定你的 git



2. 接下來，安裝 rbenv，Ruby 語言的版本管理工具：

```
cd
git clone git://github.com/sstephenson/rbenv.git .rbenv
echo 'export PATH="$HOME/.rbenv/bin:$PATH"' >> ~/.bashrc
echo 'eval "$(rbenv init -)"' >> ~/.bashrc
exec $SHELL

git clone git://github.com/sstephenson/ruby-build.git ~/.rbenv/plugins/ruby-build
echo 'export PATH="$HOME/.rbenv/plugins/ruby-build/bin:$PATH"' >> ~/.bashrc
exec $SHELL

git clone https://github.com/sstephenson/rbenv-gem-rehash.git ~/.rbenv/plugins/rbenv-gem-rehash
```

3. 安裝完 rbenv 之後，安裝 Ruby 2.2.3，並設為預設的 Ruby 版本

```
rbenv install 2.2.3
rbenv global 2.2.3
ruby -v
```

4. 告訴 Rubygems 不要安裝 rdoc

```
echo "gem: --no-ri --no-rdoc" > ~/.gemrc
```

5. 安裝 bundler (管理應用程式 Gem 依存性(dependencies)管理工具，它會根據 Gemfile 的設定自動下載及安裝 Gem 套件)

```
gem install bundler
```

6. 接下來，安裝 Rails gem

```
gem install rails -v 4.2.4
```

7. 跑完之後，輸入以下指令確保 Rails 可被 rbenv 讀取到

```
rbenv rehash
```

8. 最後，確認一下剛才安裝的 Rails 版本是否正確：

```
rails -v
```

9. 應該會顯示：

```
# Rails 4.2.4
```

恭喜！你已經安裝完開發環境了！！！

10. 建立你的第一個 Rails app

```
rails new my_app_name

# Move into the application directory
cd my_app_name
```

11. 接下來啟動 rails server：

```
rails server
```

12. 打開你的瀏覽器，輸入網址： 

```
localhost:3000
```

##恭喜你完成第一個 Rails app！！！


##Mac 安裝教學，請依照以下的安裝法：









