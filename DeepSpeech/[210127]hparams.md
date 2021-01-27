# 参数列表

| 参数名 | 类型 | 默认值 | 作用
| --- | --- | --- | ---
| `--train_files` | `string` |  | 训练集，可用逗号连接多个
| `--dev_files` | `string` |  | 验证集，可用逗号连接多个
| `--test_files` | `string` |  | 测试集，可用逗号连接多个
| `--metrics_files` | `string` |  | 我没看懂
| `--read_buffer` | `string` | `1MB` | 读缓冲区大小
| `--feature_cache` | `string` |  | 将MFCC特征缓存到磁盘以加快相同数据训练速度；<br/>指定从`--train_files`中提取的缓存特征所保存的路径
| `--cache_for_epochs` | `int` | `0` | 特征缓存视为不可用的代数


# 参数说明
* `--feature_cache`
    * **MFCC**：梅尔频率倒谱参数（Mel Frequency Cepstrum Coefficient）