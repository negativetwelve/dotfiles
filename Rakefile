require "rake"
require "fileutils"

is_osx? = RUBY_PLATFORM.downcase.include?("darwin")

desc "Installs dotfiles with default installation"
task :install do
  puts
  puts "======================================================"
  puts "Welcome to Dotfiles"
  puts "======================================================"
  puts

  install_homebrew if is_osx?

end

def install_homebrew
  run %{which brew}
  unless $?.success?
    puts "======================================================"
    puts "Installing Homebrew, the OSX package manager...If it's"
    puts "already installed, this will do nothing."
    puts "======================================================"
    run %{ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"}
  end

  puts
  puts "======================================================"
  puts "Updating Homebrew."
  puts "======================================================"
  run %{brew update}
  puts
  puts "======================================================"
  puts "Installing Homebrew packages...There may be some warnings."
  puts "======================================================"
  run %{brew install zsh ctags git hub tmux reattach-to-user-namespace the_silver_searcher}
  puts
end
