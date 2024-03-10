#include<iostream>
#include<fstream>
#include<string>
using namespace std;
void signup()
{
    string name,email, password,confirmpassword;
    cout<<"Enter your name: ";
    cin>>name;
    cout<<"Enter your email: ";
    cin>>email;
    cout<<"Enter your password: ";
    cin>>password;
    cout<<"Confirm your password: ";
    cin>>confirmpassword;
    if(password==confirmpassword)
    {
        cout<<"Signup successful";
    }
    else
    {
        cout<<"Password does not match";
    }
    ofstream out("user_data.txt",ios::app);
    out<<name<<endl;
    out<<email<<endl;
    out<<password<<endl;
    out.close();
}
void login()
{
    string email, password;
    cout<<"Enter your email: ";
    cin>>email;
    cout<<"Enter your password: ";
    cin>>password;
    ifstream in("user_data.txt");
    //doubt file m forward move kaise kre jaise ek nam ka email password checked then dusre and son on.
}
void exit()
{
  cout<<"exited";
  return ;
}
void forget_password()
{
  cout<<"set new password"<<endl;
  string newpassword,confirmnewpassword;;
  cout<<"enter new password"<<endl;
  cin>>newpassword;
  ofstream out("user.txt",ios::app);
  out<<newpassword<<endl;
  getline(cin,confirmnewpassword);
  if(newpassword==confirmnewpassword)
  {
    cout<<"password set successfully"<<endl;
  }
}
int main()
{
  int choice;
  cout<<"1.) login\n";
  cout<<"2.) signup\n";
  cout<<"3.) forgot password\n";
  cout<<"4.) exit\n";
  cout<<"enter your choice\n";
  cin>>choice;
  switch(choice)
    {
      case 1:
      //cout<<"login\n";
      login();
      break;

      case 2:
      //cout<<"signup\n";
      signup();
      break;

      case 3:
      //cout<<"forgot password\n";
      forget_password();
      break;

      case 4:
      //cout<<"exit\n";
      exit();
      break;

      default :
      cout<<"invalid choice\n";
    }
}
