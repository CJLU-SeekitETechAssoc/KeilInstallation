# 完全安装 Keil 开发环境

按照本文安装方法，实现

-  Keil C51 和 Keil MDK 共存
- 最新版 Keil 配置 AC5 编译器
- 最新版 Keil 5 兼容 Keil 4/3/2 项目

---

## 下载所需的包

从协会网盘下载，下载后文件如下

![image-20240722113907032](https://testingcf.jsdelivr.net/gh/neoluxis/image/image-07/202407221213234.png)

## 安装 Keil C51

运行 `1_C51Vxxx.exe` 安装到系统，记住安装位置

![image-20240722114019101](https://testingcf.jsdelivr.net/gh/neoluxis/image/image-07/202407221213235.png)

## 安装 Keil MDK

运行 `2_MDKxxx.exe` 安装 Keil MDK 到C51的位置

![image-20240722114121751](https://testingcf.jsdelivr.net/gh/neoluxis/image/image-07/202407221213237.png)

安装完成后，查看 Keil 安装目录，应该既有 `C51` 文件夹，也有 `ARM` 文件夹

协会提供的版本高于 5.37，因此安装好之后，只有 AC6 编译器，但是编译标准库项目协会的一些示例需要使用 AC5 编译器，于是安装 `3_AC5setup.exe` 

![image-20240722114745733](https://testingcf.jsdelivr.net/gh/neoluxis/image/image-07/202407221213238.png)

安装位置设置为 `Keil安装目录\ARM\AC5`

## 配置激活 Keil

### 激活 Keil 

以管理员身份打开 Keil

![image-20240722114906531](https://testingcf.jsdelivr.net/gh/neoluxis/image/image-07/202407221213239.png)

静音以管理员身份打开 `4_KeilMDK5Keygen.exe`

![image-20240722115214614](https://testingcf.jsdelivr.net/gh/neoluxis/image/image-07/202407221213240.png)

打开 Keil 的激活管理器

![image-20240722115304069](https://testingcf.jsdelivr.net/gh/neoluxis/image/image-07/202407221213241.png)

![image-20240722115335354](https://testingcf.jsdelivr.net/gh/neoluxis/image/image-07/202407221213242.png)

可以看到已经激活了一个社区版许可证，在激活 Keil 之前，需要将这个许可证卸载

点击 `Activate/Deactivate`

![image-20240722115445935](https://testingcf.jsdelivr.net/gh/neoluxis/image/image-07/202407221213243.png)

将其卸载

之后进入 `Floating License`

![image-20240722115535140](https://testingcf.jsdelivr.net/gh/neoluxis/image/image-07/202407221213244.png)

复制 CID

![image-20240722115557688](https://testingcf.jsdelivr.net/gh/neoluxis/image/image-07/202407221213245.png)

粘贴进注册机

![image-20240722115704489](https://testingcf.jsdelivr.net/gh/neoluxis/image/image-07/202407221213246.png)

点击 `Generate`，将生成的注册码复制到 Keil

![image-20240722115744309](https://testingcf.jsdelivr.net/gh/neoluxis/image/image-07/202407221213247.png)

同理在注册机里把 `target` 改成 ARM，再次生成注册码，复制进 Keil 添加，完成后，证书管理器显示如下，均 2032 年到期

![image-20240722120031439](https://testingcf.jsdelivr.net/gh/neoluxis/image/image-07/202407221213248.png)

### 配置 AC5 编译器

关闭 Keil，直接双击打开（普通用户）

AC5 只用于 ARM平台编译，例如 STM32等

#### 新建一个STM32 项目

`Project/Manage/Pack Installer` 搜索 STM32F1，安装 DFP 包

![image-20240722120439030](https://testingcf.jsdelivr.net/gh/neoluxis/image/image-07/202407221213249.png)

`Project/New μVision Project`，选择保存位置和芯片型号 （协会招新使用的是 STM32F103C8T6）

![image-20240722120625040](https://testingcf.jsdelivr.net/gh/neoluxis/image/image-07/202407221213250.png)

![image-20240722120638443](https://testingcf.jsdelivr.net/gh/neoluxis/image/image-07/202407221213252.png)

在这个页面保持默认 点击 	`OK`

点开这个

![image-20240722120719582](https://testingcf.jsdelivr.net/gh/neoluxis/image/image-07/202407221213253.png)

![image-20240722120818174](https://testingcf.jsdelivr.net/gh/neoluxis/image/image-07/202407221213254.png)

![image-20240722120830453](https://testingcf.jsdelivr.net/gh/neoluxis/image/image-07/202407221213255.png)

找到安装的 AC5 文件夹，添加编译器

![image-20240722120853416](https://testingcf.jsdelivr.net/gh/neoluxis/image/image-07/202407221213256.png)

这样就实现了 AC5 和 AC6 的共存

