#include <iostream>

class Stack
{
    int m_arrayStack [10];//sozdat massiv steca
    int m_lengthArray;//dlinna steca
    
public:
  
//sbros steca  
    void reset()
    {
        m_arrayStack {};
        m_lengthArray = 0;
    }
    
//esli est mesto, pomestit cislo v stec
    bool push(int value)
    {
        if(m_lengthArray > 9)
            return false;
        else{
            m_arrayStack[m_lengthArray] = value;
            m_lengthArray++;
        }
    }
    
//izvlechenie iz steca, esli v stece pusto - assert
    int pop()
    {
        if(m_lengthArray == 0){
            
        }
    }
    
};
