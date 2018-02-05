# 文件分类操作

<p style='color:red'></p>

> **danger**
> sdk version >= v1.1.2

`let MyFileCategory = new wx.BaaS.FileCategory()`

## 获取文件分类详情

`MyFileCategory.get(categoryID)`

**参数说明**

|    参数     |  类型  | 必填 | 说明 |
| :--------: | :----: | :-: | :-: |
| categoryID | String |  Y  | 文件分类 ID |

**示例代码**

```js
let MyFileCategory = new wx.BaaS.FileCategory()

MyFileCategory.get('5a2fe91508443e3123dbe1cb').then((res) => {
  // success
}, (err) => {
  // err
})
```

**返回示例**
res.data
```js
{
  created_at: 1513089301,
  files: 2,
  id: "5a2fe91508443e3123dbe1cb",
  name: "重要",
  updated_at: 1513089306
}
```
files 为文件分类下的文件数


## 获取分类下的所有文件

`MyFileCategory.getFileList(categoryID)`

**参数说明**

|     参数    |  类型   | 必填 | 参数描述 |
| :-------:  | :-----: | :-: | :-----: |
| categoryID | String  |  Y  | 文件分类 ID |

**示例代码**

```js
let MyFileCategory = new wx.BaaS.FileCategory()

MyFileCategory.getFileList('5a2fe91508443e3123dbe1cb').then((res) => {
  // success
}, (err) => {
  // err
})
```
> **info**
> 如需对分类下的文件进行更多条件的筛选，可使用 [File](./file.md) 的查询接口

## 查询，获取分类列表

文件分类查询与[数据表查询](../schema/query.md)方法一致，但只支持以下指定字段的筛选

| 支持字段 |  类型   | 说明 |
| :-----: | :----: | :-: |
|   id    | String | 文件分类 id |
|  name   | String | 文件分类名 |

**示例代码**

```js
let MyFileCategory = new wx.BaaS.FileCategory()

// 查找所有文件分类
MyFileCategory.find()

// 设置查询条件
let query = new wx.BaaS.Query()
query.contains('name', substr)
File.setQuery(query).find()
```

## 排序
文件分类查询排序与[数据表排序](../schema/limit-and-order.md)方法一致，但只支持对以下指定字段进行排序

| 支持字段    | 描述        |
| :--------- | :--------- |
| name       | 文件名      |
| created_at | 文件创建时间 |

## 分页
文件分类查询排序与[数据表分页](../schema/limit-and-order.md)方法一致