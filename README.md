# autoimdear
automatic imdear project



sudo apt install libx11-xcb-dev libxcb-glx0-dev libxcb-dri2-0-dev \
		libxcb-dri3-dev libxcb-present-dev libxcb-sync-dev
		
sudo rm -Rf dear-imgui-conan-example
git clone https://github.com/bilke/dear-imgui-conan-example.git
cd dear-imgui-conan-example
mkdir build
cd build

sudo apt install python3-pip
pip install launchpadlib
pip install testresources
pip install conan

conan install .. -s build_type=Release
conan install .. -s build_type=Debug
conan install .. -s build_type=Release --build glew --build glfw --build imgui
conan install .. -s build_type=Debug --build glew --build glfw --build imgui
cmake .. -DCMAKE_BUILD_TYPE=Release
cmake --build .
./dear-imgui-conan

