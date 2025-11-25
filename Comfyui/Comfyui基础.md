# 条件输入模块
# 潜空间
- K采样器

AI处理图像的空间，加噪去糟采样生成的图片，但是生成的图片仅仅被ai识别

VAE解码
# 像素空间

安装controlnet_aux插件

下载controlnet模型

模型放置到：comfyui安装目录/models/controlnet里面

降噪

相当于重绘服务，数值越小，越忠于原图效果，数值越大，画图会改变增加ai的想法

https://huggingface.co/vrgamedevgirl84/Wan14BT2VFusioniX

解压路径不能包含中文

保证整合包放到内存至少为80g的硬盘当中去的

空latent当中的batch决定了出图多少

<img width="1231" height="728" alt="image" src="https://github.com/user-attachments/assets/95ba7e0c-11a3-4ab8-9e11-e10a9658cdce" />

k采样器

随机种

运行后操作

步数

cfg

采样器

调度器

降噪

cfg控制最终图像和提示词的匹配程度，

cfg值越高和关键词匹配的

cfg值5-8就可以了

karras调度器

采样器


<img width="1299" height="719" alt="image" src="https://github.com/user-attachments/assets/18f155c4-0f8a-427e-94a4-32646671aaba" />

调度器的作用就是控制降噪的方法

采样器的作用就是控制降噪的程度

越靠前的词汇权重越高

模糊混乱低质量无细节

U-net为这个图片进行降噪，降噪值会结合我们的clip的文本编码器输入的特征向量

u-net为了让我们降噪的图片尽可能往那个方向去靠拢的

降噪值为0和原图一模一样了

https://huggingface.co/spaces/fancyfeast/joy-caption-pre-alpha

反推提示词

# 高清放大

Latent按照系数缩放

系数2.0

缩放方法：nearest-exact

Latent-按照系数缩放的
系统越大，锯齿形状越明显

# control-net

线稿上色

LineArt,SoftEdge

sd1.5:512*512


1024*1024的图片，上限更高的

HED Soft-Edge lines

PiDINEt Soft-Edge lines
