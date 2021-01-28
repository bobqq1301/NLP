参数列表参见[官方参数表](https://deepspeech.readthedocs.io/en/v0.9.3/Flags.html)

# 参数列表

| 参数名 | 类型 | 默认值 | 作用
| --- | --- | --- | ---
| `--train_files` | `string` |  | 训练集，可用逗号连接多个
| `--dev_files` | `string` |  | 验证集，可用逗号连接多个
| `--test_files` | `string` |  | 测试集，可用逗号连接多个
| `--metrics_files` | `string` |  | 我没看懂
| `--read_buffer` | `string` | `1MB` | 读缓冲区大小
| `--feature_cache` | `string` |  | 将MFCC特征缓存到磁盘以加快相同数据训练速度；<br/>指定从`--train_files`中提取的缓存特征所保存的路径
| `--cache_for_epochs` | `int` | `0` | 将特征缓存视为不可用的代数
| `--feature_win_len` | `int` | `32` | 特征提取音频窗口长度 (ms)
| `--feature_win_step` | `int` | `20` | 特征提取窗口步长 (ms)
| `--audio_sample_rate` | `int` | `16000` | 模型期望采样率
| `--epochs` | `int` | `75` | 总训练代数
| `--dropout_rate` | `float` | `0.05` | 前馈层dropout率
| `--dropout_rate2` | `float` | `-1.0` | 第2层dropout率，与`--dropout_rate`一致
| `--dropout_rate3` | `float` | `-1.0` | 第3层dropout率，与`--dropout_rate`一致
| `--dropout_rate4` | `float` | `0.0` | 第4层dropout率
| `--dropout_rate5` | `float` | `0.0` | 第5层dropout率
| `--dropout_rate6` | `float` | `-1.0` | 第6层dropout率，与`--dropout_rate`一致
| `--relu_clip` | `float` | `20.0` | Non-recurrent层的ReLU截断值
| `--beta1` | `float` | `0.9` | Adam优化参数
| `--beta2` | `float` | `0.999` | Adam优化参数
| `--epsilon` | `float` | `1e-8` | Adam优化参数
| `--learning_rate` | `float` | `0.001` | Adam优化学习率
| `--train_batch_size` | `int` | `1` | 一次迭代的训练样本量
| `--dev_batch_size` | `int` | `1` | 一次迭代的验证样本量
| `--test_batch_size` | `int` | `1` | 一次迭代的测试样本量
| `--export_batch_size` | `int` | `1` |
| `--inter_op_parallelism_threads` | `int` | `0` | 
| `--use_allow_growth` | `bool` | `False` |
| `--load_cudnn` | `bool` | `False` |
| `--train_cudnn` | `bool` | `False` |
| `--automatic_mixed_precision` | `bool` | `False` |
| `--limit_train` | `int` | `0` | 训练集元素数量限制
| `--limit_dev` | `int` | `0` | 验证集元素数量限制
| `--limit_test` | `int` | `0` | 测试集元素数量限制
| `--reverse_train` | `bool` | `False` | 是否反转训练集顺序
| `--reverse_dev` | `bool` | `False` | 是否反转验证集顺序
| `--reverse_test` | `bool` | `False` | 是否反转测试集顺序
| `--checkpoint_dir` | `string` |  | checkpoint文件读写位置
| `--load_checkpoint_dir` | `string` |  | checkpoint文件读取位置
| `--save_checkpoint_dir` | `string` |  | checkpoint文件存储位置
| `--checkpoint_secs` | `int` | `600` | checkpoint文件保存时间间隔
| `--max_to_keep` | `int` | `5` | 保持的checkpoint文件数量
| `--load_train` | `string` | `auto` | 选择加载的checkpoint文件<br/>`last`, `best`, `init`, `auto`
| `--load_evaluate` | `string` | `auto` | 选择作为计算任务的checkpoint文件<br/>`last`, `best`, `init`, `auto`

# 参数说明
* `--feature_cache`
    * **MFCC**：梅尔频率倒谱参数（Mel Frequency Cepstrum Coefficient）