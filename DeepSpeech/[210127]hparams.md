参数列表参见[官方参数表](https://deepspeech.readthedocs.io/en/v0.9.3/Flags.html)

## 参数列表

### Importer
| 参数名 | 类型 | 默认值 | 作用
| --- | --- | --- | ---
| `--train_files` | `string` |  | 训练集，可用逗号连接多个
| `--dev_files` | `string` |  | 验证集，可用逗号连接多个
| `--test_files` | `string` |  | 测试集，可用逗号连接多个
| `--metrics_files` | `string` |  | *我没看懂*
| `--read_buffer` | `string` | `1MB` | 读缓冲区大小
| `--feature_cache` | `string` |  | 将MFCC特征缓存到磁盘以加快相同数据训练速度；<br/>指定从`--train_files`中提取的缓存特征所保存的路径
| `--cache_for_epochs` | `int` | `0` | 将特征缓存视为不可用的代数
| `--feature_win_len` | `int` | `32` | 特征提取音频窗口长度 (ms)
| `--feature_win_step` | `int` | `20` | 特征提取窗口步长 (ms)
| `--audio_sample_rate` | `int` | `16000` | 模型期望采样率

### Global Constants
| 参数名 | 类型 | 默认值 | 作用
| --- | --- | --- | ---
| `--epochs` | `int` | `75` | 总训练代数
| `--dropout_rate` | `float` | `0.05` | 前馈层dropout率
| `--dropout_rate2` | `float` | `-1.0` | 第2层dropout率，与`--dropout_rate`一致
| `--dropout_rate3` | `float` | `-1.0` | 第3层dropout率，与`--dropout_rate`一致
| `--dropout_rate4` | `float` | `0.0` | 第4层dropout率
| `--dropout_rate5` | `float` | `0.0` | 第5层dropout率
| `--dropout_rate6` | `float` | `-1.0` | 第6层dropout率，与`--dropout_rate`一致
| `--relu_clip` | `float` | `20.0` | Non-recurrent层的ReLU截断值

### [Adam Optimizer](http://arxiv.org/abs/1412.6980) parameters
| 参数名 | 类型 | 默认值 | 作用
| --- | --- | --- | ---
| `--beta1` | `float` | `0.9` | Adam优化参数
| `--beta2` | `float` | `0.999` | Adam优化参数
| `--epsilon` | `float` | `1e-8` | Adam优化参数
| `--learning_rate` | `float` | `0.001` | Adam优化学习率

### Batch Size
| 参数名 | 类型 | 默认值 | 作用
| --- | --- | --- | ---
| `--train_batch_size` | `int` | `1` | 一次迭代的训练样本量
| `--dev_batch_size` | `int` | `1` | 一次迭代的验证样本量
| `--test_batch_size` | `int` | `1` | 一次迭代的测试样本量
| `--export_batch_size` | `int` | `1` |

### Performance
| 参数名 | 类型 | 默认值 | 作用
| --- | --- | --- | ---
| `--inter_op_parallelism_threads` | `int` | `0` | 
| `--use_allow_growth` | `bool` | `False` |
| `--load_cudnn` | `bool` | `False` |
| `--train_cudnn` | `bool` | `False` |
| `--automatic_mixed_precision` | `bool` | `False` |

### Sample
| 参数名 | 类型 | 默认值 | 作用
| --- | --- | --- | ---
| `--limit_train` | `int` | `0` | 训练集元素数量限制
| `--limit_dev` | `int` | `0` | 验证集元素数量限制
| `--limit_test` | `int` | `0` | 测试集元素数量限制
| `--reverse_train` | `bool` | `False` | 是否反转训练集顺序
| `--reverse_dev` | `bool` | `False` | 是否反转验证集顺序
| `--reverse_test` | `bool` | `False` | 是否反转测试集顺序

### Checkpointing
| 参数名 | 类型 | 默认值 | 作用
| --- | --- | --- | ---
| `--checkpoint_dir` | `string` |  | checkpoint文件读写位置
| `--load_checkpoint_dir` | `string` |  | checkpoint文件读取位置
| `--save_checkpoint_dir` | `string` |  | checkpoint文件存储位置
| `--checkpoint_secs` | `int` | `600` | checkpoint文件保存时间间隔
| `--max_to_keep` | `int` | `5` | 保持的checkpoint文件数量
| `--load_train` | `string` | `auto` | 选择加载的checkpoint文件<br/>`last`, `best`, `init`, `auto`
| `--load_evaluate` | `string` | `auto` | 选择作为计算任务的checkpoint文件<br/>`last`, `best`, `init`, `auto`

### Transfer Learning
| 参数名 | 类型 | 默认值 | 作用
| --- | --- | --- | ---
| `--drop_source_layers` | `int` | `0` | *我没看懂*

### Exporting
| 参数名 | 类型 | 默认值 | 作用
| --- | --- | --- | ---
| `--export_dir` | `string` |  | *我没看懂*
| `--remove_export` | `bool` | `False` | 是否移除旧输出模型
| `--export_tflite` | `bool` | `False` | *我没看懂*
| `--n_steps` | `int` | `16` | 多少步生成一次输出图像
| `--export_zip` | `bool` | `False` | *我没看懂*
| `--export_file_name` | `string` | `output_graph` | 输出模型文件名
| `--export_beam_width` | `int` | `500` | 导出到输出图形的默认beam width（ppi？

### Reporting
| 参数名 | 类型 | 默认值 | 作用
| --- | --- | --- | ---
| `--log_level` | `int` | `1` | `0`: debug<br>`1`: info<br>`2`: warn<br>`3`: error
| `--show_progressbar` | `bool` | `True` | 显示过程信息<br>`--log_level`应大于`0`
| `--log_placement` | `bool` | `False` | *我没看懂*
| `--report_count` | `int` | `5` | WER报告中最佳、中间、最差WER的短语数
| `--summary_dir` | `string` |  | TensorBoard summary的目标路径
| `--test_output_file` | `string` |  | 保存在测试时生成的所有loss元组的路径

### Geometry
| 参数名 | 类型 | 默认值 | 作用
| --- | --- | --- | ---
| `--n_hidden` | `int` | `2048` | 初始化所有层时的层宽
| `--layer_norm` | `bool` | `False` | 是否对每个完全连接层后使用层正规

### Initialization
| 参数名 | 类型 | 默认值 | 作用
| --- | --- | --- | ---
| `--random_seed` | `int` | `4568` | 随机种子

### Early Stopping
| 参数名 | 类型 | 默认值 | 作用
| --- | --- | --- | ---
| `--early_stop` | `bool` | `False` | 对验证数据集启用提前停止机制<br>验证过程未开始时不可用
| `--es_epochs` | `int` | `25` | 经过此代数未得到改善的训练将被停止<br>loss不被存储与checkpoint中
| `--es_min_delta` | `float` | `0.05` | 可被认为是改善的最小loss变化<br>亦被用于下节

### Reduce Learning Rate on Plateau
| 参数名 | 类型 | 默认值 | 作用
| --- | --- | --- | ---
| `--reduce_lr_on_plateau` | `bool` | `False` | 在到达高峰时启用降低学习率机制<br>在loss数代没有改善时启用
| `--plateau_epochs` | `int` | `10` | RLROP的启用代数<br>必须小于`--es_epochs`
| `--plateau_reduction` | `float` | `0.1` | 高峰发生时适用于当前学习率的乘法因子
| `--force_initialize_learning_rate` | `bool` | `False` | 对以前降低的学习率强制重新初始化

### Decoder
| 参数名 | 类型 | 默认值 | 作用
| --- | --- | --- | ---
| `--bytes_output_mode` | `bool` | `False` | 启用字节输出模式，模型将直接输出UTF-8字节值而非字母映射<br>`--alphabet_config_path`将被忽略
| `--alphabet_config_path` | `string` | `data/alphabet.txt` | 指定网络使用的字母配置文件路径
| `--scorer_path` | `string` |  | 外部计分器文件路径
| `--beam_width` | `int` | `1024` | 建立候选转录时CTC decoder使用的beam width
| `--lm_alpha` | `float` | `0.931289039105002` | CTC decoder的alpha超参，语言模型权重
| `--lm_beta` | `float` | `1.1834137581510284` | CTC decoder的beta超参，词插入权重
| `--cutoff_prob` | `float` | `1.0` | 到达概率质量之前仅考虑字符<br>`1.0`不启用
| `--cutoff_top_n` | `int` | `300` | 每个时间步仅处理按概率质量排序的此数量的字符<br>大于字母大小时不可用

### Inference Mode
| 参数名 | 类型 | 默认值 | 作用
| --- | --- | --- | ---
| `--one_shot_infer` | `string` |  | 指定一个`.wav`文件，加载checkpoint并执行inference

### Optimizer Mode
| 参数名 | 类型 | 默认值 | 作用
| --- | --- | --- | ---
| `--lm_alpha_max` | `float` | `5.0` | `--lm_alpha`的最大值
| `--lm_beta_max` | `float` | `5.0` | `--lm_beta`的最大值
| `--n_trials` | `int` | `2400` | 超参优化期间运行的试验次数

## 参数说明
* `--feature_cache`
    * **MFCC**：梅尔频率倒谱参数（Mel Frequency Cepstrum Coefficient）