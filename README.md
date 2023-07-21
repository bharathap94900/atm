#include <iostream>

const int pinPassword{ 12 };

class Client
{
private:
    int m_Withdraw{};
    int m_Deposit{};
    long m_Balance{};
public:
    
    int getDeposit()
    {
        std::cout << "Enter amonunt to depsit :";
        std::cin >> m_Deposit;
        m_Balance += m_Deposit;
        return m_Balance;
    }
    int getWithdraw()
    {
        std::cout << "Enter amont to withdraw :";
        std::cin >> m_Withdraw;
        m_Balance -= m_Withdraw;
        return m_Balance;
    }
   
    void balance()
    {
        std::cout << "Balance is :" << m_Balance << '\n';
    }
   
    
};
int main()
{
    Client cl{};
    std::cout << "Enter pin :";
    int pin{};
    std::cin >> pin;
    while (pin == pinPassword)
    {
        std::cout << "Your successfully logged in" << '\n';
        std::cout << "Select your choice \n";
        int choice{};
        do
        {
            std::cout << "click 1 to deposit \n";
            std::cout << "click 2 to withdraw \n";
            std::cout << "click 3 to check balance \n";
            std::cin >> choice;

            switch (choice)
            {
            case 1:
            {
                 cl.getDeposit() << '\n';
                break;
            }
            case 2:
            {
                cl.getWithdraw() << '\n';
                break;
            }
            case 3:
            {
                cl.balance();
                break;
            }
            default:
                std::cout << "Enter correct number \n";
                break;
            }

        } while (choice > 1 || choice < 3);
    }
    std::cout << "Try again!\n";
    
}
