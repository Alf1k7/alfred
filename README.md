//Задача на структуру данных
#include <iostream>
#include <vector>
#include <string>
using namespace std;


struct Discipline{// структура дисциплин 
    string name;// название предмета
    int grade;//  Оценка за предмет

};
struct Student{ // структура студентов
    string FIO;//имя студента
    vector<Discipline> Zachetka; //Присваиваем предметы студенту
};

int main()
{
    int n;//Количество студентов
    cout << "Kolvo studentov: ";
    cin >> n;
    vector<Student> students(n);
    for (int i = 0; i < n; i++) {
        cout <<endl<< "Student N = " << i + 1<<endl;
        cout << "FIO: ";
        cin.ignore();//игнорируем n'
        getline(cin, students[i].FIO);
        int n1;
        cout << "Kolvo disciplin: ";
        cin >> n1;
        for (int j = 0; j < n1; j++) {
            Discipline baratrum;
            cout << "Name Dis " << j + 1 << ": ";
            cin.ignore();
            getline(cin, baratrum.name);
            cout << "Grade: ";
            cin >> baratrum.grade;
            students[i].Zachetka.push_back(baratrum);
        }
    }
    int cnt = 0;
    for (int i = 0; i < n; i++) {
        bool is5 = true;
        for (int j = 0; j < students[i].Zachetka.size(); j++) {
            if (students[i].Zachetka[j].grade != 5) {
                is5 = false;
            }
        }
            
        if (is5) {
            cnt += 1;
        }
    
    }
    cout << cnt;
