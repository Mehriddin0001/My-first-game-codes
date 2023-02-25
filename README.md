# My-first-game-codes---> Tic Tac toe
#include <bits/stdc++.h>
using namespace std;
#define fast ios_base::sync_with_stdio(false), cin.tie(NULL);
#define endl '\n'
int n,x;
char mat[3][3] = {'1', '2', '3', '4', '5', '6', '7', '8', '9'};
const char player1 = 'X', player2 = 'O';
string ism1, ism2;
void tanishtiruv(){
	string savol;
	cout << "Tik Tac Toe o'yiniga xush kelibsiz!" << endl << endl;
	cout << "Ushbu o'yinni o'ynagan bo'lsangiz kerak, shartlarni bilsangiz 1 deb yozing, agar bilmasangiz 0 deb yozing va men sizga o'yin qoidalarini tushuntiraman! " << endl;
	while(1){
		cout << "0 yoki 1 kitiring: ";
		cin >> savol;
		if(savol == "1"){
			break;
		}
		else if(savol == "0"){
			cout << "Ushbu o'yinni endi birinchi marta o'ynayotgan bo'lsangiz, men sizga ushbu qoidalarni tushuntirib o'taman:" << endl;
			cout << "	1. Ushbu o'yinni ikki kishlik o'yin bo'lib, birinchi o'yinchi X, ikkinchi o'yinchi esa O harflari yordamidan o'yinni o'ynaydi! va o'yinni X ya'ni birinchi ishtirokchi boshlab beradi!" << endl;
			cout << "	2. O'yinni qanday yutsa bo'ladi? Kimki birinchi bo'lib o'z harfini(x yoki O ni) ustunchasiga qaraganda yoki qator tomonlama yoki diogonal qilib 3 ta bir xil qila olsa yutadi! " << endl;
			cout << "   Misol uchun:" << endl;
			cout << "   1. XOX                    2. XOO                     3. OOX "<< endl;
			cout << "      XOO                       OXX                        XXX "<< endl;
			cout << "      XXO                       XOX                        OXO "<< endl;
			cout << "Bunda 1-sida ustunchasida X yutdi, 2-si diogonal qilib X yutdi, 3-sida esa qatorchasiga qilib X yutdi!" << endl;
			cout << "Manimcha tushunarli bo'ldi, endi o'yinni davom ettirishingiz mumkin!" << endl;
			break;
		}
		else {
			cout << "Siz faqatgina 1 yoki 0 kiritishingiz mumkin! " << endl;
		}
	}
}
void gamers(){
	cout << "Ikkita o'yinchining (X va O) ning ismini kiriting: " << endl;
	cout << "Birinchi o'yinchi(X): "; cin >> ism1;
	cout << "Ikkinchi o'yinchi(O): "; cin >> ism2;
	cout << "O'yinga xush kelibsiz!" << endl;
	
}

void print(){
	cout << "Tic Tac Toe!" << endl;
	for(int i=0; i<3; i++){
		for(int j=0; j<3; j++){
			cout << mat[i][j] << " ";
		}
		cout << endl;
	}
}

void input1(){
	cout << endl << "Belgi qo'ymoqchi bo'lgan o'rinning nomini kiriting(sonlarda): ";
	while(1){
		cin >> n;
		if(n>9 and n<1){
			cout << "Siz faqatgina 1 dan 9 gacha bo'lgan raqamlarni kirita olasiz, qaytadan urunib ko'ring! " << endl;
		}
		else{
			break;
		}
	}
	int s = (n%3!=0 ? n/3 : n/3-1);
	if(mat[s][(n-1)%3] != 'X' and mat[s][(n-1)%3] != 'O' ){
		mat[s][(n-1)%3] = player1;
	}
	else {
		cout << "Iltimos, belgilanmaganlarini tanlang!";
		input1();
	}
}

void input2(){
	cout << endl << "Belgi qo'ymoqchi bo'lgan o'rinning nomini kiriting(sonlarda): ";
	while(1){
		cin >> n;
		if(n>9 and n<1){
			cout << "Siz faqatgina 1 dan 9 gacha bo'lgan raqamlarni kirita olasiz, qaytadan urunib ko'ring! " << endl;
		}
		else{
			break;
		}
	}
	int s = (n%3!=0 ? n/3 : n/3-1);
	if(mat[s][(n-1)%3] != 'X' and mat[s][(n-1)%3] != 'O' ){
		mat[s][(n-1)%3] = player2;
	}
	else {
		cout << "Iltimos, belgilanmaganlarini tanlang!";
		input2();
	}
}

void check() {
	if((mat[0][0] == mat[0][1] and mat[0][0] == mat[0][2] and mat[0][0] == player1) or (mat[1][0] == mat[1][1] and mat[1][0] == mat[1][2] and mat[1][0] == player1) or (mat[2][0] == mat[2][1] and mat[2][0] == mat[2][2] and mat[2][0] == player1) or (mat[0][0] == mat[1][0] and mat[0][0] == mat[2][0] and mat[0][0] == player1) or (mat[0][1] == mat[1][1] and mat[0][1] == mat[2][1] and mat[0][1] == player1) or (mat[0][2] == mat[1][2] and mat[0][2] == mat[2][2] and mat[0][2] == player1) or (mat[0][0] == mat[1][1] and mat[0][0] == mat[2][2] and mat[0][0] == player1) or (mat[0][2] == mat[1][1] and mat[0][2] == mat[2][0] and mat[0][2] == player1))
	{
		print();
		cout << "G'olib "<< ism1 << " -  1-o'yinchi(X)!,   Tabriklaymiz!! " << endl;
		x = 1;
	}
	else if((mat[0][0] == mat[0][1] and mat[0][0] == mat[0][2] and mat[0][0] == player2) or (mat[1][0] == mat[1][1] and mat[1][0] == mat[1][2] and mat[1][0] == player2) or (mat[2][0] == mat[2][1] and mat[2][0] == mat[2][2] and mat[2][0] == player2) or (mat[0][0] == mat[1][0] and mat[0][0] == mat[2][0] and mat[0][0] == player2) or (mat[0][1] == mat[1][1] and mat[0][1] == mat[2][1] and mat[0][1] == player2) or (mat[0][2] == mat[1][2] and mat[0][2] == mat[2][2] and mat[0][2] == player2) or (mat[0][0] == mat[1][1] and mat[0][0] == mat[2][2] and mat[0][0] == player2) or (mat[0][2] == mat[1][1] and mat[0][2] == mat[2][0] and mat[0][2] == player2))
	{
		print();
		cout << "G'olib " << ism2 << " - 2-o'yinchi(O),   Tabriklaymiz!! " << endl;
		x = 1;
	}
	else x = 0;
}

void tenglash(){
	char matt[3][3] = {'1', '2', '3', '4', '5', '6', '7', '8', '9'};
	for(int i=0; i<3; i++){
		for(int j=0; j<3; j++){
			mat[i][j] = matt[i][j];
		}
	}
}
int main(){
	int k=0; 
	string ques,ques2;
	cout << "Assalomu alaykum!" << endl;
	tanishtiruv();
	gamers();
	while(1){
		cout << "O'yinni boshlash uchun start deb yozing, agar xohlamangiz stop deb yozing!" << endl;
		k=0;
		while(1){
			cin >> ques;
			if(ques == "start") break;
			else if(ques == "stop") return 0;
			else cout << "Siz faqatgina start yoki stop buyruqlarini bera olasiz, iltimos, qaytadan uruning!" << endl;
		}
		cout << "- - - - - - - - - - - - - - - - - - - - - - - - - Tic Tac Toe - - - - - - - - - - - - - - - - - - - - - - - -" << endl << endl;
		while(k<9)
		{
			print();
			
			k++;
			if(k%2==1)
			{
				input1();
			}
			else{
				input2();
			}
			check();
			if(x == 1){
				break;
			} 
		}
		if(x == 0){
			print();
			cout << "Durrang!" << endl;
		}
		cout << "O'yin tugadi!"<< endl;
		cout << "Yana o'ynashni xohlaysizmi, agar xohlasangiz ha deb kiriting, xohlamasangiz yo'q deb kiriting: ";
		while(1){
			cin >> ques2; 
			if(ques2 == "ha")
			{
				tenglash();
				break;
			}
			else if(ques2 == "yo'q"){
				cout << "Xayr, salomat bo'ling!" << endl;
				return 0;
			}
			else{
				cout << "Siz faqatgina ha yoki yo'q degan belgilarni kirita olasiz, iltimos, qaytadan urunib ko'ring: ";
			}
		}
	}
	system("pause");
}

