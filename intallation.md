#Ruby on Rails Linux 安裝教學

##安裝前的小提醒

若你使用 Windows 電腦，我強烈建議安裝 Linux 雙系統或是用 VM 建立一個虛擬的 Linux 環境來開發 Ruby on Rails，可用 VirtualBox 加上 Ubuntu Linux，請參考以下教學: 
```
http://blog.xuite.net/yh96301/blog/55671076-VirtualBox+5.0%E5%AE%89%E8%A3%9DUbuntu+15.04
```

由於 Ruby 語言和 Rail 架構的核心開發群都是使用 Mac 和 Linux 開發，相較之下 Ruby on Rails 對 Windows 的優化和支援會比 Linux 差很多，若是直接在 Windows 上安裝 Ruby on Rail，通常會遇到的狀況不是無法安裝，就是一些相關的 dependencies 或是 gem 與 windows 不相容，會讓你遇上一些無法解決的問題，引響你的開發和學習進度。


## 開始安裝開發環境

Ubuntu 安裝成功後，開啟 VM，接下來就開始安裝 Rails 的開發環境：

1. 先安裝一些 Ruby 的 dependencies：

	請打開你的 Terminal，輸入以下指令：

	```
	sudo apt-get update
	sudo apt-get install git-core curl zlib1g-dev build-essential libssl-dev libreadline-dev libyaml-dev libsqlite3-dev sqlite3 libxml2-dev libxslt1-dev libcurl4-openssl-dev python-software-properties libffi-dev
	```

2. 設定你的 git

	打開 git 的彩色輸出
	```
	git config --global color.ui true
	```

	設定 git 的 user 和 email
	```
	git config --global user.name "YOUR NAME"
	git config --global user.email "YOUR@EMAIL.com"
	```

	讓 git 記住你，不需每次上傳 code 都要重打
	```
	git config --global credential.helper store
	```

3. 接下來，安裝 rbenv，Ruby 語言的版本管理工具：

	```
	cd ~
	git clone git://github.com/sstephenson/rbenv.git .rbenv
	echo 'export PATH="$HOME/.rbenv/bin:$PATH"' >> ~/.bashrc
	echo 'eval "$(rbenv init -)"' >> ~/.bashrc
	exec $SHELL
	
	git clone git://github.com/sstephenson/ruby-build.git ~/.rbenv/plugins/ruby-build
	echo 'export PATH="$HOME/.rbenv/plugins/ruby-build/bin:$PATH"' >> ~/.bashrc
	exec $SHELL
	
	git clone https://github.com/sstephenson/rbenv-gem-rehash.git ~/.rbenv/plugins/rbenv-gem-rehash
	```

4. 安裝 Sublime, 本課程使用的文字編輯器

	```
	sudo add-apt-repository ppa:webupd8team/sublime-text-3
	sudo apt-get update
	sudo apt-get install sublime-text-installer
	```

	在裝完後, 打開Sublime
	```
	cd /opt/sublime_text
	./sublime_text
	```

	點一下右下角的選單，選擇 Indent using space, 並選 tab width: 2

5. 安裝完 rbenv 之後，安裝 Ruby 2.2.3，並設為預設的 Ruby 版本

	```
	rbenv install 2.2.3
	rbenv global 2.2.3
	ruby -v
	```

6. 告訴 Rubygems 不要安裝 rdoc，初學者用不到，同時也拖長安裝時間

	```
	echo "gem: --no-ri --no-rdoc" > ~/.gemrc
	```

7. 安裝 bundler (管理應用程式 Gem 依存性(dependencies)管理工具，它會根據 Gemfile 的設定自動下載及安裝 Gem 套件)

	```
	gem install bundler
	```

	安裝 Node.js，一個 Javascript 的 runtime

	```
	sudo add-apt-repository ppa:chris-lea/node.js
	sudo apt-get update
	sudo apt-get install nodejs
	```

8. 接下來，安裝 Rails gem

	```
	gem install rails -v 4.2.4
	```

9. 跑完之後，輸入以下指令確保 Rails 可被 rbenv 讀取到

	```
	rbenv rehash
	```

10. 最後，確認一下剛才安裝的 Rails 版本是否正確：

	```
	rails -v
	```

11. 應該會顯示：

	```
	# Rails 4.2.4
	```

	恭喜！你已經安裝完開發環境了！！！

## 建立你的第一個 Rails app

	```
	rails new my_app_name
	```

1. 進入 Rails 專案的根目錄

	```
	cd my_app_name
	```

2. 接下來啟動 rails server：

	```
	rails server
	```

3. 打開你的瀏覽器，輸入網址： 

	```
	localhost:3000
	```

## 恭喜你完成第一個 Rails app！！！










