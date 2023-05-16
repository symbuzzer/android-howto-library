sudo apt install unzip  
sudo -v ; curl https://rclone.org/install.sh | sudo bash  
  
wget https://dl.google.com/android/repository/platform-tools-latest-linux.zip  
unzip platform-tools-latest-linux.zip -d ~  
  
nano ~/.profile  
  
if [ -d "$HOME/platform-tools" ] ; then  
    PATH="$HOME/platform-tools:$PATH"  
fi  
  
source ~/.profile  
  
cd ~/  
git clone https://github.com/akhilnarang/scripts  
cd scripts  
./setup/android_build_env.sh  
  
cd ~/  
mkdir -p ~/bin  
mkdir -p ~/android/pe  
  
curl https://storage.googleapis.com/git-repo-downloads/repo > ~/bin/repo  
chmod a+x ~/bin/repo  
  
git config --global user.email "alipolatbeyaz@gmail.com"  
git config --global user.name "Ali BEYAZ"  
  
cd ~/android/pe  
repo init -u https://github.com/PixelExperience/manifest -b thirteen-plus  
repo sync -c -j$(nproc --all) --force-sync --no-clone-bundle --no-tags  
  
cd ~/android/pe  
source build/envsetup.sh  
lunch aosp_apollo-userdebug  
  
croot  
mka bacon -j$(nproc --all)  
  
rclone config  
  
cd android/pe/out/target/product/apollo  
sudo mkdir 1  
sudo cp PixelExperience_Plus_apollo-13.0-20230513-0940-UNOFFICIAL.zip 1/  
rclone copy 1 gdriveubuntu:ubuntu  
