### Clone 
git clone --recursive https://github.com/ClickHouse/ClickHouse.git

### Fix deps
#### install objcopy
brew install binutils
#### find objcopy
mdfind -name objcopy
#### specify the path for objcopy
find_program (OBJCOPY_PATH NAMES "llvm-objcopy" "llvm-objcopy-10" "llvm-objcopy-9" "llvm-objcopy-8" "objcopy" PATHS "/usr/local/Cellar/binutils/2.35.1/bin/")


### Build
mkdir Clickhouse/build
cd Clickhouse/build
cmake .. -DCMAKE_CXX_COMPILER=`which clang++` -DCMAKE_C_COMPILER=`which clang` -DCMAKE_BUILD_TYPE=Debug
ninja clickhouse-bundle
cd ..

### Import
