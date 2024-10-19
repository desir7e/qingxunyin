```c++
int solution(int xPosition, int yPosition) {
    // Please write your code here
    long d=abs(xPosition-yPosition);
    long tmp=0;
    long i=1;
    long flag=1;
    while(d>tmp){
        tmp+=i;
//        printf("flag%d  tmp%d    ",flag,tmp); 
        if(d<=tmp) break;
        flag++;        
        tmp+=i;
//        printf("flag%d  tmp%d    ",flag,tmp); 
        if(d<=tmp) break;
        flag++;
        i++;
    }
    return flag;
}

int main() {
    //  You can add more test cases here
    std::cout << (solution(12, 6) == 4) << std::endl;
    std::cout << (solution(34, 45) == 6) << std::endl;
    std::cout << (solution(50, 30) == 8) << std::endl;
    return 0;
}
```

