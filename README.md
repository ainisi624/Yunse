# 云瑟 · D714

基于 FPGA 的数字乐器参赛源码。硬件为 Verilog，桌面上位机为 Python。

## 下载完整源码

[下载 D714 全部代码（RAR）](Yunse.rar)

解压后打开 `Yunse_D714_Source`。压缩包包含完整工程目录和全部 217 个提交文件：

- `hardware/`：73 个 Verilog 文件、Gowin 工程、引脚约束、时钟约束及 ROM 参数。
- `software/desktop/`：桌面上位机、C 音频渲染器源码、界面资源、依赖清单及测试。
- `software/host/`：串口协议、会话管理及配套工具。

源码对应 USERCODE `0000D714`。普通注释、缓存、日志和历史构建产物已清理，功能性综合指令及第三方许可信息保留。包内不含个人曲库、免安装程序或位流。

## 构建

硬件：Gowin V1.9.12.03，器件 `GW5AST-LV138FPG676AC1/I0`，顶层 `yunse_guzheng_board_top`。

在 `hardware` 目录依次执行：

```text
gw_sh build_syn.tcl
gw_sh build_pnr.tcl
```

上位机：在 Windows x64 Python 环境中进入 `software/desktop`，执行：

```text
python -m pip install -r requirements.txt
python build_native.py
python app.py
```

`build_native.py` 需要 PATH 中的 Windows x64 MinGW GCC。其余构建和打包说明见源码包内 README。

## 提交前核验

- 73 个 Verilog 文件编译通过，零错误、零警告。
- 294 项软件测试通过。
- RAR 完整性测试及解压后逐文件 SHA-256 核对通过。

源码包 SHA-256：

```text
2f85e48b9bf98bdf2e670b05198c57d96da9b23f535cc238c0153c3ee0a5307a
```