f = forg = http:github.com/badlands2  
fm = f:master

c = cm = 内网：github/badlands2
cm = c：master
cl = c: lifeversion

l = local = 本地文件：badlands
lm = l： maseter
ll = l: lifeversion
lp[x] = l： pbqversion[x]

1.f有更新需要打版本合并：l断开指向c的，连接到指向f的；然后pull更新；然后断开f连接到c；然后push到cm或者cl
2.新功能开发：单一无冲突在ll上开发,有多个任务，有不同的时间点检查点的情况下，建立lp[x]分支来做；最后做完了，合并到ll上，然后push ll 到cl
3. 打版本的时候记得来个tag然后在tag上去打版本
