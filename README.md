# clang-repo-manifest

An Android Repo manifest for the git repositories required to build Clang from source. 

## Setup
Instructions for installing repo: https://source.android.com/setup/downloading#installing-repo

## Initialising
Inside an empty directory: 
`repo init -u https://github.com/advisoft/clang-manifest`, then to download the code: `repo sync`

## Updating all of the Git repositories to the latest master
`repo sync`

## Building
`mkdir bld`

`cd bld`

`cmake -G "Ninja" ../llvm -DCMAKE_BUILD_TYPE:STRING=Release -DCMAKE_INSTALL_PREFIX:PATH=~/clang-master -DCOMPILER_RT_INCLUDE_TESTS:BOOL=OFF -DLLVM_ENABLE_ASSERTIONS:BOOL=OFF`

`ninja`

## Installing
`ninja install`

Now the usable binaries will be located in: `~/clang-master/bin`

## More info on using Repo
https://source.android.com/setup/using-repo
