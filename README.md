# string-steam
#include <sstream>
#include <vector>
#include <iostream>
using namespace std;

vector<int> parseInts(string str) {
	vector<int> v;
    string holder = "";
    for (int i=0; i < sizeof(str); i++){
        if (str[i] == ','){
            v.push_back(stoi(holder));
            holder = "";
        }else{
            holder = holder + str[i];
        }
    }
    v.push_back(stoi(holder));
    return v;
}

int main() {
    string str;
    cin >> str;
    vector<int> integers = parseInts(str);
    for(int i = 0; i < integers.size(); i++) {
        cout << integers[i] << "\n";
    }
    return 0;
		
}
