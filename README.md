#include <iostream>
#include <cassert>

class Stack
{
    int m_stack [10] {};//sozdat massiv steca
    int m_lengthStack = 0;//dlinna steca

public:

//sbros steca
    void reset()
    {
        m_stack [10] = {};
        m_lengthStack = 0;
    }

//esli est mesto, pomestit cislo v stec
    bool push(int value)
    {
        if(m_lengthStack > 9)
            return false;
        else{
            m_stack[m_lengthStack] = value;
            m_lengthStack++;
            return true;
        }
    }

//izvlechenie iz steca, esli v stece pusto - assert
    int pop()
    {
        //assert(m_lengthStack == 0);
        int numOut;
        numOut = m_stack[0];
        if (m_lengthStack == 0){
            m_stack[0] = 0;
            return numOut;
        }
        else{
            for (int i = 0; i < m_lengthStack; i++)
            {
                m_stack[i] = m_stack[i + 1];
            }
            m_stack[m_lengthStack] = 0;
            --m_lengthStack;
            return numOut;
        }
    }

    void print()
    {
        std::cout << "(";
        for(int num = 0; num < m_lengthStack; num++ )
            std::cout << " " << m_stack[num];
        std::cout << " )\n";
    }
};

int main()
{
	Stack stack;
//	stack.reset();

	stack.print();

	stack.push(3);
	stack.push(7);
	stack.push(5);
	stack.print();

	std::cout << "Out stack - " << stack.pop() << '\n' ;
	stack.print();

	std::cout << "Out stack - " << stack.pop() << '\n' ;
	std::cout << "Out stack - " << stack.pop() << '\n' ;

	stack.print();

	return 0;
}
