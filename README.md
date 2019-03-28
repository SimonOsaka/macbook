# macbook开发工具占用空间过大

> 核心思想将文件转移到其它空间，再链接到原有目录

1. 执行命令`cd /`
2. 执行命令`du -sh *`查找哪些目录下有大文件
3. 找到后确认能删除就删除，如果不能删除就使用命令`ln -s`将大文件迁出系统空间
4. 用iOS举例，最大的文件就是模拟器文件，目录`/Library/Developer/CoreSimulator/Profiles/Runtimes`，将此目录`mv -r`到其它空间(如：`/Volumn/dev/ios/Runtimes`)，移动时间取决于文件大小
5. 这时`/Library/Developer/CoreSimulator/Profiles`已经为空，使用命令`ls -s /Volumn/dev/ios/Runtimes ./`生成一个链接文件
6. 启动xcode模拟器，校验是否正常



> android将SDK目录和AVD迁移出即可，步骤如上类似

==看不懂不是一个合格的程序员==
