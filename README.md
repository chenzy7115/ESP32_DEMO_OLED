# 项目说明

***这是SSD1306 OLD使用LVGL的移植***

***1.***使用的文件是https://github.com/lvgl/lv_port_esp32

git clone --recurse-submodules https://github.com/lvgl/lv_port_esp32.git

***2.***下载全部文件后，将components下的lvgl和lvgl_esp32_drivers拷贝到新建的空项目的components下

***3.***配置menuconfig  LVGL配置将设置显示器长宽，单色显示。配置IIS，其中SDA为21、SCL为22

***4.***配置完成后进行第一次编译，编译过程中提示error "Unsupported orientation"，为ssd1306.c未定义显示方向

在ssd1306.c中第75行，手动添加#define CONFIG_LV_DISPLAY_ORIENTATION_LANDSCAPE 1，再次编译通过

***5.***将下载下来的main.c中的全部内容复制到，新建项目main.c中，编译通过。OLED正确显示demo_gui内容“HELLO, WORD"

pic目录下图片显示demo