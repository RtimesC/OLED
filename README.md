# 0.96寸 OLED 显示屏驱动 (I2C接口)

本项目是基于 STM32 的 0.96 寸 OLED 显示屏驱动程序，支持 4 针脚 I2C 接口，使用 GB2312 字符编码。

## 📋 项目简介

- **显示屏型号**: 0.96寸 OLED (通常为 SSD1306 驱动芯片)
- **通信接口**: I2C (4针脚: VCC, GND, SCL, SDA)
- **字符编码**: GB2312 (支持中文显示)
- **开发环境**: Keil uVision
- **目标平台**: STM32 系列单片机

## 🗂️ 项目结构

```
OLED/
├── Hardware/          # 硬件驱动层 (OLED驱动文件)
├── System/            # 系统层代码
├── User/              # 用户应用层代码 (main.c等)
├── Library/           # STM32标准库文件
├── Start/             # 启动文件
├── Objects/           # 编译输出对象文件
├── Listings/          # 编译列表文件
├── DebugConfig/       # 调试配置
├── Project.uvprojx    # Keil工程文件
└── Project.uvoptx     # Keil工程选项文件
```

## ✨ 功能特性

- ✅ OLED 基础显示功能
- ✅ I2C 通信协议
- ✅ 中文字符显示支持 (GB2312)
- ✅ 英文字符和数字显示
- ✅ 图形绘制功能
- ✅ 完整的功能函数测试示例

## 🔧 硬件连接

| OLED引脚 | STM32引脚 | 说明 |
|----------|-----------|------|
| VCC      | 3.3V/5V   | 电源正极 |
| GND      | GND       | 电源地 |
| SCL      | (查看代码确认) | I2C时钟线 |
| SDA      | (查看代码确认) | I2C数据线 |

> 注意：请根据实际的引脚配置修改上表中的 STM32 引脚号

## 🚀 快速开始

### 1. 克隆项目

```bash
git clone https://github.com/RtimesC/OLED.git
cd OLED
```

### 2. 打开工程

- 使用 Keil uVision 打开 `Project.uvprojx`
- 确保已安装对应的 STM32 芯片支持包

### 3. 编译下载

1. 点击 Keil 的编译按钮 (F7)
2. 连接 ST-Link 或其他下载器
3. 下载程序到 STM32 (F8)

### 4. 运行测试

程序下载完成后，OLED 屏幕应该会显示测试内容。

## 📝 使用示例

```c
#include "oled.h"

int main(void)
{
    // 初始化 OLED
    OLED_Init();
    
    // 清屏
    OLED_Clear();
    
    // 显示字符串
    OLED_ShowString(0, 0, "Hello OLED!");
    
    // 显示中文
    OLED_ShowChinese(0, 2, "你好世界");
    
    while(1)
    {
        // 主循环
    }
}
```

## 📚 API 说明

主要函数（请根据实际代码调整）：

- `OLED_Init()` - 初始化OLED
- `OLED_Clear()` - 清屏
- `OLED_ShowChar()` - 显示单个字符
- `OLED_ShowString()` - 显示字符串
- `OLED_ShowChinese()` - 显示中文
- `OLED_ShowNum()` - 显示数字
- `OLED_DrawBMP()` - 显示图片

## 🛠️ 开发环境

- **IDE**: Keil uVision 5 或更高版本
- **编译器**: ARM Compiler
- **调试器**: ST-Link / J-Link
- **标准库**: STM32 标准外设库

## 📄 许可证

本项目遵循 MIT 许可证 - 详见 [LICENSE](LICENSE) 文件

## 👤 作者

- **GitHub**: [@RtimesC](https://github.com/RtimesC)

## 🤝 贡献

欢迎提交 Issue 和 Pull Request！

## 📮 联系方式

如有问题，请通过 GitHub Issues 联系。

---

⭐ 如果这个项目对你有帮助，请给个 Star！