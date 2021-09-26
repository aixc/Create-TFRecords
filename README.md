# Create-TFRecords
Create TFRecords to train TensorFlow models.

The TFRecord format is a simple format for storing a sequence of binary records. Converting your data into TFRecord has many advantages, such as:

- **More efficient storage:** TFRecord data can take up less space than the original data; it can also be partitioned into multiple files.
- **Fast I/O:** TFRecord format can be read with parallel I/O operations, which is useful for TPUs or multiple hosts.
- **Self-contained files:** TFRecord data can be read from a single source — for example, the [COCO2017](https://cocodataset.org/#home) dataset originally stores data in two folders ("images" and "annotations").

An important use case of the TFRecord data format is training on TPUs. First, TPUs are fast enough to benefit from optimized I/O operations. In addition, TPUs require data to be stored remotely (e.g. on Google Cloud Storage) and using the TFRecord format makes it easier to load the data without batch-downloading.

Performance using the TFRecord format can be further improved if you also use it with the tf.data API.
