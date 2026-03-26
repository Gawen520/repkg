# RePKG
小红车(Wallpaper engine)的PKG格式壁纸解包工具，支持TEX文件转换。

# 功能特性
- 提取PKG文件
- 将PKG转换为壁纸引擎项目
- 将TEX转换为图像
- 转储PKG/TEX信息

### 命令
- help - 显示支持的命令及其解释，使用 `help "extract"` 和 `help "info"` 查看它们的选项
- extract - 提取指定的 PKG/TEX 文件或文件夹中的文件
```
-o, --output          (默认：./output) 输出目录
-i, --ignoreexts      不提取具有指定扩展名的文件（用逗号 "," 分隔）
-e, --onlyexts        仅提取具有指定扩展名的文件（用逗号 "," 分隔）
-d, --debuginfo       在提取/反编译时打印调试信息
-t, --tex             将输入目录中的所有 TEX 文件转换为图像
-s, --singledir       将所有提取的文件放在一个目录中，而不是它们的原始路径
-r, --recursive       递归搜索指定目录的所有子文件夹
-c, --copyproject     从 PKG 旁边复制 project.json 和 preview.jpg 到输出目录
-n, --usename         使用 project.json 中的名称作为项目子文件夹名称，而不是 ID
--no-tex-convert      提取 PKG 时不要将 TEX 文件转换为图像
--overwrite           覆盖所有现有文件
--osi                 仅在输出中保存图像文件
```
- info - 转储 PKG/TEX 信息
```
-s, --sort             按字母顺序排序条目
-b, --sortby           (默认：name) 排序依据...（可用选项：name, extension, size）
-t, --tex              转储指定目录中所有 TEX 文件的信息
-p, --projectinfo      要从 project.json 转储的键（用逗号分隔）（* 表示全部）
-e, --printentries     打印包中的条目
--title-filter         标题过滤器
```

### 示例
1. 解压 PKG，默认将 TEX 转换为图像，默认保存到同目录下的 output 文件夹：

   ```
   repkg.exe extract X:\Downloads\2320649746\scene.pkg
   ```

2. 在指定目录的所有子文件夹中查找 PKG 文件，并在输出目录中创建 Wallpaper Engine 项目：

   ```
   repkg.exe extract -r -c X:\Downloads
   ```

3. 在指定目录的子文件夹中查找 PKG 文件，将 TEX 条目转换为 png，并忽略它们在 PKG 中的路径：

   ```
   repkg.exe extract -e tex -s X:\Downloads
   ```

4. 将特定文件夹中的所有 TEX 文件转换为图像：

   ```
   repkg.exe extract -t -s X:\Downloads
   ```

5. 在指定目录的所有子文件夹中查找 PKG 文件，仅提取所有图片，忽略它们原本的路径，保存在输出目录：

   ``````
   repkg.exe extract --osi -n X:\Downloads
   ``````

   

   