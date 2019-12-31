## Instruction
```
npm install 
npm install hexo-deployer-git --save // To support git deployment
```
To add latex support:
```
npm uninstall hexo-renderer-marked --save
npm install hexo-renderer-kramed --save
```
To support inline math equations, find `node_modules\kramed\lib\rules\inline.j` and modify the line 11 and 20 of it:
```
//change the line 11
//escape: /^\\([\\`*{}\[\]()#$+\-.!_>])/,
//into
escape: /^\\([`*\[\]()#$+\-.!_>])/,

//change the line 20
//em: /^\b_((?:__|[\s\S])+?)_\b|^\*((?:\*\*|[\s\S])+?)\*(?!\*)/,
//into
em: /^\*((?:\*\*|[\s\S])+?)\*(?!\*)/,
```
Find the _config.yaml file of theme `Next'
and enable the math function:
```
# Math Equations Render Support
math:
  enable: true
```
When you are going to write a new post, add the math suport declaration in the front-matter
```
---
title: index.html
date: 2018-07-05 12:01:30
tags:
mathjax: true
--
```
## Reference
- [SaltyFish's Blog: hexo latex](https://dragon-liu.github.io/2019/04/26/blog6/)


