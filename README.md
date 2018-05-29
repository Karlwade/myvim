# myvim
>自己的vim配置备份
>额外需要的操作：
>>1、需要安装gtags，ctags，toolset-clang-extras组件，配置配置文件路径。
>><pre><code>let $GTAGSCONF = '/usr/local/share/gtags/gtags.conf'</code></pre>
>>
>>2、对于使用clang 和 clang tidy使用ale进行静态检查  需要在项目根目录添加.vimrc 添加编译选项如：
>>
>><pre><code>let g:ale_c_gcc_options = '-D_GNU_SOURCE -I/home/wade/learn/nginx/src/core -I/home/wade/learn/nginx/objs -Wall -O2 -std=c99'
>>let g:ale_c_clang_options = '-I/home/wade/learn/nginx/src/core -I/home/wade/learn/nginx/objs -I/home/wade/learn/nginx/src/os/unix -std=c11 -Wall'
>></code></pre>
>>
>>3、对于使用Ycm需要添加.ycm_extra_conf.py在项目根目录，添加包含的include目录，该文件模板可在ycm的目录内搜索到，添加示例如下：
>><pre><code>
>>flags = [
>>'-Wall',
>>'-Wextra',
>>'-Werror',
>>'-fexceptions',
>>'-DNDEBUG',
>># THIS IS IMPORTANT! Without a "-std=<something>" flag, clang won't know which
>># language to use when compiling headers. So it will guess. Badly. So C++
>># headers will be compiled as C headers. You don't want that so ALWAYS specify
>># a "-std=<something>".
>># For a C project, you would set this to something like 'c99' instead of
>># 'c++11'.
>>'-std=c99',
>># ...and the same thing goes for the magic -x option which specifies the
>># language that the files to be compiled are written in. This is mostly
>># relevant for c++ headers.
>># For a C project, you would set this to 'c' instead of 'c++'.
>>'-x',
>>'c',
>>'-isystem',
>>'/usr/include',
>>'-isystem',
>>'/usr/local/include',
>>'-isystem',
>>'/home/wade/learn/nginx/objs',
>>'-isystem',
>>'/home/wade/learn/nginx/src/core',
>>'-isystem',
>>'/home/wade/learn/nginx/src/os/unix',
>>]
>></code></pre>
