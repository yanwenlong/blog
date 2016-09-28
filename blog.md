# 博客表

## 管理员表（admin）
字段 | 类型 | 描述 | 其他  
id | int | 主键 | notNull  
email | varchar(50) | 登录邮箱 | unique  
name | varchar(20) | 昵称 | nullable  
password | varchar(100) | 密码 | notNull

## 文章表（article）
字段 | 类型 | 描述 | 其他  
id | int | 主键 | notNull  
title | varchar(255) | 文章标题 | notNull  
keyWords | varchar(255) | 文章关键字 | notNull  
from | varchar(100) | 来源 | default('原创')  
author | varchar(50) | 作者 | notNull  
abstract | varchar(8000) | 文章摘要 | notNull  
content | text | 文章内容 | notNull  
created_at | timestamp | 发布时间 | notNull  
status | tinyint(1) | 状态（0-未发布，1-已发布）| default(0)   
type | tinyint(1) | 分类 | default(0)

## 用户表（user）
字段 | 类型 | 描述 | 其他  
id | int | 主键 | notNull  
email | varchar(50) | 登录邮箱 | unique  
username | varchar(20) | 昵称 | nullable  
password | varchar(100) | 密码 | notNull  
status | tinyint(1) | 状态(0-黑名单，1-白名单) | default(1)

## 评论表（comment）
字段 | 类型 | 描述 | 其他  
id | int | 主键 | notNull  
article_id | int | 文章id | notNull  
user_id | int | 用户id | notNull  
content | text | 内容 | notNull  
created_at | timestamp | 评论时间 | notNull  
parent_id | int | 父类id | default(0)  
 
## 图片（image）
字段 | 类型 | 描述 | 其他  
id | int | 主键 | notNull
image_url | varchar(100) | 图片地址 | notNull
address | int | 图片展示位置 | notNull
status | tinyint | 状态(0-未展示，1-展示) | default(0) 