# 作业心得

1. 由于本作业源码基于tensorflow 1.5 api编写，而tinymind上暂时支持的tensoflow最新版本是1.4，tf1.5和1.4的部分api存在差异。根据作业文档的提示，我增加了运行时对tensoflow版本的检查，根据不同版本执行调用不同的api，这使得本地tf-1.5环境和tinymind环境都能使用同一套代码。

2. run.sh脚本里包含复制（cp）配置文件到output目录下的逻辑，实验过程中遇到报错，排查发现是如果目标文件所在目录“output”不存在，则会报错。在这个问题是花了一些时间，排查问题的方向一开始就跑偏了，以为是其他配置不对或者是代码改坏了。

3. run.sh涉及sed修改config文件的内容，但是这个命令的写法在Mac中不支持，会报错，需要稍作调整。sed -i  后面要补充一个参数，参数值是空串“”。

4. 一开始没有看run.sh，根据作业文档理解以为直接修改object_detection项目里sample/configs下相应的配置文件即可。后来才发现run.sh里写死了用data_dir下的config文件，也同时了解了tensorflow的object_detection项目下的train、eval支持指定配置文件路径，sample文件夹下附带的那些配置文件是作为参考模版，没有必要一定要把配置文件都放在那里。
