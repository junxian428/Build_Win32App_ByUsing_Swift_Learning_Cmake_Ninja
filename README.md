# Build_Win32App_ByUsing_Swift_Learning_Cmake_Ninja
Source from: https://github.com/compnerd/swift-win32 and my repository is already built by cmake and ninja run as well as the documentation i have walkthrough following video: https://youtu.be/Vp_wULne7b4 

Output Should be similar to this:

1- Git Clone Step 1


C:\Users\junxian428\Downloads>git clone https://github.com/compnerd/swift-win32

Cloning into 'swift-win32'...

remote: Enumerating objects: 5527, done.

remote: Counting objects: 100% (44/44), done.

remote: Compressing objects: 100% (41/41), done.

remote: Total 5527 (delta 18), reused 6 (delta 3), pack-reused 5483

Receiving objects: 100% (5527/5527), 1.32 MiB | 4.14 MiB/s, done.

Resolving deltas: 100% (3529/3529), done.
________________________________________________________________________________________________________________________________________________

2- Change and list Directory

C:\Users\junxian428\Downloads>cd swift-win32

C:\Users\junxian428\Downloads\swift-win32>ls

CMakeLists.txt     Documentation  LICENSE.txt    Packages   Sources  azure-pipelines.yml

CMakePresets.json  Examples       Package.swift  README.md  Tests    cmake

C:\Users\junxian428\Downloads\swift-win32>ls

CMakeLists.txt     Documentation  LICENSE.txt    Packages   Sources  azure-pipelines.yml

CMakePresets.json  Examples       Package.swift  README.md  Tests    cmake

________________________________________________________________________________________________________________________________________________

3 - Run the Command Following the 

cmake -B build -D BUILD_SHARED_LIBS=YES -D CMAKE_BUILD_TYPE=Release -D CMAKE_Swift_FLAGS="-sdk %SDKROOT%" -G Ninja -S .

__________________________________________________________________________________________________________________________________________________

C:\Users\junxian428\Downloads\swift-win32>cmake -B build -D BUILD_SHARED_LIBS=YES -D CMAKE_BUILD_TYPE=Release -D CMAKE_Swift_FLAGS="-sdk %SDKROOT%" -G Ninja -S .

-- The C compiler identification is MSVC 19.29.30140.0

-- The Swift compiler identification is Apple 5.7

-- Detecting C compiler ABI info

-- Detecting C compiler ABI info - done

-- Check for working C compiler: C:/Program Files (x86)/Microsoft Visual Studio/2019/BuildTools/VC/Tools/MSVC/14.29.30133/bin/Hostx64/x64/cl.exe - skipped

-- Detecting C compile features

-- Detecting C compile features - done

-- Check for working Swift compiler: C:/Library/Developer/Toolchains/unknown-Asserts-development.xctoolchain/usr/bin/swiftc.exe

-- Check for working Swift compiler: C:/Library/Developer/Toolchains/unknown-Asserts-development.xctoolchain/usr/bin/swiftc.exe - works

-- Found Git: C:/Program Files/Git/cmd/git.exe (found version "2.35.0.windows.1")

Submodule 'Packages/SwiftCOM' (https://github.com/compnerd/swift-com) registered for path 'Packages/SwiftCOM'

Submodule 'Packages/cassowary' (https://github.com/compnerd/cassowary) registered for path 'Packages/cassowary'

Submodule 'Packages/swift-collections' (https://github.com/apple/swift-collections) registered for path 'Packages/swift-collections'

Submodule 'Packages/swift-log' (https://github.com/apple/swift-log) registered for path 'Packages/swift-log'

Cloning into 'C:/Users/junxian428/Downloads/swift-win32/Packages/SwiftCOM'...

Cloning into 'C:/Users/junxian428/Downloads/swift-win32/Packages/cassowary'...

Cloning into 'C:/Users/junxian428/Downloads/swift-win32/Packages/swift-collections'...

Cloning into 'C:/Users/junxian428/Downloads/swift-win32/Packages/swift-log'...

Submodule path 'Packages/SwiftCOM': checked out 'ebbc617d3b7ba3a2023988a74bebd118deea4cc5'

Submodule path 'Packages/cassowary': checked out 'a438611231901f9f350da27857d786f7979d578b'

Submodule path 'Packages/swift-collections': checked out 'c0549b6284aadd5fd13156316f43fcb43c7fca77'

Submodule path 'Packages/swift-log': checked out 'd8af258aecd93cd8604e74ade3c0fe438bac13f8'

-- Building with sub-modules:

--   Cassowary rGa438611

--   Swift/COM rGebbc617

--   swift-log rGd8af258

--   Collections rGc0549b6

-- Configuring done

-- Generating done

-- Build files have been written to: C:/Users/junxian428/Downloads/swift-win32/build

__________________________________________________________________________________________________________________________________________________

Step 4- ninja -C build SwiftWin32 UICatalog

_________________________________________________________________________________________________________________________________________________
C:\Users\junxian428\Downloads\swift-win32>ls

CMakeLists.txt     Documentation  LICENSE.txt    Packages   Sources  azure-pipelines.yml  cmake

CMakePresets.json  Examples       Package.swift  README.md  Tests    build


C:\Users\junxian428\Downloads\swift-win32>ninja -C build SwiftWin32 UICatalog

ninja: Entering directory `build'

[2/6] Linking Swift shared library bin\OrderedCollections.dll

   Creating library lib\OrderedCollections.lib and object lib\OrderedCollections.exp
   
[3/6] Linking Swift shared library bin\Logging.dll

   Creating library lib\Logging.lib and object lib\Logging.exp
   
[4/6] Linking Swift shared library bin\SwiftCOM.dll

   Creating library lib\SwiftCOM.lib and object lib\SwiftCOM.exp
   
[5/6] Linking Swift shared library bin\SwiftWin32.dll

C:\Users\junxian428\Downloads\swift-win32\Sources\SwiftWin32\Platform\Error.swift:50:31: warning: '_wcserror' is deprecated: This function or variable may be unsafe. Consider using _wcserror_s instead. To disable deprecation, use _CRT_SECURE_NO_WARNINGS. See online help for details.
  
  guard let description = _wcserror(errno) else {
                              ^
   Creating library lib\SwiftWin32.lib and object lib\SwiftWin32.exp
   
[6/6] Linking Swift executable bin\UICatalog.exe

   Creating library bin\UICatalog.lib and object bin\UICatalog.exp

C:\Users\junxian428\Downloads\swift-win32>ls

CMakeLists.txt     Documentation  LICENSE.txt    Packages   Sources  azure-pipelines.yml  cmake

CMakePresets.json  Examples       Package.swift  README.md  Tests    build

C:\Users\junxian428\Downloads\swift-win32>cd build

C:\Users\junxian428\Downloads\swift-win32\build>ls

CMakeCache.txt  Examples  Sources                 bin          cmake_install.cmake  swift

CMakeFiles      Packages  SwiftWin32Config.cmake  build.ninja  lib

C:\Users\junxian428\Downloads\swift-win32\build>cd bin

C:\Users\junxian428\Downloads\swift-win32\build\bin>ls

CoffeeCup.jpg  Logging.emit-module.d             SwiftCOM.dll            UICatalog.exe

Info.plist     OrderedCollections.dll            SwiftCOM.emit-module.d  UICatalog.exp

Logging.dll    OrderedCollections.emit-module.d  SwiftWin32.dll          UICatalog.lib


C:\Users\junxian428\Downloads\swift-win32\build\bin>UICatalog.exe

Good night!

Good morning!

Good morning!

Good night!

2022-09-15T14:19:24+0800 warning org.compnerd.swift-win32 : [SwiftWin32] SetParent: Win32 Error 1400 - Invalid window handle.

2022-09-15T14:19:24+0800 warning org.compnerd.swift-win32 : [SwiftWin32] SetParent: Win32 Error 1400 - Invalid window handle.

Goodbye cruel world!

C:\Users\junxian428\Downloads\swift-win32\build\bin>ls

CoffeeCup.jpg  Logging.dll            OrderedCollections.dll            SwiftCOM.dll            SwiftWin32.dll  UICatalog.exp

Info.plist     Logging.emit-module.d  OrderedCollections.emit-module.d  SwiftCOM.emit-module.d  UICatalog.exe   UICatalog.lib



Screenshot:

![image](https://user-images.githubusercontent.com/58724748/190333217-03f76e9f-985a-4c8c-86ff-56bb9c8680df.png)

![image](https://user-images.githubusercontent.com/58724748/190333326-8f418b4f-9b07-4a8b-875a-11094695f798.png)







