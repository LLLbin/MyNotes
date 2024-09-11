# FFmpeg

### [官方文档](https://www.ffmpeg.org/)

---

## **第一部分：FFmpeg 基本命令的使用**

### 1. **安装 FFmpeg**

- **Linux** 安装:

  ```bash
  sudo apt update
  sudo apt install ffmpeg
  ```
- **macOS** 安装（通过 Homebrew）:

  ```bash
  brew install ffmpeg
  ```
- **Windows** 安装

下载预编译版本：[https://ffmpeg.org/download.html](https://ffmpeg.org/download.html)，然后将其添加到环境变量中。

### 2. **查看 FFmpeg 版本**

```bash
ffmpeg -version
```

### 3. **图像处理**

#### 3.1 **图像转换格式**

将 PNG 图像转换为 JPEG：

```bash
ffmpeg -i input.png output.jpg
```

#### 3.2 **从视频中提取帧图像**

将视频中的每一帧保存为 PNG 格式的图像：

```bash
ffmpeg -i input.mp4 frames/output_%04d.png
```

#### 3.3 **将一组图像合成视频**

将一系列命名为 `frame_0001.png`、`frame_0002.png` 的图像合成为视频：

```bash
ffmpeg -framerate 24 -i frame_%04d.png -c:v libx264 -r 30 -pix_fmt yuv420p output.mp4
```

- `-framerate 24`：设置输入帧率为 24 fps。
- `-r 30`：输出帧率为 30 fps。

### 4. **视频处理**

#### 4.1 **格式转换**

将 MP4 转换为 AVI 格式：

```bash
ffmpeg -i input.mp4 output.avi
```

#### 4.2 **调整比特率**

将视频比特率调整为 1000 kbps：

```bash
ffmpeg -i input.mp4 -b:v 1000k output.mp4
```

#### 4.3 **调整帧率**

将视频帧率调整为 30 fps：

```bash
ffmpeg -i input.mp4 -r 30 output.mp4
```

#### 4.4 **改变分辨率**

将视频分辨率调整为 1280x720：

```bash
ffmpeg -i input.mp4 -s 1280x720 output.mp4
```

#### 4.5 **视频裁剪**

裁剪视频，从 00:00:10 开始，持续 30 秒：

```bash
ffmpeg -i input.mp4 -ss 00:00:10 -t 00:00:30 -c copy output.mp4
```

#### 4.6 **视频旋转**

将视频顺时针旋转 90 度：

```bash
ffmpeg -i input.mp4 -vf "transpose=1" output.mp4
```

#### 4.7 **视频合并**

将多个视频文件合并：

1. 创建 `filelist.txt`，内容如下：

   ```
   file 'input1.mp4'
   file 'input2.mp4'
   file 'input3.mp4'
   ```
2. 执行以下命令：

   ```bash
   ffmpeg -f concat -safe 0 -i filelist.txt -c copy output.mp4
   ```

### 5. **音频处理**

#### 5.1 **提取音频**

从视频中提取音频并保存为 MP3：

```bash
ffmpeg -i input.mp4 -q:a 0 -map a output.mp3
```

#### 5.2 **音频格式转换**

将 WAV 音频文件转换为 MP3：

```bash
ffmpeg -i input.wav output.mp3
```

#### 5.3 **调整音频比特率**

将音频文件比特率调整为 128 kbps：

```bash
ffmpeg -i input.mp3 -b:a 128k output.mp3
```

---

## **第二部分：结合 x264、x265、VVC 的使用**

### 1. **x264 编码和解码**

#### 1.1 **使用 x264 进行视频编码**

```bash
ffmpeg -i input.mp4 -c:v libx264 -preset slow -crf 23 output.mp4
```

- `-preset slow`：编码器速度（fast、medium、slow 等）。
- `-crf 23`：CRF 值（恒定速率因子），控制质量，范围 0-51，值越低质量越高。

#### 1.2 **控制 x264 比特率**

```bash
ffmpeg -i input.mp4 -c:v libx264 -b:v 2000k output.mp4
```

- `-b:v 2000k`：将视频比特率设置为 2000 kbps。

#### 1.3 **x264 解码**

```bash
ffmpeg -i input_x264.mp4 -c:v libx264 output_decoded.mp4
```

### 2. **x265 编码和解码**

#### 2.1 **使用 x265 进行视频编码**

```bash
ffmpeg -i input.mp4 -c:v libx265 -preset medium -crf 28 output.mp4
```

- `-preset medium`：设置编码速度。
- `-crf 28`：控制质量，范围 0-51，值越低质量越高。

#### 2.2 **控制 x265 比特率**

```bash
ffmpeg -i input.mp4 -c:v libx265 -b:v 1000k output.mp4
```

#### 2.3 **x265 解码**

```bash
ffmpeg -i input_x265.mp4 -c:v libx265 output_decoded.mp4
```

### 3. **VVC（H.266）编码和解码**

#### 3.1 **使用 VVC 进行视频编码**

```bash
ffmpeg -i input.mp4 -c:v libvvc -b:v 3000k output.vvc
```

- `-c:v libvvc`：指定使用 VVC 编码器。
- `-b:v 3000k`：将视频比特率设置为 3000 kbps。

#### 3.2 **控制 VVC 的 QP（量化参数）**

```bash
ffmpeg -i input.mp4 -c:v libvvc -qp 32 output.vvc
```

- `-qp 32`：设置量化参数为 32，越低质量越高。

#### 3.3 **VVC 解码**

```bash
ffmpeg -i input.vvc -c:v libvvc output_decoded.mp4
```

#### 3.4 **使用 VVC 的编码模式（AI、RA、LD）**

- **AI（All Intra 模式）**：
- 所有的帧都使用 帧内编码（Intra Frame Encoding），即每帧独立编码，不依赖于其他帧。
- 适用于高质量、低延迟的场景，例如视频编辑和存档。
- 优点：解码时独立，每一帧可以单独解码。
- 缺点：压缩效率较低，文件较大。
- `-g 1`：设置 GOP（Group of Pictures）大小为 1，意味着每帧都是 I 帧。

  ```bash
  ffmpeg -i input.mp4 -c:v libvvc -g 1 output_ai.vvc
  ```
- **RA（Random Access 模式）**：
- 随机访问编码模式，其中会定期插入帧内编码帧（I-frames）以及帧间编码帧（P-frames 和 B-frames），允许用户从视频的任意位置开始播放。
- 适用于点播视频、流媒体等需要随机访问的场景。
- 优点：压缩效率高，支持随机跳转。
- 缺点：延迟比 AI 模式稍高。
- `-g 48`：设置 GOP 大小为 48 帧，即每 48 帧插入一个 I 帧。
- `-bf 2`：设置 B 帧的数量为 2（即每组 P 帧之间插入 2 个 B 帧）。
- `-qp 32`：设置量化参数为 32。

  ```bash
  ffmpeg -i input.mp4 -c:v libvvc -g 48 -bf 2 output_ra.vvc
  ```
- **LD（Low Delay 模式）**：
- 低延迟编码模式，使用帧间编码，但通常不会插入 B-frames，从而降低延迟。
- 适用于实时应用，如视频通话和直播。
- 优点：延迟低，适合实时传输。
- 缺点：压缩效率低于 RA 模式。
- `-g 16`：GOP 大小为 16 帧，每 16 帧插入一个 I 帧。
- `-bf 0`：禁用 B 帧。
- `-qp 32`：设置量化参数为 32。

  ```bash
  ffmpeg -i input.mp4 -c:v libvvc -g 16 -bf 0 output_ld.vvc
  ```
