🤖 RPA 自动化指令编辑器（RPA Command Editor）

一个基于 PySide6 + pyautogui 的桌面级 RPA（机器人流程自动化）工具，支持图形化编辑、执行 11 种自动化操作，无需编程即可实现重复性任务自动化。
![Python](https://img.shields.io/badge/Python-3.8%2B-blue?logo=python)
![License](https://img.shields.io/badge/License-MIT-green.svg)
![Platform](https://img.shields.io/badge/Platform-Windows-lightgrey)

✅ 图形化编辑界面：拖拽式添加/删除/排序指令
✅ 11 种核心操作：点击、双击、右键、文本输入、等待、滚轮、复制/粘贴/删除、快捷键、窗口激活
✅ 一键生成模板：点击【📄 新建脚本】自动填充完整示例
✅ Excel 脚本导入/导出：.xlsx 格式，兼容 Excel/WPS
✅ 后台安全执行：指令在独立线程运行，不阻塞 UI
✅ 实时日志反馈：执行过程全程可视
✅ 跨命令重试机制：失败自动重试，提升稳定性

▶ 快速开始
启动编辑器
python main.py

创建新脚本
点击 【📄 新建脚本】 → 自动生成 11 种操作示例
或手动点击 【➕ 添加】 逐条编辑
执行自动化
点击 【▶ 执行一次】 运行当前脚本
点击 【🔁 循环执行】 持续运行（慎用！）
保存/加载
【💾 保存脚本】 → 导出为 xxx.xlsx
【📂 加载脚本】 → 从 Excel 恢复指令

🧩 支持的指令类型
表格
编号	操作类型	参数说明	示例
1	左键单击	图片路径（.png）	login_button.png
2	左键双击	图片路径	file_icon.png
3	右键单击	图片路径	desktop_empty.png
4	文本输入	任意文本（自动粘贴）	admin123
5	等待	秒数（支持小数）	1.5
6	滚轮滑动	单位（正=上，负=下）	-200
7	复制	无参数	（留空）
8	粘贴	无参数	（留空）
9	删除	无参数	（留空）
10	快捷键	按键组合（小写，+连接）	ctrl+c, alt+f4
11	激活窗口	窗口标题关键词	微信, 记事本
💡 图片识别提示：将 .png 图片与脚本放在同一目录，或使用相对路径如 images/btn.png。


📂 项目结构
rpa-command-editor/
├── main.py               # 主程序（UI 入口）
├── core.py               # 核心执行引擎
├── generate_template.py  # 生成 Excel 模板（可选）
├── requirements.txt      # 依赖列表
├── README.md             # 本文件
└── images/               # （用户自建）存放截图素材

⚠️ 注意事项
仅支持 Windows：因 ACTIVATE_WINDOW 使用 pygetwindow（Windows only）
图片识别依赖屏幕分辨率：录制与执行需在相同 DPI 下进行
避免无限循环：使用【🔁 循环执行】时请确保有退出条件
权限问题：部分系统需以管理员身份运行才能操作某些窗口


🙌 最后
PySide6 - 跨平台 GUI 框架
PyAutoGUI - 自动化控制库
openpyxl - Excel 读写支持
Made with ❤️ for automation enthusiasts.
重复工作，交给机器人！
