# Build_Win32App_ByUsing_Swift_Learning_Cmake_Ninja

Source: https://github.com/compnerd/swift-win32

What is the difference this with the main repository?

This one is completed and done build by Running the below command, it means it is already built and ready to run:





cmake -B build -D BUILD_SHARED_LIBS=YES -D CMAKE_BUILD_TYPE=Release -D CMAKE_Swift_FLAGS="-sdk %SDKROOT%" -G Ninja -S .

ninja -C build SwiftWin32 UICatalog

%CD%\build\bin\UICatalog.exe