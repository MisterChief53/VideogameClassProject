cmake_minimum_required(VERSION 3.20)
project(LearnOpenGL)

## Find dependencies
find_package(glfw3 REQUIRED)
find_package(glad REQUIRED)
find_package(glm REQUIRED)
find_package(freetype REQUIRED)
find_package(imgui REQUIRED)
find_package(assimp REQUIRED)
#find_package(reactphysics3d REQUIRED)



# Set source and destination directories for resources
set(RESOURCE_DIR "resources")  # Adjust path to your resources folder

# stb does not have a CMake build, but is header-only
#find_path(STB_INCLUDE_DIRS "stb.h") 
set(STB_INCLUDE_DIRS "${vcpkg_installed_dirs}/x64-windows/include")



## Create main executable
add_executable(
	main 
	source/main.cpp
	source/stbImg.cpp
	source/Camera.h
	source/Cubo.h
	source/CuboL.h
	source/Mesh.h
	source/Model.h
	source/Shader.h
	source/Texture.h
)
target_include_directories(main 
  PRIVATE 
	${STB_INCLUDE_DIRS}
	"${CMAKE_CURRENT_LIST_DIR}/source"
)
target_link_libraries(
  main
  PRIVATE
    freetype
    glfw
    glad::glad
    glm::glm
    imgui::imgui
    assimp::assimp
    #reactphysics3d
)