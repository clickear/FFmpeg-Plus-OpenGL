# FFmpeg + OpenGL (ffmpeg 滤镜)

## <a href="README.MD">English</a> | <a href="README_ZH.MD"><b>中文</b></a>
<hr>

- [介绍](#介绍)
    - [使用示例展示](#使用示例展示)

- [如何使用 FFmpeg+OpenGL Shader Filter: vf_glplusshader](#ffmpeg-plus-gl-shader)
    
    - [目录结构](#目录结构)
    - [编译构建](#编译构建)
    - [运行](#运行)

- [相关帮助](#相关帮助)
    - [FFmpeg编译相关帮助 - 如果不知道FFmpeg是如何编译怎么办](#FFmpeg编译相关帮助)

- [关于](#关于)

## 介绍 ##

一个可以在FFmpeg cmd里使用的OpenGL滤镜，可以自己写shader并且动态加载渲染。

可以使用 <a href="Plus-GL-Shader">滤镜 `plusglshader`</a> 来渲染你的视频。


### 使用示例展示 ###

* 示例脚本 <a href="Plus-GL-Shader/run_example.sh">`Plus-GL-Shader/run_example.sh`</a>

* 示例Shaders: <a href="Plus-GL-Shader/gl">`示例Shader目录 ./Plus-GL-Shader/gl`</a>

* 效果如下

| shader name | source | render |
| - | - | - |
| Fragments Shader: <br><a href="Plus-GL-Shader/gl/sway_shader.gl">Plus-GL-Shader/gl/sway_shader.gl</a><br>Vertex Shader: <br><a href="Plus-GL-Shader/gl/sway_vertex.gl">Plus-GL-Shader/gl/sway_vertex.gl</a> | <img src="Plus-GL-Shader/cat_quqi.jpeg" width="300" /> | <img src="Plus-GL-Shader/example_show/sway.gif" width="300" /> |
| Fragments Shader: <br><a href="Plus-GL-Shader/gl/jitter_shader.gl">Plus-GL-Shader/gl/jitter_shader.gl</a><br>Vertex Shader: <br><a href="Plus-GL-Shader/gl/jitter_vertex.gl">Plus-GL-Shader/gl/jitter_vertex.gl</a> | <img src="Plus-GL-Shader/cat_quqi.jpeg" width="300" /> | <img src="Plus-GL-Shader/example_show/jitter.gif" width="300" /> |
| Fragments Shader: <br><a href="Plus-GL-Shader/gl/preview_shader.gl">Plus-GL-Shader/gl/preview_shader.gl</a><br>Vertex Shader: <br><a href="Plus-GL-Shader/gl/preview_vertex.gl">Plus-GL-Shader/gl/preview_vertex.gl</a> | <img src="Plus-GL-Shader/cat_quqi.jpeg" width="300" /> | <img src="Plus-GL-Shader/example_show/preview.gif" width="300" /> |
| Fragments Shader: <br><a href="Plus-GL-Shader/gl/soul_shader.gl">Plus-GL-Shader/gl/soul_shader.gl</a><br>Vertex Shader: <br><a href="Plus-GL-Shader/gl/soul_vertex.gl">Plus-GL-Shader/gl/soul_vertex.gl</a> | <img src="Plus-GL-Shader/cat_quqi.jpeg" width="300" /> | <img src="Plus-GL-Shader/example_show/soul.gif" width="300" /> |
| Fragments Shader: <br><a href="Plus-GL-Shader/gl/split_interval_shader.gl">Plus-GL-Shader/gl/split_interval_shader.gl</a><br>Vertex Shader: <br><a href="Plus-GL-Shader/gl/split_interval_vertex.gl">Plus-GL-Shader/gl/split_interval_vertex.gl</a> | <img src="Plus-GL-Shader/cat_quqi.jpeg" width="300" /> | <img src="Plus-GL-Shader/example_show/split_interval.gif" width="300" /> |
| Fragments Shader: <br><a href="Plus-GL-Shader/gl/stab_ci_shader.gl">Plus-GL-Shader/gl/stab_ci_shader.gl</a><br>Vertex Shader: <br><a href="Plus-GL-Shader/gl/stab_ci_vertex.gl">Plus-GL-Shader/gl/stab_ci_vertex.gl</a> | <img src="Plus-GL-Shader/cat_quqi.jpeg" width="300" /> | <img src="Plus-GL-Shader/example_show/stab_ci.gif" width="300" /> |
| Fragments Shader: <br><a href="Plus-GL-Shader/gl/test_shader.gl">Plus-GL-Shader/gl/test_shader.gl</a><br>Vertex Shader: <br><a href="Plus-GL-Shader/gl/test_vertex.gl">Plus-GL-Shader/gl/test_vertex.gl</a> | <img src="Plus-GL-Shader/cat_quqi.jpeg" width="300" /> | <img src="Plus-GL-Shader/example_show/test.gif" width="300" /> |
| Fragments Shader: <br><a href="Plus-GL-Shader/gl/white_mask_shader.gl">Plus-GL-Shader/gl/white_mask_shader.gl</a><br>Vertex Shader: <br><a href="Plus-GL-Shader/gl/white_mask_vertex.gl">Plus-GL-Shader/gl/white_mask_vertex.gl</a> | <img src="Plus-GL-Shader/cat_quqi.jpeg" width="300" /> | <img src="Plus-GL-Shader/example_show/white_mask.gif" width="300" /> |
| Fragments Shader: <br><a href="Plus-GL-Shader/gl/split_4_shader.gl">Plus-GL-Shader/gl/split_4_shader.gl</a><br>Vertex Shader: <br><a href="Plus-GL-Shader/gl/split_4_vertex.gl">Plus-GL-Shader/gl/split_4_vertex.gl</a> | <img src="Plus-GL-Shader/cat_quqi.jpeg" width="300" /> | <img src="Plus-GL-Shader/example_show/split_4.gif" width="300" /> |
| Fragments Shader: <br><a href="Plus-GL-Shader/gl/split_9_shader.gl">Plus-GL-Shader/gl/split_9_shader.gl</a><br>Vertex Shader: <br><a href="Plus-GL-Shader/gl/split_9_vertex.gl">Plus-GL-Shader/gl/split_9_vertex.gl</a> | <img src="Plus-GL-Shader/cat_quqi.jpeg" width="300" /> | <img src="Plus-GL-Shader/example_show/split_9.gif" width="300" /> |
| Fragments Shader: <br><a href="Plus-GL-Shader/gl/split_vert2_shader.gl">Plus-GL-Shader/gl/split_vert2_shader.gl</a><br>Vertex Shader: <br><a href="Plus-GL-Shader/gl/split_vert2_vertex.gl">Plus-GL-Shader/gl/split_vert2_vertex.gl</a> | <img src="Plus-GL-Shader/cat_quqi.jpeg" width="300" /> | <img src="Plus-GL-Shader/example_show/split_vert2.gif" width="300" /> |

## FFmpeg-Plus-GL-Shader ##

### 目录结构 ###

* Filter Source Code Path: <a href="Plus-GL-Shader">Plus-GL-Shader</a>

    * libavfilter.diff

    * vf_plusglshader.c

### 编译构建 ###

* 相关依赖
    * Centos 7.x+ || Linux

        * 第一步 安装相关依赖
            ```shell
            yum install -y glew glew-devel
            yum install -y glfw glew-devel
            yum install -y mesa-dri-drivers

            #
            # If can not compile , you need
            #
            yum install -y libGLEW*
            yum install -y mesa
            yum install -y mesa-libGLU mesa-libGLU-devel
            yum install -y libXfont*
            ```

        * 第二步（可选）
            > 如果你在无显卡环境下跑此滤镜（比如你的生产环境服务器）,需要xvfb的支持

            ```shell
            yum install -y xorg-x11-server-Xvfb 
            ```

    * Ubuntu || Linux

        * 第一步 安装相关依赖
            ```shell
            apt-get install libglfw3-dev libglfw3
            apt-get install libglew2.0 libglew-dev
            ```

        * 第二步（可选）
            > 如果你在无显卡环境下跑此滤镜（比如你的生产环境服务器）,需要xvfb的支持

            ```shell
            apt-get install xvfb
            ```

    * MacOS下编译 （需要brew支持）
        ```shell
        brew install glew glfw
        ```

* 编译构建

    * 下载源码
        ```shell
        git clone https://github.com/numberwolf/FFmpeg-Plus-OpenGL.git
        git clone https://github.com/FFmpeg/FFmpeg.git # for 4.x+
        
        cd FFmpeg
        
        #
        # Patch
        #
        cp ../FFmpeg-Plus-OpenGL/Plus-GL-Shader/vf_plusglshader.c libavfilter/
        git apply ../FFmpeg-Plus-OpenGL/Plus-GL-Shader/libavfilter.diff
        ```

    * 编译
        * 编译的`必选项` - 和此滤镜相关
            > --enable-opengl \
            > --extra-libs='-lGLEW -lglfw' \
            > --enable-filter=plusglshader

        * 编译示例 - 可以不参考此示例，但是必须加上`必选项`
            ```shell
            #!/bin/bash
            ./configure \
              --enable-cross-compile \
              --pkg-config-flags="--static" \
              --extra-ldflags="-lm -lz -llzma -lpthread" \
              --extra-libs=-lpthread \
              --extra-libs=-lm \
              --enable-gpl \
              --enable-libfdk_aac \
              --enable-libfreetype \
              --enable-libmp3lame \
              --enable-libopus \
              --enable-libvpx \
              --enable-libx264 \
              --enable-libx265 \
              --enable-libass \
              --enable-libfreetype       \
              --enable-libfontconfig     \
              --enable-libfribidi        \
              --enable-libwebp           \
              --enable-nonfree \
              --disable-shared \
              --enable-static \
              --enable-opengl \
              --extra-libs='-lGLEW -lglfw' \
              --enable-filter=plusglshader
            make clean
            make -j16
            make install
            ```

### 运行 ###

* 检查 `Plus-GL-Shader`:`plusglshader` 滤镜是否安装成功
    * 检查命令
        ```shell
        ffmpeg -help filter=plusglshader
        ```

    * 正确输出
        ```shell
        ffmpeg version a0d68e65 Copyright (c) 2000-2020 the FFmpeg developers
          built with Apple LLVM version 10.0.0 (clang-1000.10.44.4)
          configuration: --enable-cross-compile --pkg-config-flags=--static --extra-ldflags='-lm -lz -llzma -lpthread' --extra-libs=-lpthread --extra-libs=-lm --enable-gpl --enable-libfdk_aac --enable-libfreetype --enable-libmp3lame --enable-libopus --enable-libvpx --enable-libx264 --enable-libx265 --enable-libass --enable-libfreetype --enable-libfontconfig --enable-libfribidi --enable-libwebp --enable-nonfree --disable-shared --enable-static --enable-opengl --extra-libs='-lGLEW -lglfw' --enable-filter=plusglshader
          libavutil      56. 51.100 / 56. 51.100
          libavcodec     58. 91.100 / 58. 91.100
          libavformat    58. 45.100 / 58. 45.100
          libavdevice    58. 10.100 / 58. 10.100
          libavfilter     7. 85.100 /  7. 85.100
          libswscale      5.  7.100 /  5.  7.100
          libswresample   3.  7.100 /  3.  7.100
          libpostproc    55.  7.100 / 55.  7.100
        Filter plusglshader
          Generic OpenGL shader filter
            Inputs:
               #0: default (video)
            Outputs:
               #0: default (video)
        plusglshader AVOptions:
          sdsource          <string>     ..FV...... gl fragment shader source path (default is render gray color)
          vxsource          <string>     ..FV...... gl vertex shader source path (default is render gray color)
          duration          <duration>   ..FV...... gl render duration (default 0)

        This filter has support for timeline through the 'enable' option.
        ```

* 使用`plusglfilter`转码渲染 (Transcoding)

    > plusglshader=sdsource='./test_shader.gl':vxsource='./test_vertex.gl'

    * 参数项
    
        * `sdsource` : Fragment shader file path (Default is gray)
        * `vxsource` : Vertex shader file path (Default is gray)
        * `duration` : Shader渲染生效时长,超出部分帧不做处理

    * 滤镜使用规则

        * `plusglshader`
        * `plusglshader=sdsource='./test_shader.gl':vxsource='./test_vertex.gl'`
    
    * 用你自己的Shader渲染

        * 1) Fragment shader
            > Example: <a href="Plus-GL-Shader/test_shader.gl">test_shader.gl</a>

            #### Notice: playTime is timestamp, from 0 -> end

            ```c
            uniform sampler2D tex;
            uniform float playTime;
            varying vec2 texCoord;
            void main() {
                gl_FragColor = texture2D(tex, texCoord * 0.5 + 0.5);
                float usePts = max(playTime, 0.4);
                float gray = (gl_FragColor.r + gl_FragColor.g + gl_FragColor.b) / (usePts * usePts);
                gl_FragColor.r = gray;
                gl_FragColor.g = gray;
                gl_FragColor.b = gray;
            }
            ```

        * 2) Vertex shader
            > Example: <a href="Plus-GL-Shader/test_vertex.gl">test_vertex.gl</a>

            ```c
            attribute vec2 position;
            varying vec2 texCoord;
            void main(void) {
                gl_Position = vec4(position, 0, 1);
                texCoord = position;
            }
            ```

    * 如果在无头（无显示器显卡环境下）环境下使用

        > 你需要xvfb server支持,使用如下命令

        ```shell
        xvfb-run -a --server-args="-screen 0 1280x720x24 -ac -nolisten tcp -dpi 96 +extension RANDR" \
        ffmpeg -v debug \
        -i 1000p10s_9k.mp4 \
        -filter_complex "[0:v]plusglshader=sdsource='./test_shader.gl':vxsource='./test_vertex.gl'[1outgl];[1outgl]scale=1280:-2" \
        -vcodec libx264 \
        -an \
        -pix_fmt yuv420p \
        -y test.mp4
        ```

    * 在有头（显卡 显示器）环境下运行

        ```shell
        ffmpeg -v debug \
        -i 1000p10s_9k.mp4 \
        -filter_complex "[0:v]plusglshader=sdsource='./test_shader.gl':vxsource='./test_vertex.gl'[1outgl];[1outgl]scale=1280:-2" \
        -vcodec libx264 \
        -an \
        -pix_fmt yuv420p \
        -y test.mp4
        ```

    * 输出示例

        | Tag | Src | Dst |
        |-|-|-|
        | Frame | <img src="Plus-GL-Shader/example_src.png" width="500" /> | <img src="Plus-GL-Shader/example_dst.png" width="500" /> |


## 相关帮助 ##

#### FFmpeg编译相关帮助 ####

* <a href="Plus-GL-Shader">filter `plusglshader`</a>.
    * <a href="https://trac.ffmpeg.org/wiki/CompilationGuide">如果你不知道如何编译FFmpeg，请点这里</a>
    * [学会之后可以编译我们的 `plusglshader`</a>](#build)

## 关于 ##

#### Contact

* Github: 

    * https://github.com/numberwolf/FFmpeg-Plus-OpenGL
    * https://github.com/numberwolf/h265web.js

* Email(porschegt23@foxmail.com)

* QQ: 531365872

* Discord:numberwolf#8694

* Wechat:numberwolf11



