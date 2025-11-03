```
#include <iostream>
#include <vector>
using namespace std;

int main() {
    int n;
    cout << "请输入数组元素个数 n: ";
    if (!(cin >> n) || n <= 0) {
        cout << "输入不合法\n";
        return 0;
    }

    vector<int> a(n);
    cout << "请输入 " << n << " 个整数:\n";
    for (int i = 0; i < n; ++i) cin >> a[i];

    int maxVal = a[0], minVal = a[0];
    int maxIdx = 0, minIdx = 0;
    for (int i = 1; i < n; ++i) {
        if (a[i] > maxVal) { maxVal = a[i]; maxIdx = i; }
        if (a[i] < minVal) { minVal = a[i]; minIdx = i; }
    }

    cout << "原始数组元素为: ";
    for (int i = 0; i < n; ++i) cout << a[i] << (i + 1 == n ? '\n' : ' ');

    cout << "最大值: " << maxVal << "，位置(下标): " << maxIdx << '\n';
    cout << "最小值: " << minVal << "，位置(下标): " << minIdx << '\n';
    return 0;
}
```
