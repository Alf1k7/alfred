Задача "Плот"

#include <iostream>
#include <string>
#include <vector>
using namespace std;
int main(int argc, char* argv[])
{
	int x1, x2, x, y1, y2, y;
	cin >> x1 >> y1 >> x2 >> y2 >> x >> y;
	if (y < y1) {
		cout << "S"; //если ниже южного борта, то плывем к нему
	}
	else {
		if (y > y2) {
			cout << "N"; //если выше северного борта, то плывем к нему
		}
		//если попадаем в зону между верхним и нижним бортами,
		//то корректировать "высоту" не нужно => ничего не выводим
	}
	if (x < x1) {
		cout << "W"; //если левее западного борта, то плывем к нему
	}
	else {
		if (x > x2) {
			cout << "E"; //если правее восточного борта, то плывем к нему
		}
		//если попадаем в зону между левым и правым бортом,
		//то ничего корректировать не нужно => ничего не выводим
	}
	system("pause"); //останавливаем программу
	return 0;
}
