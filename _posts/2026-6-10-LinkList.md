#LinkListde的结构以及遍历方式

public class SinglylinkList{
private Node head;
}

private static  class Node{
int value;
int next;

public Node(int value,Node next){
this.value=value;
this.next=next;
}
}

public void addFirst(){
//链表为空的时候
head=new Node(value,null);
//链表不为空的时候
head=new Node(value,head);
}
