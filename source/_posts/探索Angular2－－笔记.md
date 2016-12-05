---
title: 探索Angular2－－笔记
date: 2016-10-14 15:25:35
tags:
	- Angular2	
	- JavaScript
categories: 前端开发	
---

### 学习笔记

1. 元数据：告诉Angular如何处理一个类，例如"@Component"装饰器后面的类被视作一个组件，传给装饰器的参数（配置项）就是元数据。它是用来指导Angular的行为的。


### 代码规范

1. 所有service都添加@Injectable()


### 实际使用技巧

1. 可选依赖 `@Optional()`
{% codeblock lang:javascript %}
import { Optional } from '@angular/core';

constructor(@Optional() private logger: Logger) {
  if (this.logger) {
    this.logger.log(some_message);
  }
}
{% endcodeblock %}

2. s