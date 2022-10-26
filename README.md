# 萌娃人脸生成器
<br />
&emsp;&emsp;<b>更新：基于StyleGAN2制作的新版生成器消除了生成图片中水滴斑点和扭曲/损坏现象的出现，质量大幅提升。<a href='https://github.com/a312863063/generators-with-stylegan2'>点此查看新版</a>。</b><br />
--------------------------------------------------------------------------------------------------------------------<br /><br /><br />
&emsp;&emsp;注明：之前做的一些有意思的人脸生成器，现在全部开源分享出来。它的主要作用是可生成制作各类型的人脸素材，供我们任意使用且无须担心人脸版权的问题。在定制人脸上，开源的全系列生成器包括：<a href='https://github.com/a312863063/seeprettyface-generator-yellow'>黄种人脸生成器</a>，<a href='https://github.com/a312863063/seeprettyface-generator-wanghong'>网红脸生成器</a>，<a href='https://github.com/a312863063/seeprettyface-generator-star'>明星脸生成器</a>，<a href='https://github.com/a312863063/seeprettyface-generator-model'>超模脸生成器</a>和<a href='https://github.com/a312863063/seeprettyface-generator-babies'>萌娃脸生成器</a>，同时<a href='https://github.com/a312863063/seeprettyface-face_editor'>人脸属性编辑器</a>能够对所有这些生成器生成的人物进行调整和改变。<br />
&emsp;&emsp;此项目已免费开源使用，模型版权拥有者为：www.seeprettyface.com 。<br />
<br /><br /><br />
&emsp;&emsp;这是一个用StyleGAN训练出的萌娃人脸生成器，生成效果如下所示。<br /><br /><br />

# 生成示例

## &emsp;&emsp;单张样本
&emsp;&emsp;&emsp;&emsp;&emsp;![Image text](https://github.com/a312863063/seeprettyface-generator-babies/blob/master/examples/example1.png)<br/><br/>
&emsp;&emsp;&emsp;&emsp;&emsp;![Image text](https://github.com/a312863063/seeprettyface-generator-babies/blob/master/examples/example2.png)<br/><br/>

## 概览（常规版）
![Image text](https://github.com/a312863063/seeprettyface-generator-babies/blob/master/examples/64_examples.jpg)
<br /><br /><br />
查看更多的生成样本可以前往[这里](https://pan.baidu.com/s/1JfyZYyfGzdO6TgKzOuWa0Q)（提取码：75AG），是一个含有1万张生成样本的萌娃脸数据集。<br /><br /><br />

## 概览（可爱笑容版）
![Image text](https://github.com/a312863063/seeprettyface-generator-babies/blob/master/examples/examples_cute_smile.jpg)
<br /><br /><br />
查看更多的生成样本可以前往[这里](https://pan.baidu.com/s/1G_hn-1jdOC6s_gMqsTmthg)（提取码：q9f6），是一个含有1万张生成样本的可爱笑容萌娃脸数据集。<br /><br /><br />

# 萌娃脸属性编辑
&emsp;&emsp;人脸属性编辑支持在年龄、笑容、角度、性别和光照等23个维度上对生成人物作出调整（详细了解请前往[人脸属性编辑器](https://github.com/a312863063/seeprettyface-face_editor)处）。这儿只展示5种基本调整示例。
## 笑容调整
![Image text](https://github.com/a312863063/seeprettyface-generator-babies/blob/master/examples/smile.jpg)
<br/><br/>
## 年龄调整
![Image text](https://github.com/a312863063/seeprettyface-generator-babies/blob/master/examples/age.jpg)
<br/><br/>
## 角度调整
![Image text](https://github.com/a312863063/seeprettyface-generator-babies/blob/master/examples/angle.jpg)
<br/><br/>
## 性别调整
![Image text](https://github.com/a312863063/seeprettyface-generator-babies/blob/master/examples/gender.jpg)
<br/><br/>
## 光照调整
![Image text](https://github.com/a312863063/seeprettyface-generator-babies/blob/master/examples/exposure.jpg)
<br/><br/>

# 运行代码
## 环境配置
&emsp;&emsp;Both Linux and Windows are supported, but we strongly recommend Linux for performance and compatibility reasons.<br/>
&emsp;&emsp;64-bit Python 3.6 installation. We recommend Anaconda3 with numpy 1.14.3 or newer.<br/>
&emsp;&emsp;TensorFlow 1.10.0 or newer with GPU support.<br/>
&emsp;&emsp;NVIDIA driver 391.35 or newer, CUDA toolkit 9.0 or newer, cuDNN 7.3.1 or newer.<br/>

## 运行步骤
&emsp;&emsp;1.在model文件夹中按照txt地址下载模型，放在该位置<br/>
&emsp;&emsp;2.运行generate_kid.py或者generate_smile_kid.py<br/>
<br /><br /><br />
## 了解技术原理 & 获取训练集：[点此进入](http://www.seeprettyface.com/)
![Image text](https://github.com/a312863063/seeprettyface/blob/master/EP001-01.png)<br/><br/><br/>

## 实践经验：

原始项目地址：https://github.com/a312863063/seeprettyface-generator-babies

### 1.介绍

本文是运行一个 `StyleGAN` 训练出的萌娃人脸生成器。

### 2. 实践过程

#### 1.1 下载代码库
#### 1.2 下载预训练权重

下载链接在：seeprettyface-generator-babies/model/模型下载后放在这里.txt 说明中：

	百度网盘：
		链接：https://pan.baidu.com/s/1Txa3HPxcWfL_mQynTxBJ-g 
		提取码：movs 

FK 百度网盘，太慢了。

下载解压后放在：

	model/
	├── classifier-smiling.pkl
	├── generator_kids.pkl

#### 1.3 配置环境

注释掉 `generate_kid.py`:

	# from aip import AipFace
	
创建一个 conda 环境：

	# 注意，python 不能选择3.8及以上，因为要装 tensorflow1.x
	conda create -n gan python=3.6
	# 安装一些必要包 PIL 的包名字叫 pillow
	pip install numpy pillow requests -i https://pypi.tuna.tsinghua.edu.cn/simple 
	# 安装 tensorflow-gpu
	conda install tensorflow-gpu==1.15

#### 遇到错误

安装 tensorflow-gpu ， 但是我遇到了如下错误:

	InvalidArchiveError("Error with archive /home/我的用户名/conda/pkgs/tensorflow-base-1.15.0-gpu_py36h9dcbed7_0/.cph_tmpli1l9i4d/pkg-tensorflow-base-1.15.0-gpu_py36h9dcbed7_0.tar.zst.  You probably need to delete and re-download or re-create this file.  Message from libarchive was:\n\nFailed to create dir 'lib/python3.6/site-packages/tensorflow_core/include/external/com_github_googleapis_googleapis'")
	
**解决：**

参考：https://blog.csdn.net/eaxy_z/article/details/120293066

	conda clean -p		# 删除未使用的包
	conda clean -t		# 删除缓存的tarballs包
	conda clean -a		# 删除所有缓存的数据（包括索引缓存等 ）
	
然后，重新运行：

	conda install tensorflow-gpu==1.15
	
完美运行，在 result 下生成了 20只 萌娃，还有对应的 result/generate_code。




