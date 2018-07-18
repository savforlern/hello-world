#include <iostream>
#include <cassert>

class Stack
{
    int m_arrayStack [10] {};//sozdat massiv steca
    int m_lengthArray{0};//dlinna steca

public:

//sbros steca
    void reset()
    {
        m_arrayStack [10] = {};
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
            return true;
        }
    }

//izvlechenie iz steca, esli v stece pusto - assert
    int pop()
    {
        //assert(m_lengthArray == 0);
        return m_arrayStack[m_lengthArray];
    }

    void print()
    {
        std::cout << "(";
        for(int num = 0; num < m_lengthArray; num++ )
            std::cout << " " << m_arrayStack[num];
        std::cout << " )\n";
    }
};

int main()
{
	Stack stack;
//	stack.reset();

	stack.print();

	stack.push(4);
	stack.push(7);
	stack.push(5);
	stack.print();

//	stack.pop();
//	stack.print();

//	stack.pop();
//	stack.pop();
//
//	stack.print();

	return 0;
}
