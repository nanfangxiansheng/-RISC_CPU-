# 总览

基于北航的夏宇闻教授的verilog数字系统设计第十七章的简化的RISC_CPU代码复现。

测试文件中包含三项测试分别为test1,test2,test3.

建议在vscode这款广泛使用的编辑器中执行命令，可以在terminal终端中输入下面的指令，为了方便高亮代码，可以安装下面的插件：

![-RISC_CPU-/verilog.png at main · nanfangxiansheng/-RISC_CPU-](https://github.com/nanfangxiansheng/-RISC_CPU-/blob/main/verilog.png)

iverilog编译命令为（iverilog是一个开源的verilog编译器。采用WSL2虚拟机安装iverilog或者直接win安装iverilog和gtkwave，教程参考网上，比较众多）：

```shell
iverilog -o cpu.out .\accumulator.v .\addr_decode.v .\address_multiplexer.v .\alu.v .\clock_manager.v .\command_register.v .\condition_control.v .\data_controller.v .\risc_cpu_tb.v .\risc_cpu.v .\program_counter.v .\ram_test.v .\rom_test.v
```

执行编译后文件的命令为：

```shell
vvp cpu.out
```

值得注意的是，若要观察波形，测试文件中是无法生成的，解决办法是自行建立一个vivado项目并把像.dat后缀(测试基准数据集)这样的文件放置在srcs\sim\new这样的目录下面。

