# screw_decode
decode screw encode php file
### first
前提需要有加密之后的文件，和加密的扩展库php_screw.so
打开screwdecode.c找到PM9SCREW,PM9SCREW_LEN和pm9screw_mycryptkey，3个可能被使用者修改，需要用IDA去需找然后替换掉。
pm9screw_mycryptkey是至关重要的，拿不到就解密不了。别的两个可以暴力尝试解决,其实就是读取掉头部n个字节尝试解密。

打开screwdecode.c
### install

    git clone https://github.com/firebroo/screw_decode.git
    make

如果以上出错，就看报错然后google,一个是依赖php-devel，一个是依赖zlibc-devel

### Usage

    sudo ./decode path
 
结果保存在同目录，文件名字为原文件名字后面追加.decode, sudo 权限保证可以有chdir和创建文件权限。
