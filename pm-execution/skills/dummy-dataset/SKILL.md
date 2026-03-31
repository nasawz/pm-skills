---
name: dummy-dataset
description: "生成用于测试的真实虚拟数据集，支持可自定义列、约束和输出格式（CSV、JSON、SQL、Python 脚本）。适用于创建测试数据、构建模拟数据集或为开发和演示生成示例数据。"
---
# 虚拟数据集生成

生成用于测试的真实虚拟数据集，支持可自定义列、约束和输出格式（CSV、JSON、SQL、Python 脚本）。创建可执行脚本或直接生成数据文件，供立即使用。

**使用场景：** 创建测试数据、生成示例数据集、为开发构建真实的模拟数据，或填充测试环境。

**参数：**
- `$PRODUCT`: 产品或系统名称
- `$DATASET_TYPE`: 数据类型（例如：客户反馈、交易记录、用户档案）
- `$ROWS`: 要生成的行数（默认：100）
- `$COLUMNS`: 要包含的特定列或字段
- `$FORMAT`: 输出格式（CSV、JSON、SQL、Python 脚本）
- `$CONSTRAINTS`: 额外的约束或业务规则

## 分步流程

1. **识别数据集类型** - 了解数据领域
2. **定义列规范** - 列名、数据类型和取值范围
3. **确定行数** - 需要多少样本记录
4. **选择输出格式** - CSV、JSON、SQL INSERT 或 Python 脚本
5. **应用真实模式** - 确保数据看起来真实有效
6. **添加业务约束** - 遵守业务逻辑和关系
7. **生成或编写数据脚本** - 创建可执行输出
8. **验证输出** - 确保数据质量和完整性

## 模板：Python 脚本输出

```python
import csv
import json
from datetime import datetime, timedelta
import random

# Configuration
ROWS = $ROWS
FILENAME = "$DATASET_TYPE.csv"

# Column definitions with realistic value generators
columns = {
    "id": "auto-increment",
    "name": "first_last_name",
    "email": "email",
    "created_at": "timestamp",
    # Add more columns...
}

def generate_dataset():
    """Generate realistic dummy dataset"""
    data = []
    for i in range(1, ROWS + 1):
        record = {
            "id": f"U{i:06d}",
            # Generate values based on column definitions
        }
        data.append(record)
    return data

def save_as_csv(data, filename):
    """Save dataset as CSV"""
    with open(filename, 'w', newline='') as f:
        writer = csv.DictWriter(f, fieldnames=data[0].keys())
        writer.writeheader()
        writer.writerows(data)

if __name__ == "__main__":
    dataset = generate_dataset()
    save_as_csv(dataset, FILENAME)
    print(f"Generated {len(dataset)} records in {FILENAME}")
```

## 示例数据集规范

**数据集类型：** 客户反馈

**列：**
- feedback_id（自增，U001, U002...）
- customer_name（真实姓名）
- email（有效邮箱格式）
- feedback_date（过去 90 天内的日期）
- rating（1-5 星）
- category（Bug、功能请求、投诉、表扬）
- text（真实反馈内容）
- product（电子产品、服装、家居）

**约束：**
- 评分分布：40% 为 5 星，30% 为 4 星，20% 为 3 星，10% 为 1-2 星
- Bug 类别仅与 1-3 星评分关联
- 功能请求仅与 3-5 星评分关联
- 邮箱域名真实（gmail、yahoo、company.com）

## 交付成果

- 可执行的 Python 脚本或直接数据文件
- 带有正确标题和格式的 CSV 文件
- 结构和类型有效的 JSON 文件
- 用于数据库填充的 SQL INSERT 语句
- 数据验证和约束合规性
- 真实、符合业务场景的值
- 数据生成逻辑的文档说明
- 使用数据集的快速入门指南

## 输出格式

**CSV：** 平面表格格式，易于导入电子表格和数据库

**JSON：** 嵌套结构，适用于 API 和 NoSQL 数据库

**SQL：** INSERT 语句，可直接在关系型数据库上执行

**Python 脚本：** 可执行生成器，适用于自定义或大型数据集
