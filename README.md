#说明文档
命令行启动：CUDA_VISIBLE_DEVICES=0,1 python main.py --data /home/chenqiongbin/fuxian/ACPL/dataset --task cx14 --resize 512 --batch-size 8 --epochs 20  --dist-url 'tcp://localhost:10001' --multiprocessing-distributed --world-size 1 --rank 0  --desc ACPL_2_1_k150 --num-workers 4 --eval-interval 100 --reinit --label_ratio 2 --runtime 1 --topk 150 --pl-epochs 10  --ds-mixup --sel 1 --num-gmm-sets 3 --lr 0.03

对于重要参数进行讲解：
--resize 设置图片裁剪的大小
--epochs 设置训练的轮次
--reinit --label_ratio 训练集中标签样本占比
--topk   在设置最近邻时最近邻的个数
--sel    选择不同信息量的样本进行伪标签，0是低信息量，1是中等信息量，2是高信息量

data\dataloaders\dataloader_semi.py 用于数据预处理，随机挑选训练集和测试集
运行程序之前先对数据进行预处理

