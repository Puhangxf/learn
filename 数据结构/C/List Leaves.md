### Given a tree, you are supposed to list all the leaves in the order of top down, and left to right.

## Input Specification:
Each input file contains one test case. For each case, the first line gives a positive integer N (≤10) 
which is the total number of nodes in the tree -- and hence the nodes are numbered from 0 to N−1. 
Then N lines follow, each corresponds to a node, and gives the indices of the left and right children
of the node. If the child does not exist, a "-" will be put at the position. Any pair of children are 
separated by a space.

Output Specification:
For each test case, print in one line all the leaves' indices in the order of top down, and left to 
right. There must be exactly one space between any adjacent numbers, and no extra space at the end 
of the line.

## Sample Input:
		8
		1 -
		- -
		0 -
		2 7
		- -
		- -
		5 -
		4 6
## Sample Output:
		4 1 5

#### 代码：
		#include<stdio.h>
		#define Max 10
		#define Null -1

		struct Node{
			int left;
			int right;
		}Tree[Max];
		int Order[Max] = {0};
		//用cnt记录叶子结点的个数
		int cnt = 0;

		int BuildTree(int N){
			char Left,Right;
			int i,check[Max] = {0};

			for(i = 0; i < N ; i++){
				getchar();
				scanf("%c %c",&Left,&Right);
				if(Left!='-'){
					Tree[i].left = Left-'0';
					check[Tree[i].left] = 1;
				}
				else
					Tree[i].left = Null;
					
				if(Right!='-'){
					Tree[i].right = Right - '0';
					check[Tree[i].right] = 1;
				}
				else
					Tree[i].right = Null;
			}
			
			for(i = 0; i < N ; i++){
				if(check[i]!=1)
					break;
			}
			
			return i;
		}

		void traver(int x,int depth){
			if(x == Null)
				return ;
			if(Tree[x].left == Null && Tree[x].right == Null){
				cnt++;
				//顺序是从上到下，左到右，depth为主导(*100),cnt为次要的(*10)
				Order[x] = depth*100 + cnt*10 + x;
			}
			traver(Tree[x].left,depth+1);
			traver(Tree[x].right,depth+1);
		}

		void rever(int x[],int N){
			for(int  i = 0; i < N -1 ;i++){
				int minj = i;
				for(int j = i+1 ; j < N ; j++){
					if(x[minj] > x[j])
						minj = j;
				}
				//交换 
				int swap = x[i];
				x[i] = x[minj];
				x[minj] = swap;
			}
		}

		int main(){
			int N;
			scanf("%d",&N);
			int i = BuildTree(N);
			traver(i,1);
			rever(Order,N);
			for(int i = N-cnt; i< N ; i++){
				if(i > N-cnt)
					printf(" ");
				printf("%d",Order[i]%10);
			} 

			return 0;
		}
		
		
