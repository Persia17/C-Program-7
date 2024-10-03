# C-Program-7
#include<iostream>
using namespace std;
class DB;
class DM{
    int meter,centimeter;
    public:
    void accept(){
        cout<<"Enter the meter and centimeter value:"<<endl;
        cin>>meter>>centimeter;
    }
    void display(){
        cout<<"\nMeter: "<<meter;
        cout<<"\nCentimeter: "<<centimeter;
    }
    friend void add(DB d1,DM d2);
};
class DB{
    int inches,feet;
    public:
    void accept(){
        cout<<"Enter the Feet and Inches value:"<<endl;
        cin>>feet>>inches;
    }
    void display(){
        cout<<"\nFeet: "<<feet;
        cout<<"\nInches: "<<inches;
    }
    friend void add(DB d1,DM d2);
};
void add(DB d1,DM d2){
    DM d;
    int c=(d2.meter*100+d2.centimeter+d1.feet*30.48+d1.inches*2.54);
    if(c>=100){
       d.meter=c/100;
       d.centimeter=c%100;
    }
    else{
        d.meter=0;
        d.centimeter=c;
    }
    d.display();
}
int main(){
    DB d1;
    DM d2;
    d1.accept();
    d2.accept();

    d1.display();
    d2.display();

    cout<<"\nAddition of Meter and Centimeter: "<<endl;
    add(d1,d2);

    return 0;
}

