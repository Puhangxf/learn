### 设一循环队列Queue,只有头指针front,不设尾指针，另设一个内含元素个数的计数器，试写出相应的入队、出队算法
#### 带头节点


		 public T getLastElement(T x){
			Node<T> q = head;
			Node<T> p = head.next;
			if(x.equals(p.data)){
				System.out.print("为第一个头结点,无前驱元素！");
				return null;
			}
			while(!x.equals(p.data)){
				q = p;
				p = p.next
			 if(p == null){
				System.out.print("不存在！");
				return null;
			 }
			}
			return q.data;
		 }

 
####不带头结点
  public T getLastElement(T x){
	Node<T> q = head;
	Node<T> p = head.next;
	
    while(!x.equals(p.data)){
		q = p;
		p = p.next
	 if(p == null){
		System.out.print("不存在！");
		return null;
	 }
	
	return q.data;
 }
 
### 队列
 class Queue<T>{
	int MaxSize ;
	int front ;
	int count;
	T []array;
	public Queue(int MaxSize){
		this.MaxSize = MaxSize;
		array = (T [])new Object[MaxSize];
		front  = 0;
		count = 0;
	}
	
	public T dequeue(){
		if(count == 0){
			System.out.print("队列为空！");
			return null;
		}
		count--;
		front = (font+1)%MaxSize;
		return array[front];
	}
	
	public void enqueue(T x){
		if(count == MaxSize){
			System.out.print("队列已满！");
			return null;
		}
		count++;
		array[(front+count)MaxSize] = x;
	}

}












