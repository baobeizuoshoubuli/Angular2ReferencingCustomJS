# Angular2ReferencingCustomJS
Angular references the JS file demo
TypeScript/Angular2调用原生JS的桥接文件 示例。

1、首先准备好.js 文件 （app.component.js）
2、生成TypeScript 与 javascript的桥接文件 xxx.d.ts （app.component.d.ts） 方法：
    （1）快速生成桥接文件
	     将你要生成桥接文件的.js文件修改后缀名为.ts。因为TypeScript是JavaScript的超集，所以JavaScript代码完全可以在TypeScript的文件中执行（就像C++的文件能够跑C语言一样）。
         首先确保你的电脑上已经安装了TypeScript，打开“终端”（Windows下是命令行），cd到你刚刚修改后缀名的文件所在的文件夹，运行命令：
             tsc --declaration 刚刚修改后缀名的文件名（包括后缀名）。
         例如：
             tsc --declaration myJavaScript.ts
	 （2）手动编写桥接文件 略
3、在需要调用js方法的.ts 中  第一行引入 .d.ts文件
     例如： ///<reference path="app.component.d.ts" />
4、项目中引入javascript文件
   在 angular-cli.json 文件中 scripts 中加入自己定义好的js文件  
   例如：   "scripts": ["./app/app.component.js"]
5、在tsconfig.json 中引入 桥接文件 xxx.d.ts
   例如 
   "types":[ 
      "src/app/app.component.d.ts" 
    ],
	
6、ng build 、     ng serve    启动网站
 
 
