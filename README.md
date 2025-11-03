```#include <iostream>
#include <iomanip>

using namespace std;

int main() {
    // 定义 4x6 的实型二维数组
    float scores[4][6] = { 0 };
    int i, j;

    // 输入原始成绩数据 (3x5)
    cout << "请输入 3 个学生 5 门课程的成绩：" << endl;
    for (i = 0; i < 3; i++) {
        for (j = 0; j < 5; j++) {
            cin >> scores[i][j];
        }
    }

    // 输出原始成绩数据 (3x5)
    cout << "\n原始成绩数据 (3x5):" << endl;
    for (i = 0; i < 3; i++) {
        for (j = 0; j < 5; j++) {
            cout << fixed << setprecision(1) << scores[i][j] << " ";
        }
        cout << endl;
    }

    // 计算每个学生的平均成绩
    for (i = 0; i < 3; i++) {
        float sum = 0;
        for (j = 0; j < 5; j++) {
            sum += scores[i][j];
        }
        scores[i][5] = sum / 5;
    }

    // 计算单科的成绩总和
    for (j = 0; j < 5; j++) {
        float sum = 0;
        for (i = 0; i < 3; i++) {
            sum += scores[i][j];
        }
        scores[3][j] = sum;
    }

    // 计算第 4 行第 6 列的值
    float total_sum = 0;
    for (i = 0; i < 3; i++) {
        total_sum += scores[i][5];
    }
    scores[3][5] = total_sum;

    // 输出填入结果后的数组 (4x6)
    cout << "\n填入结果后的数组 (4x6):" << endl;
    for (i = 0; i < 4; i++) {
        for (j = 0; j < 6; j++) {
            cout << fixed << setprecision(1) << scores[i][j] << " ";
        }
        cout << endl;
    }

    // 计算单科平均成绩
    cout << "\n单科平均成绩:" << endl;
    for (j = 0; j < 5; j++) {
        float avg = scores[3][j] / 3;
        cout << fixed << setprecision(4) << avg << " ";
    }
    cout << endl;

    return 0;
}```
