1. 


编译SSDT文件：https://zhuanlan.zhihu.com/p/95045901


更新版本：



HibernationFixup.kext 1.4.6	黑苹果睡眠修复

- -hbfx-dump-nvram 在休眠之前和内核崩溃之后将NVRAM保存到文件nvram.plist中（带有崩溃信息）

- -hbfx-disable-patch-pci 禁用IOPCIFamily的修补程序（此修补程序有助于避免恢复后挂起和黑屏（不会为所有设备调用restoreMachineState）

- hbfx-patch-pci = XHC，IMEI，iGPU允许指定设备列表，restoreMachineState不会仅针对这些设备被调用

- -hbfxdbg 打开调试输出

- -hbfxbeta 启用在不受支持的osx上加载

- -hbfxoff 禁用kext加载

  

Lilu.kext 1.6.2 黑苹果第三方驱动内核扩展

- -liludbg 以启用 Debug 输出（在 Debug 二进制文件中可用）
- -liludbgall 以在 Lilu 和所有加载的插件中启用 Debug 输出（在 Debug 二进制文件中可用）
- -liluoff 禁用 Lilu
- -liluuseroff 以禁用 Lilu 用户修补程序（例如 dyld_shared_cache 操作）
- -liluslow 以启用旧版用户修补程序
- -lilulowmem 以禁用内核解压缩（在恢复模式下禁用Lilu）
- -lilubeta 以在不受支持的操作系统版本上启用 Lilu（ 10.13 及更低版本默认启用）
- -lilubetaall 以在不受支持的 macOS 版本上启用 Lilu 和所有已加载的插件（可能造成未知后果，小心使用）
- -liluforce 以强制启用 Lilu，不管其模式，操作系统，安装程序或恢复模式
- liludelay=1000 可以在每次 Debug 输出后启用1秒的延迟以方便故障排除
- lilucpu=N 可使 Lilu 和插件设定 Nth CPUInfo::CpuGeneration
- liludump=N 以使 Lilu Debug 版本在 N秒 后将日志转储到 /var/log/Lilu_VERSION_KERN_MAJOR.KERN_MINOR.txt