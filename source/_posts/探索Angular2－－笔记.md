---
title: 探索Angular2－－笔记
date: 2016-10-14 15:25:35
tags:
	- Angular2	
	- JavaScript
categories: 前端开发	
---

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

2. sdf