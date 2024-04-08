#include<iostream>
using namespace std;

class Linklist
{
    private:
        struct Node
        {
            int data;
            Node*link;
        }*START;
    public:
        Linklist();
        void insert (int no);
        void display ();
        void insertbeg(int num);
        void insert_at_location(int loc,int num);
        void insert_before_element(int bnum,int num);
        void deletebeg();
        void deletend();
        void delete_before(int num);
        void delete_after(int num);
        void search(int num);
        ~Linklist ();
};
Linklist::Linklist()
{
    START=NULL;
}
Linklist::~Linklist()
{
    Node*q;
    while (START!=NULL)
    {
        q=START->link;
        delete START;
        START=q;
    }
}
void Linklist::display()
{
    Node*PTR=START;
    while(PTR!=0)
    {
        cout<<PTR->data<<" ";
        PTR=PTR->link;
    }
    cout<<endl;
}
void Linklist::insert (int num)
{
    Node*PTR,*r;
    if(START==NULL)
    {
        PTR=new Node;
        PTR->data=num;
        PTR->link=NULL;
        START=PTR;
    }
    else
    {
        PTR=START;
        while (PTR->link !=NULL)
            PTR=PTR->link;
        
        r=new Node;
        r->data=num;
        r->link=NULL;
        PTR->link=r;
    }
}
void Linklist::insertbeg(int num)
{
    Node*PTR;
    PTR=new Node;
    PTR->data=num;
    PTR->link=START;
    START=PTR;
}
void Linklist::insert_at_location(int loc, int num)
{
    Node*PTR,*r;
    PTR=START;
    for(int i=0;i<loc;i++)
    {
        PTR=PTR->link;
        if(PTR==NULL)
        {
            cout<<"There are less than "<<loc<<" elements in list "<<endl;
            return ;
        }
    }
    r=new Node;
    r->data=num;
    r->link=PTR->link;
    PTR->link=r;
}
void Linklist::insert_before_element(int bnum,int num)
{
    Node*PTR,*r;
    PTR=START;
    Node* prev=nullptr;
    if(PTR !=nullptr && PTR->data==bnum)
    {
        r=new Node;
        r->data=num;
        r->link=PTR;
        START=r;
        return;
    }
    while (PTR!=nullptr &&PTR->data !=bnum)
    {
        prev=PTR;
        PTR=PTR->link;
    }
    if(PTR==nullptr)
    {
        cout<<"Element " << bnum << " not found in the linked list." << endl;
        return;
    }
    r=new Node;
    r->data=num;
    prev->link=r;
    r->link=PTR;
}
void Linklist::deletebeg()
{
    Node*PTR,*r;
    if(START ==nullptr)
    {
        cout<<"Linked list is empty. Cannot delete from an empty list." << endl;
        return;
    }
    r=START;
    START=START->link;
    delete r;
}
void Linklist::deletend()
{
    if (START == nullptr) {
        cout << "Linked list is empty. Cannot delete from an empty list." << endl;
        return;
    }
    if (START->link == nullptr) {
        delete START;
        START = nullptr;
        return;
    }
    Node* prev = nullptr;
    Node*PTR;
    PTR=START;
    while (PTR->link != nullptr)
    {
        prev = PTR;
        PTR = PTR->link;
    }
    prev->link = nullptr;
    delete PTR;
}
void Linklist::delete_before(int num)
{
    Node*PTR,*prev;
    cout<<"Enter the number of which before element has to be deleted: ";
    cin>>num;
    PTR=START;
    prev=nullptr;
    if (START == nullptr || START->link == nullptr) 
    {
        cout << "Cannot delete before. Linked list does not have enough elements." << endl;
        return;
    }
    while (PTR != nullptr && PTR->data != num) 
    {
        prev = PTR;
        PTR = PTR->link;
    }
    if (PTR == nullptr || PTR == START) 
    {
        cout << "Element " << num << " not found in the linked list." << endl;
        return;
    }
    if (prev == nullptr) 
    {
        cout << "No node to delete before the first node." << endl;
        return;
    }
    Node* toDelete = prev->link;
    prev->link = PTR;

    delete toDelete;
}
void Linklist::delete_after(int num)
{
    Node*PTR,*after;
    cout<<"Enter the number of which after element has to be deleted: ";
    cin>>num;
    PTR=START;
    after=nullptr;
    if (START == nullptr || START->link == nullptr) 
    {
        cout << "Cannot delete after. Linked list does not have enough elements." << endl;
        return;
    }
    while (PTR != nullptr && PTR->data != num) 
    {
        PTR = PTR->link;
    }
    if (PTR == nullptr) 
    {
        cout << "Element " << num << " not found in the linked list." << endl;
        return;
    }
    if (PTR->link == nullptr) {
        cout << "No node to delete after the last node." << endl;
        return;
    }
    after = PTR->link;
    PTR->link = after->link;

    delete after;
}
void Linklist::search(int num)
{
    Node*PTR;
    PTR=START;
    int count;
    cout<<"Enter the element you search for: ";
    while(PTR->data!=num)
    {
        count++;
        PTR=PTR->link;
    }
    cout<<"Element "<<num<<" found at "<<count;
}
void all_opp(Linklist& l)
{
    int choice, num, loc, bnum;
    do {
        cout << "1. Insert\n";
        cout << "2. Insert at Beginning\n";
        cout << "3. Insert at Location\n";
        cout << "4. Insert Before Element\n";
        cout << "5. Delete from Beginning\n";
        cout << "6. Delete from End\n";
        cout << "7. Delete Before Element\n";
        cout << "8. Delete After Element\n";
        cout << "9. Search\n";
        cout << "10. Display\n";
        cout << "11. Exit\n";
        cout << "Enter your choice: ";
        cin >> choice;

        switch (choice)
        {
        case 1:
            cout << "Enter the number to insert: ";
            cin >> num;
            l.insert(num);
            break;
        case 2:
            cout << "Enter the number to insert at beginning: ";
            cin >> num;
            l.insertbeg(num);
            break;
        case 3:
            cout << "Enter the number to insert: ";
            cin >> num;
            cout << "Enter the location: ";
            cin >> loc;
            l.insert_at_location(loc, num);
            break;
        case 4:
            cout << "Enter the number to insert before: ";
            cin >> bnum;
            cout << "Enter the number to insert: ";
            cin >> num;
            l.insert_before_element(bnum, num);
            break;
        case 5:
            l.deletebeg();
            break;
        case 6:
            l.deletend();
            break;
        case 7:
            cout << "Enter the number of which before element has to be deleted: ";
            cin >> num;
            l.delete_before(num);
            break;
        case 8:
            cout << "Enter the number of which after element has to be deleted: ";
            cin >> num;
            l.delete_after(num);
            break;
        case 9:
            cout << "Enter the element you want to search: ";
            cin >> num;
            l.search(num);
            break;
        case 10:
            cout << "The linked list contains: ";
            l.display();
            break;
        case 11:
            cout << "Exiting...\n";
            break;
        default:
            cout << "Invalid choice. Please enter a valid option.\n";
            break;
        }
    } while (choice != 11);
}

int main()
{
    Linklist l;
    int num;
    cout << "Enter the number of elements to store: ";
    cin >> num;

    for (int i = 0; i < num; i++) 
    {
        int a;
        cout<<"Enter the "<<i+1<< " element: ";
        cin>>a;
        l.insert(a);
    }
    all_opp(l);
    return 0;
}
