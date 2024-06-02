## Preparation

brew install chruby ruby-install xz

echo "source $(brew --prefix)/opt/chruby/share/chruby/chruby.sh" >> ~/.zshrc
echo "source $(brew --prefix)/opt/chruby/share/chruby/auto.sh" >> ~/.zshrc
echo "chruby ruby-3.1.3" >> ~/.zshrc # run 'chruby' to see actual version

ruby-install ruby 3.1.3

bundle lock --add-platform x86_64-linux - to lock platform

## Run

bundle
jekyll build
jekyll serve
