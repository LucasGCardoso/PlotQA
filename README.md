# PlotQA: Reasoning over Scientific Plots
This repository provides the PlotQA dataset which deals with the task of question-answering over a very specific class of images, namely scientific plots such as bar plots, line plots, and dot-line plots. This work is to be presented at <a href="https://wacv20.wacv.net/" target="_blank">WACV 2020</a>.

<!--
This repository provides the dataset described in the paper:

**[PlotQA: Reasoning over Scientific Plots](https://arxiv.org/pdf/1909.00997.pdf)**
 <br>
 <a href="https://gangulypritha.github.io/" target="_blank">Pritha Ganguly</a>,
 <a href="https://niteshmethani.github.io/" target="_blank">Nitesh Methani</a>,
<a href="https://www.cse.iitm.ac.in/~miteshk/" target="_blank">Mitesh Khapra</a>,
<a href="http://www.cse.iitm.ac.in/~pratyush/" target="_blank">Pratyush Kumar</a>


This paper deals with the task of question-answering over a very specific class of images, namely scientific plots such as bar plots, line plots, and dot-line plots. This work is to be presented at <a href="https://wacv20.wacv.net/" target="_blank">WACV 2020</a>.
-->


### What is PlotQA?
PlotQA is a VQA dataset with 28.9 million question-answer pairs grounded over 224,377 plots on data from real-world sources and questions based on crowd-sourced question templates. 

### Why PlotQA?
Existing synthetic datasets ([FigureQA](https://arxiv.org/pdf/1710.07300.pdf), [DVQA](https://arxiv.org/pdf/1801.08163.pdf)) for reasoning over plots do not contain variability in data labels, real-valued data, or complex reasoning questions. Consequently, proposed models for these datasets do not fully address the challenge of reasoning over plots. In particular, they assume that the answer comes either from a small fixed size vocabulary or from a bounding box within the image. However, in practice this is an unrealistic assumption because many questions require reasoning and thus have real valued answers which appear neither in a small fixed size vocabulary nor in the image. In this work, we aim to bridge this gap between existing datasets and real world plots by introducing PlotQA. Further, 80.76% of the out-of-vocabulary (OOV) questions in PlotQA have answers that are not in a fixed vocabulary.

<!-- To know more about PlotQA, read our full paper [here](https://arxiv.org/pdf/1909.00997.pdf). -->

Few examples of the {plot, question, answer} triplets from the PlotQA dataset are given below:

<p float="center">
	<!--- <img src="images/sample_images.png" width="400" /> --->
	<img src="images/sample_images.png" />
</p>

#

### Dataset Download Links

**Images**

`png` directory contains RGBA images of the scientific plots in `.png` format. The plot images are named as `0.png`, `1.png`, etc.

The plot images for different data splits can be downloaded from the following link:

[Train](https://drive.google.com/file/d/1AYuaPX-Lx7T0GZvnsPgN11Twq2FZbWXL/view?usp=sharing), [Validation](https://drive.google.com/file/d/1i74NRCEb-x44xqzAovuglex5d583qeiF/view?usp=sharing), [Test](https://drive.google.com/file/d/1D_WPUy91vOrFl6cJUkE55n3ZuB6Qrc4u/view?usp=sharing)

#
**Annotations**

`annotations.json` is a list of dictionaries where each dictionary represents the ground-truth annotations of a plot.
It consists the following fields:
```
models: It is a list of dictionaries. Depending on the type of the plot (single or 2,3,4-multi), 
	the length of the dictionary can vary from 1 to 4. Each dictionary contain the following keys-
		name: Label corresponding to each datapoint.
		color: Color corresponding to the `name` datapoint.
		bboxes: Each bounding box corresponding to the `name` datapoints in the plot.

type: Type of the plot (vbar_categorical, hbar_categorical, dot_line, line).

general_figure_info: It is a dictionary containng the following keys-
		title: Bounding box and the text corresponding to the title of the plot.
		x_axis: Bounding boxes, axis labels, ticks lables corresponding to the x-axis of the plot.
		y_axis: Bounding boxes, axis labels, ticks lables corresponding to the y-axis of the plot.
		legend: Bounding boxes, axis labels, ticks lables corresponding to the legend of the plot.
		plot_info: Bounding box corresponding to the plot.
		figure_info: Bounding box corresponding to the figure.
	
image_index: Image-index corresponding to each image.
```

The annotations for the plot images for different data splits can be downloaded from the following links:

[Train](https://drive.google.com/file/d/1VzWwxBVrlep17BGZU17GpLuGpwjyWbzq/view?usp=sharing), [Validation](https://drive.google.com/file/d/1CCp1tvMd62LfBrWa6pRdb1lpg68A2yFw/view?usp=sharing), [Test](https://drive.google.com/file/d/1ikiPqkDgxNilYsU5hbK03T4_x2eDmopP/view?usp=sharing)

#
**Question-Answer pairs**

`qa_pairs.json` is a list of dictionaries where each dictionary represents a question. Each question is represented using the following fields:
```
image_index: Image-index corresponding to the image on which this question is being asked.

question_string: Text of the question.

answer: Answer corresponding to the question `question_string`.

answer_bbox: Bounding box of the answer if the answer comes from the plot itself.

template: Template from which `question_string` is being instantiated.

type: Type of the plot (vbar_categorical, hbar_categorical, dot_line, line).
```

`qa_pairs_v1.json`: This .json file contains 8,190,674 number of question-answer pairs. 

The question-answer pairs for different data splits can be downloaded from the following links:

[Train](https://drive.google.com/file/d/1bBSUutd-Die27ZH3QTMVhBjW9l5hAwrr/view?usp=sharing), [Validation](https://drive.google.com/file/d/1yUjF_9Jgx720Kffef4_JDRt7lTHQZlKH/view?usp=sharing), [Test](https://drive.google.com/file/d/1pKujAjE4yMpSJ8gEQWIxdEyGkorJHeFm/view?usp=sharing)

`qa_pairs_v2.json`: This .json file is an extended version of the `qa_pairs_v1.json` which has 28,952,641 number of question-answer pairs.

The extended version of the question-answer pairs for different data splits can be downloaded from the following links:

[Train](https://drive.google.com/file/d/1UNvkdq1YJD_ne6D3zbWtoQij37AtfpNp/view?usp=sharing), [Validation](https://drive.google.com/file/d/1y9RwXSye2hnX0e2IlfSK34ESbeVblhH_/view?usp=sharing), [Test](https://drive.google.com/file/d/1OQBkoe_dpvFs-jnWAdRdxzh1-hgNd9bO/view?usp=sharing)

#
# QA-as-classification code
Visual Element Detection (VED) stage:
We used Detectron which is Facebook AI Research's software system that implements state-of-the-art object detection algorithms. It is written in Python and powered by the Caffe2 deep learning framework. We used the Faster RCNN with FPN model given at https://github.com/facebookresearch/Detectron for detecting different elements in the plot images.

Now follow these instructions to train the Faster RCNN with FPN model on PlotQA dataset:
1. Install Caffe2 and Detecron. You might have to use the script given in the link (https://drive.google.com/file/d/1uk8qqzcvLV7fWQ6EcavVBb0BYXxPGf5U/view?usp=sharing) to install Caffe2 on a AWS GPU instance.
2. Download the PlotQA images and the annotations from here and put it in the directory: ~/Detectron/detectron/datasets/data/.
3. Replace the ~/Detectron/detectron/datasets/dataset_catalog.py with the file given here.
4. Download the xyz.yaml config file from here.
5. Run this command to start training:
python tools/train_net.py --cfg [PATH_TO_THE_CONFIG]/e2e_faster_rcnn_R-50-FPN_1x.yaml  OUTPUT_DIR [PATH_TO_OUTPUT_DIR]

#
# Contact
If you have any questions, suggestions or comments about the dataset in the paper, feel free to contact us at:
Nitesh Methani (nmethani@cse.iitm.ac.in), Pritha Ganguly (prithag@cse.iitm.ac.in).

<!---
The annotations expand to about 800 MB.

Please cite the following if you use the PlotQA dataset in your work:
```
@inproceedings{kafle2018dvqa,
  title={DVQA: Understanding Data Visualizations via Question Answering},
  author={Kafle, Kushal and Cohen, Scott and Price, Brian and Kanan, Christopher},
  booktitle={CVPR},
  year={2018}
}
```
--->
