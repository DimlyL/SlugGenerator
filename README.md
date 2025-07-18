# SlugGenerator
一个服务于 VNS 的插件，用于快速生成 markdown 文件对应的 slug。

使用说明：编译后，在命令行中输入 SlugGenerator.exe <文件路径>.md，即可为相应的 markdown 文件生成 slug。

## 要求：

原本的 .md 文件中需要包含以 `title:` 和 `date:` 开头的两行文字。  
程序会读取 title 和 date 并且根据它们生成对应的 slug。

## 注意：

- 程序执行成功后，生成一个新的 _new 文件，而非直接覆盖原文件。
- 生成 slug 后，程序会在原 .md 文件的同一目录下搜索其他 .md 文件，查询是否有相同的 slug，如有相同则会进行调整。

## 问题：

- 算法基于 CRC16，然而这部分好像有点问题……？至少它能生成一个 unsigned short 范围内的数就是了。
- 原本它是会输出读取到的 title 和 date 的，但是似乎是因为编码不同，输出的 title 会变成乱码……？暂时把这两行注释掉了。
