# ML-demo
## 1.Introduction:
In the demo, we will show our results after implementing the code of training process of the paper, and you can check this by follow the steps in section 2. In this section, we will briefly introduce what we have down to complete this demo.<br>
<br>
Implementing the code of this paper in a VM in the GPU FARM without root permission is a hard work. Running this code requires many tools that are not installed in the VM which really helps to transform the form of the training pictures, setup the environment,  structure the datasets and etc. So we spent a lot of time doing these works by other means before running the code.<br>
<br>
The demo/outputs(sample)/output_of_training folder stores the outputs of our training period. We just train the MUNIT model in 10 000 iterations------- the connection to the GPU farm VM is unstable, more iterations of training would be interrupted. So our model demo can’t perform as good as the trained model in the paper (1 000 000 iterations). If you are interested in training better models or implementing the trained model in the paper, see https://github.com/NVlabs/MUNIT/blob/master/TUTORIAL.md<br>
## 2.Tutorial:
·model/gen_00010000.pt· is our pretrained model demo. You can apply the pictures in demo/inputs to test our model demo.
### 2.1 Multimodal Translation
The following command can translate edges to shoes
```
$ python test.py --config configs/edges2shoes_folder.yaml --input inputs/edges2shoes_edge.jpg --output_folder results/edges2shoes --checkpoint models/gen_00010000.pt --a2b 1
```
### 2.2 Example-guided Translation
The above command outputs diverse shoes from an edge input. In addition, it is possible to control the style of output using an example shoe image.
```
$ python test.py --config configs/edges2shoes_folder.yaml --input inputs/edges2shoes_edge.jpg --output_folder results --checkpoint models/gen_00010000.pt --a2b 1 --style inputs/edges2shoes_shoe.jpg
```
