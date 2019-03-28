# macbook开发工具占用空间过大

> 核心思想将文件转移到其它空间，再链接到原有目录

1. 执行命令`cd /`
2. 执行命令`du -sh *`查找哪些目录下有大文件
3. 找到后确认能删除就删除，如果不能删除就使用命令`ln -s`将大文件迁出系统空间
4. 用iOS举例，最大的文件就是模拟器文件，目录`/Library/Developer/CoreSimulator/Profiles/Runtimes`，将此目录`mv -r`到其它空间(如：`/Volumn/dev/ios/Runtimes`)，移动时间取决于文件大小
5. 这时`/Library/Developer/CoreSimulator/Profiles`已经为空，使用命令`ls -s /Volumn/dev/ios/Runtimes ./`生成一个链接文件
6. 启动xcode模拟器，校验是否正常



> android将SDK目录和AVD迁移出即可，步骤如上类似

# macbook development tools take up too much space

> The core idea is to transfer files to other spaces and then link to the original directory

1. Execute the command `cd /`
2. Execute the command `du -sh *` to find out which directories have large files.
3. After you find it, you can delete it and delete it. If you can't delete it, use the command `ln -s` to move large files out of system space.
4. With iOS, the largest file is the emulator file, the directory `/Library/Developer/CoreSimulator/Profiles/Runtimes`, and the directory `mv -r` to other spaces (eg: `/Volumn/dev/ios/ Runtimes`), the movement time depends on the file size
5. At this point `/Library/Developer/CoreSimulator/Profiles` is empty, use the command `ls -s /Volumn/dev/ios/Runtimes ./` to generate a link file.
6. Start the xcode emulator and verify that it is normal.



> android will move the SDK directory and AVD out, the steps are similar

**translate by google**
