//Queue using Linked list
//SOURCE CODE
import java.io.*;
import java.util.*;
public class Solution{
    public static void main(String[] args){
        Scanner sc=new Scanner (System.in);
        Queueusingll q=new Queueusingll();
        int n=sc.nextInt();
        for (int i=0;i<n;i++){
            int query=sc.nextInt();
            if(query==1){
                int val=sc.nextInt();
                q.enqueue(val);
            }
            else if(query==2){
                System.out.println(q.dequeue());
            }
            else if(query==3){
                System.out.println(q.front());
            }
            else if(query==4){
                System.out.println(q.len());
            }
            else if(query==5){
                System.out.println(q.isEmpty());
            }
        }
    }
}
class Queueusingll{
    Node head,tail;
    int len=0;
    Queueusingll(){
      head=null;
      tail=null;
    }
        class Node{
            int data;
            Node next;
            Node(int val){
            data=val;
            next=null;
        }  
    }
    public void enqueue(int val){
        Node n=new Node(val);
        if(head==null){
            head=n;
            tail=n;
            len++;
        }
        else{
        tail.next=n;
        tail=n;
        len++;
        }
    }
    public int dequeue(){
        if(len>0){
          int temp=head.data;
          head=head.next;
          len--;
          return temp;
        }
        else{
            return -1;
        }
    }
    public int front(){
        return head.data;
    }
    public int len(){
        return len;
    }
    public boolean isEmpty(){
        return head==null;
    }
}
