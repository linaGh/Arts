## Algorithm
删除链表中等于给定值 val 的所有节点。
示例:
输入: 1->2->6->3->4->5->6, val = 6
输出: 1->2->3->4->5

```/**
 * Definition for singly-linked list.
 * public class ListNode {
 *     int val;
 *     ListNode next;
 *     ListNode(int x) { val = x; }
 * }
 */
class Solution {
    public ListNode removeElements(ListNode head, int val) {
        // Write your code here
        ListNode first=new ListNode(-1);
        first.next=head;
        ListNode pre=first;
        ListNode p=head;
        while(p!=null){
            if(p.val==val){
                pre.next=p.next;
                p=p.next;
            }else{
                p=p.next;
                pre=pre.next;
            }
        }
        return first.next;  
    }

}
```
### 
## Review 
AntiPattern: https://martinfowler.com/bliki/AntiPattern.html  
![AntiPattern](https://martinfowler.com/bliki/images/antipattern/antipattern.png "AntiPattern")

When writing a description of an antipattern it's valuable to describe how to get out of trouble if you've taken the bad path. 

**It's useful to remember that the same solution can be a good pattern in some contexts and an antipattern in others. The value of a solution depends on the context that you use it.**
耗子叔提到的大神:
Martin Fowler ，他的经典书有《重构》、《分析模式》、《企业应用架构模式》、领域特定语言》和《NoSQL 精粹》等

### 
## Tip
关于日志打印:  

log.log(Leavel.FINE. "I am here, and the value of X is" + calX() + " and Y is" + calY());  
这里包含了看起来不必要的字符串连接. 因为除了日志级别特别高, 否则这里的日志不会打印出来, 那也就没有必要调calX()了. **下面这样的代码会更好**  
  ```
  if(log.isLoggable(Leavel.FINE)) {  
      log.log(Level.FINE,  
              "I am here, ang the value of X is {} and Y is {}",  
              new Object[](calX(), calY()))  
  };  
  ``` 
  *除非启用日志, 否则就可以避免字符串连接的同时, 避免方法调用或者对象分配.  
  这是编码习惯的选择, 不属于应该避免的过早优化.*

## Share 

7 Things to Start Being More Productive, Today  
做的更多、时间更长,不是长久之计, 或许只是通往成功的路  
有时, 工作少也能作出不错的成绩  
成功的方法不是努力工作, 而是有方法的工作.  

*作者列出了7件事帮助他做的更少, 产出更多.(事半功倍)*

- 1、**停止通过超时工作来代替增加产出**  
  Henry Ford, 福特汽车尝试人, 首先尝试用5*8=40h的工作制,和之前的6*10=60h来比, 员工的生产力增加了.
  “losing just one hour of sleep per night for a week will cause a level of cognitive degradation equivalent to a .10 blood alcohol level.”
  It’s important for us not to overwork ourselves and get enough sleep to maintain a high level of productivity. Next time you’re wondering why you may not be working productively, the reason may be simple as you being deprived of adequate sleep. 
  (每天的小憩很重要!!!)
- 2、**不要经常说“yes”, 学会拒绝**    
the Pareto principle: 2/8理论
研究证明, 说“I dont't”比“I can't”更有效果一些
下次想要避免说“yes“时, 试着说“I don't”
比如想要减少在社交媒体的时间, 删掉手机和电脑上那些诱惑人的app, 增加访问的难度, 这样你就可以更少的使用它,还有戒掉零食哦
- 3、**停止所有的事情都亲力亲为, 试着请别人帮助你**  
一个简单例子, 用户比做营销的更懂他需要什么
- 4、**停止做一个完美主义的人**  
越追求完美, 产出越少(会导致拖延, 一定程度上来说, 可能会错过商机)
The perfect moment is NOW.
越追求完美, 产出越少(会导致拖延, 一定程度上来说, 可能会错过商机)
- 5、**停止做重复性工作, 尝试自动化**  
- 6、**停止猜测, 开始备份你由数据做出的决定**  
这里说的是要优化你的生活方式去成长, 以挖掘你的最大潜力.
比如人在下午12:00到14:00时很容易分神, 所以不适合做脑力强度大的工作
- 7、**停止工作, 留些时间什么也不做**  
在我们过度集中于一些事情的时候, 很可能适得其反, 或者偏离我们工作的目标, 工作一段时间休息一下对我们的大脑和身心都是有益的
在哈佛正在进行的一项研究表明人们对独处时做的事情记忆力更强, 另一个研究表明, 适当的独处可以增强一个人的同理心, 但是我们都知道, 在生活中有太多的隐私是不健康的, 一定程度的隐私可以帮助保持好心情和提高分数

**作者赠言:** 
It‘s important to take time for reflection. We often find the solutions we’re looking for when we’re not actively searching for them.

It’s also important to understand that we don’t become more productive overnight. Like everything in life, it requires effort and practice. Change doesn’t happen just by sitting around and waiting for it. Instead, take the time to learn more about your body and find actionable ways to optimize your energy and time for a more successful and happier life.
You can use the [editor on GitHub](https://github.com/linaGh/Arts/edit/master/README.md) to maintain and preview the content for your website in Markdown files.

原文链接:https://medium.com/s/story/7-things-you-need-to-stop-doing-to-be-more-productive-backed-by-science-a988c17383a6  
