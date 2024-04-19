# How to use vcpkg

first clone the vcpkg repo (there is already a .gitignore file ignoring the vcpkg folder)

then do

`cmake -S . -B build/windows -G "Visual Studio 17" -DCMAKE_BUILD_TYPE=Release -DCMAKE_TOOLCHAIN_FILE="$PWD/vcpkg/scripts/buildsystems/vcpkg.cmake"`

obviously you would use a different generator (or none at all) and make the cmaketoolchain file point to your vcpkg toolchain file

this will compile all dependencies. Now you have a cmake project with all dependencies built from source and linked succesfully.