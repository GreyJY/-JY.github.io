#LinkListde的结构以及遍历方式

public class SinglylinkList{
private Node head;

//static静态内部类相当于于把Node这个类变成外部类的内部类，这样这个内部类里面的其他类就用再多一个.访问进来创建对象少一层(加不加static就决定用不用创建对象来访问,有static就不用创建对象)
private static  class Node{
int value;
int next;
//一般这种只含this或者大量this方法的函数都用来存储数据这里的Node类相当于一个小盒子节点value是数据，next指针指向下一个节点的value(next指针存储下个节点的数据的地址)
public Node(int value,Node next){
this.value=value;
this.next=next;
}
}

//存储数据一个节点里面有value有next
public void addFirst(int value){
//链表为空的时候
head=new Node(value,null);
//链表不为空的时候
head=new Node(value,head);
}

public void addFirst(node newNode){
newNode.next=head;
head=newNode;

}
//下面是遍历方式
//第一种方式
public void loop1(){
Node p=head;
//这种while的逻辑方式就单纯看到p不等于空的时候就遍历
while(p!=null){
System.out.println(p.value);
p=p.next

}
}

//第二钟方式
public void loop2(Consumer<Integer>consumer){
//偏逻辑的遍历方式跟int的遍历是两种风格
for(Node p=head;p!=null;p=p.next){
consumer.accept(p.value)
}
}
}


public calss TestSinglyLinkedList{
//这个注释可以在没有main方法的情况下让编译器运行代码
@Text
SinglyLinkedList list=new SinglyLinkedList():
list.addFirst(1);
list.addFirst(2);
list.loop1(value->{
System.out.println(value);
})

}
