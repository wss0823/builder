# Bilder
### 介绍
> 以命令行模式生成对应的 `Model,Struct,Service,Logic,Controller`文件




### 使用方法
##### 1 composer.json引入如下包名，更新composer

```bash
"require-dev" : {
        "drcarpen/builder":"^0.4"
    }
```
#####  2 app/Commands 加入新文件 BuilderCommand.php
```bash

<?php
namespace App\Commands;

use Uniondrug\Builder\Commands\Builder;

/**
 * 生成脚手架
 * php console builder --table tableName
 * @package App\Commands
 */
class BuilderCommand extends Builder
{
    protected $authorConfig = [
        'name' => 'yourName',
        'email' => 'yourEmail@uniondrug.cn'
    ];
}

```

##### 3 命令行第三个参数为数据表命，必须依照规范，为下划线定义，如 wx_members

```bash

php console builder --table tableName --e release

```

### 参数说明

1. --table tableName 表名必填，根据此表名生成对应的Model等文件
1. --env     environment 指定的环境变量，可改变database.php中的对应环境的数据库配置

