=====================
c++ thread library
=====================

thread basic
============


.. code-block:: c++
    :linenos:

    #include <iostream>
    #include <trhead>
    #include <chrono>
    bool isStoped = false;
    void thread1Task(int delayms)
    {
        while(!isStoped)
        {
            std::cout<<"hello,world\n";
            std::this_thread.sleepfor(std::chrono::milliseconds(delayms));
        }
    }
    int main()
    {
        std::thread thread1(thread1Task, 100);
        return 0;   
    }


timing in c++
=============

.. code-block:: c++
    :linenos:

    #include <iostream>
    #include <thread>
    #include <chrono>

    struct Timer {
        std::chrono::high_resolution_clock::time_point start;
        std::chrono::high_resolution_clock::time_point end;
        std::chrono::duration<float> duration;
        Timer() {
            start = std::chrono::high_resolution_clock::now();
        }
        ~Timer() {
            end = std::chrono::high_resolution_clock::now();
            duration = end - start;
            std::cout << "elapsed " << duration.count() * 1000 << "ms\n";
        }
    };
    int main()
    {
        Timer timer;
        std::this_thread::sleep_for(std::chrono::milliseconds(400));
        return 0;   
    }

table
=======================

.. csv-table:: 
    :header: 序号,mcu引脚,引脚名称,引脚功能
    :align: center
    :widths: 1 2 4 6

    1, PA10, USART1_TX, 串口1发送
    2, PA9, USART1_RX, 串口1接收 
