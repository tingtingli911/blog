---
title: 初学ionic
date: 2016-12-05 20:30:33
tags:
	- Angular2	
	- JavaScript
categories: 前端开发	
---

### 1. Ionic2 多语言支持

看了半天的Angular2官方文档，没有搞太明白，主要原因是官方使用的是SystemJs而不是Webpack。经过曲折的经历，终于找到了一个非常适合Ionic2翻译的插件－－ng2-translate。使用起来非常简单，尤其是对于ionic。(附上官方文档链接:http://ionicframework.com/docs/v2/resources/ng2-translate/)

1. 安装ng2-translate：

   `npm install ng2-translate --save`
   
2. 修改/src/app/app.module.ts
   加入以下代码：
   {% codeblock %}
   import {HttpModule, Http} from '@angular/http';
   import { TranslateModule, TranslateStaticLoader, TranslateLoader } from 'ng2-translate/ng2-translate';
   export function createTranslateLoader(http: Http) {
   	return new TranslateStaticLoader(http, 'assets/i18n', '.json');
   }
   {% endcodeblock %}
   更改import部分：
   {% codeblock %}
   @NgModule({
   imports: [
     TranslateModule.forRoot({
      provide: TranslateLoader,
      useFactory: (createTranslateLoader),
      deps: [Http]
      })
   ]
   })
   {% endcodeblock %}

3. 修改/src/app/app.component.ts
{% codeblock %}
import {TranslateService} from 'ng2-translate';
@Component({
  templateUrl: 'app.html'
})
export class MyApp {
  rootPage = HomePage;

  constructor(platform: Platform, translate: TranslateService) {
    platform.ready().then(() => {
      // Okay, so the platform is ready and our plugins are available.
      // Here you can do any higher level native things you might need.
      StatusBar.styleDefault();
      Splashscreen.hide();
    });

    translate.setDefaultLang('cn');
    translate.use('cn');
  }
}
{% endcodeblock %}

4. 使用方法
使用方法很简单，参考{% link 'ng2-translate' 'https://github.com/ocombe/ng2-translate' %}介绍即可
  
  