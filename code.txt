#include <iostream>
#include <stdlib.h>
#include <time.h>
#include <locale.h>
#include <Windows.h>
int main()
{
	SetConsoleCP(1251);
	SetConsoleOutputCP(1251);
	int arr[10] = { 1, 2, 5, 6, 8, 9, 10, 3, -77, 0 }, min = arr[0], max = arr[0];
	setlocale(LC_ALL, "Rus");

	srand(time(NULL));
	for (int i = 0; i < 10; i++)
	{
		arr[i] = rand()%10;
		
		for (int i = 1; i < 10; i++)
		{
			if (min > arr[i])
				min = arr[i];
			else if (max < arr[i])
				max = arr[i];
		}

			
	}
	std::cout << "Макс и минимум" << " " << max << " " << min << " " << "\n";
	std::cout << "Выводим разницу" << " " << max - min << " " << "\n";
	system("pause");
	
	int num; // размер массива
	srand(time(NULL));
	std::cout << "Задание 3, Введите значение:" << "\n";
	std::cin >> num; // получение от пользователя размера массива

	int* arr1 = new int[num]; // Выделение памяти для массива
	for (int i = 0; i < num; i++) {
		// Заполнение массива и вывод значений его элементов
		arr1[i] = rand();
		std::cout << " " << arr1[i] << "\n";
	}
	delete[] arr1; // очистка памяти

	system("pause");
	std::cout << "Задание 4" << "\n";
	int arr2[5][5] = {}, sum = 0;
	srand(time(NULL));
	for (int i = 0; i < 5; i++) {
		int count = 0;
		for (int j = 0; j < 5; j++) {
			arr2[i][j] = rand()%100 - (rand() % 100)+20;
			count += 1;
			std::cout << arr2[i][j] << " ";
			if (count == 5) {
				std::cout << "\n";
			}
			sum = arr2[i][j] + sum;
		}
		std::cout << sum << " " << "\n";
		sum = 0;
	}
	system("pause");

   

    char choice1[20], choice2[20];

    struct student
    {
        char famil[20], name[20], facult[20];
        int nomzach;
    } stud[3];

    std::cout << "Поиск в структуре по двум параметрам" << std::endl << std::endl;

    std::cout << "Ввод данных" << std::endl;
    for (int i = 0; i < 3; i++)
    {
        std::cout << "----------------------------" << std::endl;
        std::cout << "Фамилия " << i + 1 << "-го студента: ";
        std::cin >> stud[i].famil;
        std::cout << "Имя " << i + 1 << "-го студента: ";
        std::cin >> stud[i].name;
        std::cout << "Факультет " << i + 1 << "-го студента: ";
        std::cin >> stud[i].facult;
        std::cout << "Номер зачетной книжки " << i + 1 << "-го студента: ";
        std::cin >> stud[i].nomzach;
    }

    std::cout << "----------------------------" << std::endl;
    std::cout << "Ввод параметров для поиска (фамилия, имя, факультет)" << "\n";
    std::cout << "Параметр 1: ";
    std::cin >> choice1;
    std::cout << "Параметр 2: ";
    std::cin >> choice2;
    std::cout << "----------------------------" << std::endl;

    std::cout << "Результаты поиска" << std::endl;;

    for (int i = 0; i < 3; i++)
    {
        if ((strcmp(choice1, stud[i].famil) == 0 and strcmp(choice2, stud[i].facult) == 0)
            or (strcmp(choice1, stud[i].facult) == 0 and strcmp(choice2, stud[i].famil) == 0)
            or (strcmp(choice1, stud[i].famil) == 0 and strcmp(choice2, stud[i].name) == 0)
            or (strcmp(choice1, stud[i].name) == 0 and strcmp(choice2, stud[i].famil) == 0)
            or (strcmp(choice1, stud[i].name) == 0 and strcmp(choice2, stud[i].facult) == 0)
            or (strcmp(choice1, stud[i].facult) == 0 and strcmp(choice2, stud[i].name) == 0))
        {
            std::cout << "----------------------------" << std::endl;
            std::cout << "Фамилия: " << stud[i].famil << std::endl;
            std::cout << "Имя: " << stud[i].name << std::endl;
            std::cout << "Факультет: " << stud[i].facult << std::endl;
            std::cout << "Номер зачетной книжки: " << stud[i].nomzach << std::endl;
        }
    }
	
}