#include<iostream>
#include<fstream>
#include<conio.h>
#include<ctime>
#include<windows.h>
using namespace std;
float spend;
float bud;
float lmoney;
time_t now = time(0);
static char* dt = ctime(&now);
int l = strlen(dt);

void newf();
float income();
void intro();
void review();
void next();
bool flag=0;
inline void back()
{
	cout<<"\npress b to back";
	char ch=getch();
	if(ch=='b'||ch=='B')
	intro();
}
class expense {
public:
    float ifood(float a);
    float icloth(float a);
    float iliving(float a);
    float itrans(float a);
    float ieduc(float a);
    float imed(float a);
};

expense e;
float cloth()
{  float b, c = 0;
    ifstream file("cloth.txt");
    if (file.is_open()) {
        while (file >> b) {
            c += b;
        }
        file.close();
    }
    return c;
}
float med()
{    float b, c = 0;
    ifstream file("med.txt");
    if (file.is_open()) {
        while (file >> b) {
            c += b;
        }
        file.close();
    }
    return c;
}
float trans()
{ float b, c = 0;
    ifstream file("trans.txt");
    if (file.is_open()) {
        while (file >> b) {
            c += b;
        }
        file.close();
    }
    return c;
}
float food() {
    float b, c = 0;
    ifstream file("food.txt");

    if (!file.is_open())
        return c;

    while (file >> b) {
        c += b;
    }

    return c;
}
float educ()
{ float b, c = 0;
    ifstream file("living.txt");
    if (file.is_open()) {
        while (file >> b) {
            c += b;
        }
        file.close();
    }
    return c;
}
float liv()
{  float b, c = 0;
    ifstream file("living.txt");
    if (file.is_open()) {
        while (file >> b) {
            c += b;
        }
        file.close();
    }
    return c;
}
float expense::icloth(float a)
{
 float b;
    system("CLS");
    std::cout << "\t\t\tIN Clothing\n";
    std::cout << "Transaction  \t\tMoney left\n" << lmoney;
    
    std::fstream data("cloth1.txt", ios::in | ios::app);
    data << dt << "  " << a << "\n";
    data.close();
    data.open("clothing1.txt", ios::in);

    std::string str;
    while (getline(data, str)) {
        std::cout << str << std::endl;
    }
    data.close();

    std::fstream file("cloth.txt");
    file << a << " ";
    file.close();

    file >> b;  // Assuming 'med.txt' contains only one value per line

    float c = 0;
    while (file) {
    c += b;   
    file >> b;
}
    std::cout << "Total\t\t\t  " << c;
    file.close();

    std::ofstream kp("bidget.txt");
    kp << lmoney;
    kp.close();

    back();
    return c;}
float expense::itrans(float a)
{
	

 float b;
    system("CLS");
    std::cout << "\t\t\tIN transportation\n";
    std::cout << "Transaction  \t\tMoney left\n" << lmoney;
    
    std::fstream data("trans1.txt", ios::in | ios::app);
    data << dt << "  " << a << "\n";
    data.close();
    data.open("trans1.txt", ios::in);

    std::string str;
    while (getline(data, str)) {
        std::cout << str << std::endl;
    }
    data.close();

    std::fstream file("trans.txt");
    file << a << " ";
    file.close();

    file >> b;  // Assuming 'med.txt' contains only one value per line

    float c = 0;
    while (file) {
    c += b;   
    file >> b;
}
    std::cout << "Total\t\t\t  " << c;
    file.close();

    std::ofstream kp("bidget.txt");
    kp << lmoney;
    kp.close();

    back();
    return c;}
float expense::ifood(float a)
{
 float b;
    system("CLS");
    std::cout << "\t\t\tIN FOOD\n";
    std::cout << "Transaction  \t\tMoney left\n" << lmoney;
    
    std::fstream data("FOOD1.txt", ios::in | ios::app);
    data << dt << "  " << a << "\n";
    data.close();
    data.open("med1.txt", ios::in);

    std::string str;
    while (getline(data, str)) {
        std::cout << str << std::endl;
    }
    data.close();

    std::fstream file("food.txt");
    file << a << " ";
    file.close();

    file >> b;  // Assuming 'med.txt' contains only one value per line

    float c = 0;
    while (file) {
    c += b;   
    file >> b;
}
    std::cout << "Total\t\t\t  " << c;
    file.close();

    std::ofstream kp("bidget.txt");
    kp << lmoney;
    kp.close();

    back();
    return c;
}
float expense::ieduc(float a)
{
	//	lmoney=bud-(food()+cloth()+liv()+trans()+educ()+med());

 float b;
    system("CLS");
    std::cout << "\t\t\t IN EDUCATION\n";
    std::cout << "Transaction  \t\tMoney left\n" << lmoney;
    
    std::fstream data("educ1.txt", ios::in | ios::app);
    data << dt << "  " << a << "\n";
    data.close();
    data.open("educ1.txt", ios::in);

    std::string str;
    while (getline(data, str)) {
        std::cout << str << std::endl;
    }
    data.close();

    std::fstream file("educ.txt");
    file << a << " ";
    file.close();

    file >> b;  // Assuming 'med.txt' contains only one value per line

    float c = 0;
    while (file) {
    c += b;   
    file >> b;
}
    std::cout << "Total\t\t\t  " << c;
    file.close();
    std::ofstream kp("bidget.txt");
    kp << lmoney;
    kp.close();

    back();
    return c;
}
float expense::imed(float a) {
    float b;
    system("CLS");
    std::cout << "\t\t\tIN MEDICAL\n";
    std::cout << "Transaction  \t\tMoney left\n" << lmoney;
    
    std::fstream data("med1.txt", ios::in | ios::app);
    data << dt << "  " << a << "\n";
    data.close();
    data.open("med1.txt", ios::in);

    std::string str;
    while (getline(data, str)) {
        std::cout << str << std::endl;
    }
    data.close();

    std::fstream file("med.txt");
    file << a << " ";
    file.close();

    file >> b;  // Assuming 'med.txt' contains only one value per line

    float c = 0;
    while (file) {
    c += b;   
    file >> b;
}
    std::cout << "Total\t\t\t  " << c;
    file.close();

    std::ofstream kp("bidget.txt");
    kp << lmoney;
    kp.close();

    back();
    return c;
}


float expense::iliving(float a)
{	//lmoney=bud-(food()+cloth()+liv()+trans()+educ()+med());

float b;
	system("CLS");
	cout<<"\t\t\t IN livingICAL\n";
	cout<<"transaction  \t\tmoney left\n"<<lmoney;
//char *ch={"med1.txt"};
    fstream data("living.txt",ios::in|ios::app);
 data<<dt<<"  "<<a<<"\n";
 data.close(); 
 data.open("living.txt",ios::in);
 char str[40];
 while(!data.eof())
 {
 data.getline(str,40);
 cout<<str<<endl;
 }
  data.close();
    FILE *fp;
	fp=fopen("liv.txt","a");
	fprintf(fp,"%f ", a); 
	fclose(fp);
	fp=fopen("liv.txt","r");
    float c=0;
		while(!feof(fp))
	{
		fscanf(fp,"%f ", &b);
	   // printf("%f + ",b);
		c=c+b;
	}
	cout<<"total\t\t\t  "<<c;
	fclose(fp);
		FILE *kp;
     kp=fopen("bidget.txt","w");
	fprintf(kp,"%f ", lmoney); 
	fclose(kp);;
	back();
	return c;}
	int main(void );
	void intro()
	{

		 system("CLS");
		 cout<<dt<<endl;
		
	label:	cout<<"Money spend in\t\tmoney left:"<<lmoney;
	
         cout<<"\n1.)food\n2.)cloth\n3.)living\n4.)tranportion\n5.)education\n6.)medical \npress b to back";
         char ch=getch();
         switch (ch)
           {
         	 case '1':{
         	 y:cout<<"\n Enter the amount:";
			  cin>>spend;
			   if(spend>lmoney||spend<0)
			  {
			  	cout<<"wrong input";
			  	goto y;
			  }
			  lmoney-=spend;	
              e.ifood(spend);
             break;}
             case '2':{
			
             	cout<<"\n Enter the amount:";
			 x: cin>>spend; if(spend>lmoney||spend<0)
			  {
			  	cout<<"wrong input";
			  	goto x;
			  }
			   lmoney-=spend;
             e.icloth(spend);
             break;}
             case '3':{
             c:	cout<<"\n Enter the amount:";
			  cin>>spend;
			  if(spend>lmoney||spend<0)
			  {
			  	cout<<"wrong input";
			  	goto c;
			  }
			   lmoney-=spend;
             e.iliving(spend);
             break;}
             case'4':{
				
			 
             d:	cout<<"\n Enter the amount:";
			  cin>>spend;
			   if(spend>lmoney||spend<0)
			  {
			  	cout<<"wrong input";
			  	goto d;
			  }else{
			  
			   lmoney-=spend;
             e.itrans(spend);}
         }
             break;
             case'5':{
			e:	cout<<"\n Enter the amount:";
			  cin>>spend; 
			  if(spend>lmoney||spend<0)
			  {
			  	cout<<"wrong input";
			  	goto e;
			  }else{
			  
			  
			   lmoney-=spend;
             e.ieduc(spend);}
             break;}
             case '6':{
			
			 
             f:	cout<<"\n Enter the amount:";
			  cin>>spend; 
			  if(spend>lmoney||spend<0)
			  {
			  	cout<<"wrong input";
			  	goto f;
			  }
			   lmoney-=spend;
             e.imed(spend);
             
             break;}
             case 'b':
		 next();	
             default :
             	system("cls");
             cout<<"wrong key\n";
             goto label;
             break;
             
    
			}
	   }	 
void review()
{
	system("cls");
	cout<<"\nfood\tcloth\tliving\ttransportation\teduc\tmedical\tmoney left in budget\n";

    cout<<food()<<"\t  "<<cloth()<<"\t"<<liv()<<"\t         "<<trans()<<"\t"<<educ()<<"\t"<<med()<<"   \t"<<lmoney;
    
    cout<<"\npress b to back";
    
    char ch=getch();
    if(ch=='b'||ch=='B')
    next();
}
void next()
{	
     system("CLS");
	 xyz:	cout<<"1.)Money review\n2.)Spend amount\n3.)change in budget\n ";
	 	char k=getch();
	  if(k=='1')
		 review();
		 else if(k=='2') 
	 	intro();
	 	else if
		 (k=='3')
	 	income();

//boost::filesystem::remove_all(p);;
	 	else
	 	system("cls");
	 	cout<<"wrong key\n";
	 	goto xyz;
	 	
	 	
}

float income(){
	label:cout<<"\n1.)Subtract money\n2.)Add more money\t\t\t\t Money left: "<<lmoney<<endl;
     int a;
     
     char ch=getch();
     switch(ch)
     {
     case '1':
	 {
	 	x:cout<<"\nEnter  amount";
	 	cin>>a;
	 	if(a<0){
		 cout<<"\nwrong input";
	 	goto x;}
	 	else if (a>lmoney)
	 	{cout<<"Your subtracted amount should be less than the budget";
	 	goto x; }
	 else
	 lmoney-=a;
	 	break;
		 }	
	 
	 case '2':
	 	{
	 	y:cout<<"\nEnter AMOUNT amount";
	 	cin>>a;
	 	if(a<0){
		 cout<<"\nwrong input";
	 	goto y;}
	 	else
	 	lmoney=lmoney+a;
	 	break;
		 }	
		 default :
             	system("cls");
             cout<<"wrong key\n";
             goto label;
             break;
	 }
	 cout<<"\nnew bud:"<<lmoney;
	 Sleep(1500);
     FILE *fp;
     fp=fopen("bidget.txt","w");
	fprintf(fp,"%f ", lmoney); 
	fclose(fp);
     next();
     	}
void newf()
{
	cout<<"\nEnter your budget:";
	cin>>lmoney;
	
	FILE *fp;
     fp=fopen("bidget.txt","w");
	fprintf(fp,"%f ",lmoney); 
	fclose(fp);
    next();
	
		 }    	

int main() 

{
	 system("cls");
	 dt[--l]={' '};   //cout<<date;
	 char title[]="\t\t\t\t**************\n\t\t\t\tBUDGET TRACKER\n\t\t\t\t**************";
	 char *ptr=&title[0];
	 for(int i=0;i<sizeof(title);i++)
	      {   cout << *(ptr+i);    Sleep(40);  } 
	 
	 cout<<"\n\t\t\t     press space  to continue";
	 getch();
	 FILE *fp;
	 cloth();
	 
fp=fopen("bidget.txt","r");
if (fp==NULL)
newf();
while(!feof(fp)){
      flag=1;
	fscanf(fp,"%f ", &lmoney); }
	fclose(fp);
	
	 next();
	 
	 return 0;
}
