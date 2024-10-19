环状DNA序列整理

```
#include <iostream>
#include <string>

std::string solution(std::string dna_sequence) {
   int  n = dna_sequence.size();
    std::string s;
    s = dna_sequence;
    std::string t;
    t = dna_sequence;
    for (int i = 0;i < n;i++)
    {
        char r = t[0];
        t = t.substr(1, n - 1);
        
        t = t + r;
        //std::cout << t << ' ';
        if (s.compare(t) > 0)
        {
            s = t;
        }

    }
    //std::cout << s << std::endl;
    return s;
}

int main() {
    // You can add more test cases here
    std::cout << (solution("ATCA") == "AATC") << std::endl;
    std::cout << (solution("CGAGTC") == "AGTCCG") << std::endl;
    std::cout << (solution("TCATGGAGTGCTCCTGGAGGCTGAGTCCATCTCCAGTAG") == "AGGCTGAGTCCATCTCCAGTAGTCATGGAGTGCTCCTGG") << std::endl;
    return 0;
}
```

