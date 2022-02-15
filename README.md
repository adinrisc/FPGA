# FPGA

#### 介绍
双目摄像头采集数据 ETH发包 DDR3缓存HMDI输出

#### 软件架构
使用芯路恒ACX720开发板，PPLip核产生系统所需主要时钟，IIC控制ov5640摄像头初始化，双目摄像头采集数据通过DVP接口输出，输出数据通过image_stitch_x模块合并输出，通过eth_udp_tx_gmii以及eth_tx_ctrl传输到上位机进行处理，同时通过ddr3_ctrl_2port将数据暂存于板载DDR3中，图像流输出后转化为RGB565形式通过disp_play模块进行输出，借用div_encoder将RGB信号转为TMDS信号进行HMDI输出。


#### 安装教程

1.  vivado 2018.3
2.  小梅哥UDP摄像头V3.2

#### 使用说明
1.  网口mac地址以及端口需要与电脑一致
2.  电脑需要千兆网口
3.  上位机软件像素设置与工程一致
