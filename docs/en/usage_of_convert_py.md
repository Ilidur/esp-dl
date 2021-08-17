# Usage of convert.py

The script [convert.py](../../tool/convert.py) quantizes floating-point coefficients in .npy files to C/C++ code in .cpp and .hpp files. It also converts the element order of coefficients to boost operations.

convert.py runs according to config.json, a necessary configuration file for a model. For how to write a config.json file, please refer to [Specification of config.json](./specification_of_config_json.md).

Please note that convert.py requires Python 3.7 or versions higher.

## Argument Description

When you run convert.py, the following arguments should be filled:

| Argument            | Value                                        |
| :------------------ | :------------------------------------------- |
| -t \| --target_chip | esp32 \| esp32s2 \|esp32s3 \| esp32c3        |
| -i \| --input_root  | directory of npy files and config.json         |
| -n \| --name        | name of output files        |
| -o \| --output_root | directory of output files |



## Example

Assume that:

- the relative path of convert.py is **../../tool/convert.py**
- target_chip is **esp32s3**
- npy files and config.json are in directory **./my_input_directory**
- name of output files is **my_coefficient**
- output files will be stored in directory **./my_output_directory**

Execute the following command:

```sh
python ../../tool/convert.py -t esp32s3 -i ./my_input_directory -n my_coefficient -o ./my_output_directory
```

Then, `my_coefficient.cpp` and `my_coefficient.hpp` would be generated in `./my_output_directory`.