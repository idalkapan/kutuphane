# kutuphane
#pragma once

#include <vector>    //dinamik boyutlu dizileri temsil eden kütüphanedir.
#include <string>     // metinsel verileri saklamak için kullanılan kütüphanedir.
#include <fstream>     // dosya işlemleri için kullanılan kütüphanedir.
#include <sstream>       //  string üzerinde işlemler yapmamizi sağlayan kütüphanedir. metin işleme ve                               dönüştürmede çok kullanılır.
#include <codecvt>        //karakter kodlama dönüşümleri için kullanılır.

// Veritabanı yapısı
struct DatabaseStruct {
    std::stringstream stream;     // Veritabanı üzerinde işlemleri gerçekleştirmek için
    std::vector<int> bookIDList;   // Kitap ID'lerini tutan tamsayı vektörü
    std::vector<int> userIDList;     // Kullanıcı ID'lerini tutan tamsayı vektörü
};

// Kitap sınıfı
class ClassBook {
public:
    ClassBook(
        int           ID, //1
        std::string   title, //2
        int           ownerID = 0, //3
        int           timeBorrow = 0, //4
        std::string   placeNumber = "0", //5
        std::string   copy = "", //6
        std::string   library = "", //7
        std::string   section = "", //8
        std::string   collection = "", //9
        std::string   subsection = "", //10
        std::string   shape = "", //11
        std::string   enviroment = "", //12
        std::string   lang = "", //13
        std::string   author = "", //14
        std::string   responsible = "", //15
        std::string   year = "", //16
        std::string isbn = 0, //17
        std::string   info = "", //18
        std::string   publisher = "", //19
        std::string   edition = "", //20
        std::string   physAttrib = "", //21
        std::string   serialRec = "", //22
        std::string   subject = "", //23
        std::string   notes = "" //24
    );
    ~ClassBook(){}     //Kitap nesnesi oluşturur


    int           getID() { return ID; }    // Kitap ID'sini döndürür
    std::string   getTitle() { return title; } // Kitap başlığını döndürür
    int           getOwnerID() { return ownerID; }         // Diğer get ve set fonksiyonları kitap                                                                özelliklerine erişim sağlar
    int           getTimeBorrow() { return timeBorrow; }
    std::string   GetPlaceNumber() { return placeNumber; }
    std::string   GetCopy() { return copy; }
    std::string   GetLibrary() { return library; }
    std::string   GetSection() { return section; }
    std::string   GetCollection() { return collection; }
    std::string   GetSubSection() { return subsection; }
    std::string   GetShape() { return shape; }
    std::string   GetEnviroment() { return enviroment; }
    std::string   GetLang() { return lang; }
    std::string   GetAuthor() { return author; }
    std::string   GetResponsible() { return responsible; }
    std::string   GetYear() { return year; }
    std::string GetISBN() { return isbn; }
    std::string   GetInfo() { return info; }
    std::string   GetPublisher() { return publisher; }
    std::string   GetEdition() { return edition; }
    std::string   GetPhysAttrib() { return physAttrib; }
    std::string   GetSerialRec() { return serialRec; }
    std::string   GetSubject() { return subject; }
    std::string   GetNotes() { return notes; }

    void SetID(int newID) { ID = newID; }
    void SetTitle(const std::string& newTitle) { title = newTitle; }
    void SetOwnerID(int newOwnerID) { ownerID = newOwnerID; }
    void SetTimeBorrow(int newTimeBorrow) { timeBorrow = newTimeBorrow; }
    void SetPlaceNumber(const std::string& newPlaceNumber) { placeNumber = newPlaceNumber; }
    void SetCopy(const std::string& newCopy) { copy = newCopy; }
    void SetLibrary(const std::string& newLibrary) { library = newLibrary; }
    void SetSection(const std::string& newSection) { section = newSection; }
    void SetCollection(const std::string& newCollection) { collection = newCollection; }
    void SetSubSection(const std::string& newSubSection) { subsection = newSubSection; }
    void SetShape(const std::string& newShape) { shape = newShape; }
    void SetEnviroment(const std::string& newEnviroment) { enviroment = newEnviroment; }
    void SetLang(const std::string& newLang) { lang = newLang; }
    void SetAuthor(const std::string& newAuthor) { author = newAuthor; }
    void SetResponsible(const std::string& newResponsible) { responsible = newResponsible; }
    void SetYear(const std::string& newYear) { year = newYear; }
    void SetISBN(const std::string& newISBN) { isbn = newISBN; }
    void SetInfo(const std::string& newInfo) { info = newInfo; }
    void SetPublisher(const std::string& newPublisher) { publisher = newPublisher; }
    void SetEdition(const std::string& newEdition) { edition = newEdition; }
    void SetPhysAttrib(const std::string& newPhysAttrib) { physAttrib = newPhysAttrib; }
    void SetSerialRec(const std::string& newSerialRec) { serialRec = newSerialRec; }
    void SetSubject(const std::string& newSubject) { subject = newSubject; }
    void SetNotes(const std::string& newNotes) { notes = newNotes; }

protected:

    int         ID; //1
    std::string title; //2
    int         ownerID; //3
    int         timeBorrow; //4
    std::string placeNumber; //5
    std::string copy; //6
    std::string library; //7
    std::string section; //8
    std::string collection; //9
    std::string subsection; //10
    std::string shape; //11
    std::string enviroment; //12
    std::string lang; //13
    std::string author; //14
    std::string responsible; //15
    std::string year; //16
    std::string isbn; //17
    std::string info; //18
    std::string publisher; //19
    std::string edition; //20
    std::string physAttrib; //21
    std::string serialRec; //22
    std::string subject; //23
    std::string notes; //24

};

class ClassUser {     // Kullanıcı sınıfı
public:
    ClassUser(int ID, std::string name, std::string password, bool isMod); //Bu sınıf, bir kullanıcının temel özelliklerini (ID, isim, şifre, mod yetkisi, ve giriş durumu) ve bu özelliklere erişim ve değiştirme fonksiyonlarını içerir.

    int getID() { return ID; }     //get` Fonksiyonları: `getID()`, `getName()`, `getPassword()`, `getMod()` ve `getLogin()` fonksiyonları, ilgili özelliklere erişmek için kullanılır.

    std::string getName() { return name; }
    std::string getPassword() { return password; }
    bool getMod() { return isMod; }
    bool getLogin() { return loggedIn; }

    void SetID(int newID) { ID = newID; }   //`set` Fonksiyonları: `SetID()` ve `SetMod()` fonksiyonları, ilgili özellikleri değiştirmek için kullanılır.
    void SetMod(bool newMod) { isMod = newMod; }

    void login() { loggedIn = true; }     //login()` ve `logout()` Fonksiyonları: Kullanıcının giriş durumunu değiştirmek için kullanılır.
    void logout() { loggedIn = false; }

protected:    //protected` Veriler: Sınıfın korunan verileri tanımlanır. `ID`, `name`, `password` gibi özellikler doğrudan erişilemez, ancak bu sınıfın alt sınıflarından erişilebilirler.

    int ID;
    std::string name;
    std::string password;
    bool loggedIn = false;
    bool isMod = false;

};

std::vector<ClassBook> bookList;  // Kitap nesnelerini tutan vektör
std::vector<ClassUser> userList;  // Kullanıcı nesnelerini tutan vektör


ClassBook::ClassBook(      //`ClassBook` sınıfı tanımlanır. Bu sınıf, kitap nesnelerini temsil eder. Verilen çeşitli özelliklere sahiptir.

    int         ID, //1
    std::string title, //2
    int         ownerID, //3
    int         timeBorrow, //4
    std::string placeNumber, //5
    std::string copy, //6
    std::string library, //7
    std::string section, //8
    std::string collection, //9
    std::string subsection, //10
    std::string shape, //11
    std::string enviroment,//12
    std::string lang, //13
    std::string author, //14
    std::string responsible, //15
    std::string year, //16
    std::string isbn, //17
    std::string info, //18
    std::string publisher, //19
    std::string edition, //20
    std::string physAttrib, //21
    std::string serialRec, //22
    std::string subject, //23
    std::string notes //24
        ) :
    ID(ID), //1
    title(title), //2
    ownerID(ownerID), //3
    timeBorrow(timeBorrow), //4
    placeNumber(placeNumber), //5
    copy(copy), //6
    library(library), //7
    section(section), //8
    collection(collection), //9
    subsection(subsection), //10
    shape(shape), //11
    enviroment(enviroment), //12
    lang(lang), //13
    author(author), //14
    responsible(responsible), //15
    year(year), //16
    isbn(isbn), //17
    info(info), //18
    publisher(publisher), //19
    edition(edition), //20
    physAttrib(physAttrib), //21
    serialRec(serialRec), //22
    subject(subject), //23
    notes(notes) //24
{
    bookList.push_back(*this);     //`bookList` ve `userList` vektörleri tanımlanır ve sınıf nesneleri oluşturulduğunda bu vektörlere eklenirler. Böylece, kullanıcılar ve kitaplar vektörlerde saklanır.

}

ClassUser::ClassUser(int ID, std::string name, std::string password, bool isMod) : ID(ID), name(name), password(password), isMod(isMod) {
    userList.push_back(*this);
}

DatabaseStruct readDatabase(); //readDatabase() fonksiyonunu çağırarak bir DatabaseStruct yapısı döndürür.

bool saveDatabase() {    //saveDatabase adında bir fonksiyon başlatılıyor, bu fonksiyon bir bool değer döndürür.
    DatabaseStruct database = readDatabase();  //readDatabase() fonksiyonunu çağırarak dönen değeri database adlı bir DatabaseStruct değişkende saklar.
    {
        std::string inter = database.stream.str(); //database yapısının stream verisini bir std::string değişkende saklar.
        inter.erase(inter.end() - 6, inter.end());  //inter değişkeninin son 6 karakterini siler.
        database.stream.str(inter);       //database yapısının stream verisini temizlenmiş inter değişkeniyle günceller.
    }
    database.stream.seekp(0, std::ios_base::end); //database yapısının stream konumunu dosyanın sonuna taşır.

    bool cont = true;

    for (int i = 0; i < bookList.size(); i++) {
        for (int k = 0; k < database.bookIDList.size(); k++) {
            if (bookList[i].getID() == database.bookIDList[k]) { cont = false; break; }
        }

        if (cont == false) { cont = true; continue; }
        database.stream << "Start book\n";
        database.stream << bookList[i].getID() << "\n";
        database.stream << bookList[i].getTitle() << "\n";
        database.stream << bookList[i].getOwnerID() << "\n";
        database.stream << bookList[i].getTimeBorrow() << "\n";
        database.stream << bookList[i].GetPlaceNumber() << "\n";
        database.stream << bookList[i].GetCopy() << "\n";
        database.stream << bookList[i].GetLibrary() << "\n";
        database.stream << bookList[i].GetSection() << "\n";
        database.stream << bookList[i].GetCollection() << "\n";
        database.stream << bookList[i].GetSubSection() << "\n";
        database.stream << bookList[i].GetShape() << "\n";
        database.stream << bookList[i].GetEnviroment() << "\n";
        database.stream << bookList[i].GetLang() << "\n";
        database.stream << bookList[i].GetAuthor() << "\n";
        database.stream << bookList[i].GetResponsible() << "\n";
        database.stream << bookList[i].GetYear() << "\n";
        database.stream << bookList[i].GetISBN() << "\n";
        database.stream << bookList[i].GetInfo() << "\n";
        database.stream << bookList[i].GetPublisher() << "\n";
        database.stream << bookList[i].GetEdition() << "\n";
        database.stream << bookList[i].GetPhysAttrib() << "\n";
        database.stream << bookList[i].GetSerialRec() << "\n";
        database.stream << bookList[i].GetSubject() << "\n";
        database.stream << bookList[i].GetNotes() << "\n";
        database.stream << "End book\n";
    }
    cont = true;
    for (int i = 0; i < userList.size(); i++) {
        for (int k = 0; k < database.userIDList.size(); k++) {
            if (userList[i].getID() == database.userIDList[k]) { cont = false; break; }
        }

        if (cont == false) { cont = true; continue; }
        database.stream << "Start user\n";
        database.stream << userList[i].getID() << "\n";
        database.stream << userList[i].getName() << "\n";
        database.stream << userList[i].getPassword() << "\n";
        database.stream << userList[i].getMod() << "\n";
        database.stream << "End user\n";
    }

    database.stream << "Final\n";

    std::ofstream fileDatabase;
    fileDatabase.open("Database.txt");

    if (fileDatabase.is_open()) {
        fileDatabase << database.stream.str();
        
        fileDatabase.close();
    }
    else {
        fileDatabase.close();
        return 0;
    }

    return 1;
}

void readDataBook(std::ifstream &file, std::string &input, DatabaseStruct &database) {
    int         id; //1
    std::string title; //2
    int         ownerID = 0; //3
    int         timeBorrow = 0; //4
    std::string placeNumber = "0"; //5
    std::string copy = ""; //6
    std::string library = ""; //7
    std::string section = ""; //8
    std::string collection = ""; //9
    std::string subsection = ""; //10
    std::string shape = ""; //11
    std::string enviroment = ""; //12
    std::string lang = ""; //13
    std::string author = ""; //14
    std::string responsible = ""; //15
    std::string year = ""; //16
    std::string isbn = ""; //17
    std::string info = ""; //18
    std::string publisher = ""; //19
    std::string edition = ""; //20
    std::string physAttrib = ""; //21
    std::string serialRec = ""; //22
    std::string subject = ""; //23
    std::string notes = ""; //24

    int readOrder = 1;
    bool duplBreak = false;

    while (file) {
        getline(file, input);
        database.stream << input << "\n";

        if (duplBreak == true) {
            break;
        }

        if (input == "End book") {
            ClassBook(
                id,
                title,
                ownerID,
                timeBorrow,
                placeNumber,
                copy,
                library,
                section,
                collection,
                subsection,
                shape,
                enviroment,
                lang,
                author,
                responsible,
                year,
                isbn,
                info,
                publisher,
                edition,
                physAttrib,
                serialRec,
                subject,
                notes);

            readOrder = 0;
            break;
        }
        else if (readOrder == 1) {
            id = atoi(input.c_str());;
            database.bookIDList.push_back(id);
            readOrder++;

            for (int i = 0; i < bookList.size(); i++) {
                if (id == bookList[i].getID()) {
                    duplBreak = true;
                }
            }
        }
        else if (readOrder == 2) {
            title = input;
            readOrder++;
        }
        else if (readOrder == 3) {
            ownerID = atoi(input.c_str());
            readOrder++;
        }
        else if (readOrder == 4) {
            timeBorrow = atoi(input.c_str());
            readOrder++;
        }
        else if (readOrder == 5) {
            placeNumber = input;
            readOrder++;
        }
        else if (readOrder == 6) {
            copy = input;
            readOrder++;
        }
        else if (readOrder == 7) {
            library = input;
            readOrder++;
        }
        else if (readOrder == 8) {
            section = input;
            readOrder++;
        }
        else if (readOrder == 9) {
            collection = input;
            readOrder++;
        }
        else if (readOrder == 10) {
            subsection = input;
            readOrder++;
        }
        else if (readOrder == 11) {
            shape = input;
            readOrder++;
        }
        else if (readOrder == 12) {
            enviroment = input;
            readOrder++;
        }
        else if (readOrder == 13) {
            lang = input;
            readOrder++;
        }
        else if (readOrder == 14) {
            author = input;
            readOrder++;
        }
        else if (readOrder == 15) {
            responsible = input;
            readOrder++;
        }
        else if (readOrder == 16) {
            year = input;
            readOrder++;
        }
        else if (readOrder == 17) {
            isbn = atoi(input.c_str());
            readOrder++;
        }
        else if (readOrder == 18) {
            info = input;
            readOrder++;
        }
        else if (readOrder == 19) {
            publisher= input;
            readOrder++;
        }
        else if (readOrder == 20) {
            edition = input;
            readOrder++;
        }
        else if (readOrder == 21) {
            physAttrib = input;
            readOrder++;
        }
        else if (readOrder == 22) {
            serialRec = input;
            readOrder++;
        }
        else if (readOrder == 23) {
            subject = input;
            readOrder++;
        }
        else if (readOrder == 24) {
            notes = input;
            readOrder++;
        }
    }
}

void readDataUser(std::ifstream& file, std::string &input, DatabaseStruct &database) {
    int id;
    std::string name;
    std::string password;
    bool mod;

    int readOrder = 1;
    bool duplBreak = false;

    while (file) {
        getline(file, input);
        database.stream << input << "\n";

        if (duplBreak == true) {
            break;
        }

        if (input == "End user") {
            ClassUser(id, name, password, mod);
            readOrder = 0;
            break;
        }
        else if (readOrder == 1) {
            id = atoi(input.c_str());;
            database.userIDList.push_back(id);
            readOrder++;

            for (int i = 0; i < userList.size(); i++) {
                if (id == userList[i].getID()) {
                    duplBreak = true;
                }
            }
        }
        else if (readOrder == 2) {
            name = input;
            readOrder++;
        }
        else if (readOrder == 3) {
            password = input;
            readOrder++;
        }
        else if (readOrder == 4) {
            if (input == "1") {
                mod = true;
            }
            else {
                mod = false;
            }
            readOrder++;
        }
    }
}

DatabaseStruct readDatabase() {
    std::ifstream file;
    std::string input;
    DatabaseStruct database;

    file.open("Database.txt");

    while (file) {
        getline(file, input);
        database.stream << input << "\n";

        if (input == "Start book") {
            readDataBook(file, input, database);
        }
        else if (input == "Start user") {
            readDataUser(file, input, database);
        }
        
        if (input == "Final") {
            break;
        }
    }
    file.close();

    return database;
}

void MoveBookContents(const int& bookID, DatabaseStruct &database) {
    std::string input;
    int readOrder = 1;
    int id;
    std::streampos posStart;
    std::streampos posEnd;
    std::string inter;
    inter = database.stream.str();

    bookList.erase(bookList.begin() + (bookID));

    for (int i = 0; i < bookList.size(); i++) {
        if (i >= bookID) {
            bookList[i].SetID(i);
        }
    }
    
    database.stream.seekg(0, std::ios_base::beg);

    while (database.stream) {
        std::getline(database.stream, input);

        if (input == "Start book") {
            readOrder++;
        }
        else if (readOrder == 2) {
            id = atoi(input.c_str());
            if (id > bookID) {
                database.stream.seekg(-(int)(input.size() + 1), std::ios_base::cur);
                posStart = database.stream.tellg();
                database.stream.seekg(input.size(), std::ios_base::cur);
                posEnd = database.stream.tellg();
                
                inter.erase(posStart, posEnd - posStart);
                inter.insert(posStart, std::to_string(id - 1));
                database.stream.str(inter);

                database.stream.seekg(posEnd, std::ios_base::beg);

            }
            readOrder = 1;
        }
    }
}

void MoveUserContents(const int& userID, DatabaseStruct& database) {
    std::string input;
    int readOrder = 1;
    int id;
    std::streampos posStart;
    std::streampos posEnd;
    std::string inter;
    inter = database.stream.str();

    userList.erase(userList.begin() + (userID));

    for (int i = 0; i < userList.size(); i++) {
        if (i >= userID) {
            userList[i].SetID(i);
        }
    }

    database.stream.seekg(0, std::ios_base::beg);

    while (database.stream) {
        std::getline(database.stream, input);

        if (input == "Start user") {
            readOrder++;
        }
        else if (readOrder == 2) {
            id = atoi(input.c_str());
            if (id > userID) {
                database.stream.seekg(-(int)(input.size() + 1), std::ios_base::cur);
                posStart = database.stream.tellg();
                database.stream.seekg(input.size(), std::ios_base::cur);
                posEnd = database.stream.tellg();

                inter.erase(posStart, posEnd - posStart);
                inter.insert(posStart, std::to_string(id - 1));
                database.stream.str(inter);

                database.stream.seekg(posEnd, std::ios_base::beg);
            }
            readOrder = 1;
        }
    }
}

void DeleteBook(int bookID) {
    DatabaseStruct database = readDatabase();
    database.stream.seekg(0, std::ios_base::beg);
    std::fstream file;
    std::string input;
    int readOrder = 1;
    int id;
    std::streampos posStart;
    std::streampos posEnd;

    while (database.stream) {
        std::getline(database.stream, input);

        if (input == "Start book") {
            database.stream.seekg(-11, std::ios_base::cur);
            posStart = database.stream.tellg();
            database.stream.seekg(11, std::ios_base::cur);
            readOrder++;
        }
        else if (readOrder == 2) {
            id = atoi(input.c_str());
            if (id == bookID) {
                readOrder++;
            }
            else {
                readOrder = 1;
            }
        }
        else if (input == "End book" && readOrder != 1) {

            posEnd = database.stream.tellg();
            {
                std::string inter = database.stream.str();
                inter.erase(posStart, posEnd - posStart);
                database.stream.str(inter);
            }

            database.stream.seekg(0, std::ios_base::beg);

            MoveBookContents(bookID, database);

            readOrder = 1;
            break;
        }

        if (input == "Final") {
            break;
        }
    }

    file.open("Database.txt");    // database.txt dosyasını açar.
    file << database.stream.str();
    file.close();
}

void DeleteUser(int userID) {
    DatabaseStruct database = readDatabase();
    database.stream.seekg(0, std::ios_base::beg);
    std::fstream file;
    std::string input;
    int readOrder = 1;
    int id;
    std::streampos posStart;
    std::streampos posEnd;

    while (database.stream) {
        std::getline(database.stream, input);

        if (input == "Start user") {
            database.stream.seekg(-11, std::ios_base::cur);
            posStart = database.stream.tellg();
            database.stream.seekg(11, std::ios_base::cur);
            readOrder++;
        }
        else if (readOrder == 2) {
            id = atoi(input.c_str());
            if (id == userID) {
                readOrder++;
            }
            else {
                readOrder = 1;
            }
        }
        else if (input == "End user" && readOrder != 1) {

            posEnd = database.stream.tellg();
            {
                std::string inter = database.stream.str();
                inter.erase(posStart, posEnd - posStart);
                database.stream.str(inter);
            }

            database.stream.seekg(0, std::ios_base::beg);

            MoveUserContents(userID, database);

            readOrder = 1;
            break;
        }

        if (input == "Final") {
            break;
        }
    }

    file.open("Database.txt");
    file << database.stream.str();
    file.close();
}

void UpdateBook(int bookID) {
    DatabaseStruct database = readDatabase();
    database.stream.seekg(0, std::ios_base::beg);
    std::fstream file;
    std::string input;
    int readOrder = 1;
    int id;
    std::streampos posStart;
    std::streampos posEnd;
    std::string inter;
    std::string backup;

    while (database.stream) {
        std::getline(database.stream, input);

        if (input == "Start book") {
            database.stream.seekg(-11, std::ios_base::cur);
            posStart = database.stream.tellg();
            database.stream.seekg(11, std::ios_base::cur);
            readOrder++;
        }
        else if (readOrder == 2) {
            id = atoi(input.c_str());
            if (id == bookID) {
                readOrder++;
            }
            else {
                readOrder = 1;
            }
        }
        else if (input == "End book" && readOrder != 1) {

            posEnd = database.stream.tellg();
            
            inter = database.stream.str();
            inter.erase(posStart, posEnd - posStart);
            database.stream.str(inter);

            backup = database.stream.str();
            backup.erase(std::ios_base::beg, posStart);
            
            inter.erase(posStart, std::ios_base::end - posStart);
            database.stream.str(inter);
            
            readOrder = 1;
            break;
        }

        if (input == "Final") {
            break;
        }
    }

    database.stream.seekp(posStart, std::ios_base::beg);

    database.stream << "Start book\n";
    database.stream << bookList[bookID].getID() << "\n";
    database.stream << bookList[bookID].getTitle() << "\n";
    database.stream << bookList[bookID].getOwnerID() << "\n";
    database.stream << bookList[bookID].getTimeBorrow() << "\n";
    database.stream << bookList[bookID].GetPlaceNumber() << "\n";
    database.stream << bookList[bookID].GetCopy() << "\n";
    database.stream << bookList[bookID].GetLibrary() << "\n";
    database.stream << bookList[bookID].GetSection() << "\n";
    database.stream << bookList[bookID].GetCollection() << "\n";
    database.stream << bookList[bookID].GetSubSection() << "\n";
    database.stream << bookList[bookID].GetShape() << "\n";
    database.stream << bookList[bookID].GetEnviroment() << "\n";
    database.stream << bookList[bookID].GetLang() << "\n";
    database.stream << bookList[bookID].GetAuthor() << "\n";
    database.stream << bookList[bookID].GetResponsible() << "\n";
    database.stream << bookList[bookID].GetYear() << "\n";
    database.stream << bookList[bookID].GetISBN() << "\n";
    database.stream << bookList[bookID].GetInfo() << "\n";
    database.stream << bookList[bookID].GetPublisher() << "\n";
    database.stream << bookList[bookID].GetEdition() << "\n";
    database.stream << bookList[bookID].GetPhysAttrib() << "\n";
    database.stream << bookList[bookID].GetSerialRec() << "\n";
    database.stream << bookList[bookID].GetSubject() << "\n";
    database.stream << bookList[bookID].GetNotes() << "\n";
    database.stream << "End book\n";

    database.stream << backup;

    inter.clear();
    inter = database.stream.str();

    file.open("Database.txt");
    file << database.stream.str();
    file.close();
}

void UpdateUser(int userID) {
    DatabaseStruct database = readDatabase();
    database.stream.seekg(0, std::ios_base::beg);
    std::fstream file;
    std::string input;
    int readOrder = 1;
    int id;
    std::streampos posStart;
    std::streampos posEnd;
    std::string inter;
    std::string backup;

    while (database.stream) {
        std::getline(database.stream, input);

        if (input == "Start user") {
            database.stream.seekg(-11, std::ios_base::cur);
            posStart = database.stream.tellg();
            database.stream.seekg(11, std::ios_base::cur);
            readOrder++;
        }
        else if (readOrder == 2) {
            id = atoi(input.c_str());
            if (id == userID) {
                readOrder++;
            }
            else {
                readOrder = 1;
            }
        }
        else if (input == "End user" && readOrder != 1) {

            posEnd = database.stream.tellg();

            inter = database.stream.str();
            inter.erase(posStart, posEnd - posStart);
            database.stream.str(inter);

            backup = database.stream.str();
            backup.erase(std::ios_base::beg, posStart);

            inter.erase(posStart, std::ios_base::end - posStart);
            database.stream.str(inter);

            readOrder = 1;
            break;
        }

        if (input == "Final") {
            break;
        }
    }

    database.stream.seekp(posStart, std::ios_base::beg);

    database.stream << "Start user\n";
    database.stream << userList[userID].getID() << "\n";
    database.stream << userList[userID].getName() << "\n";
    database.stream << userList[userID].getPassword() << "\n";
    database.stream << userList[userID].getMod() << "\n";
    database.stream << "End user\n";

    database.stream << backup;

    inter.clear();
    inter = database.stream.str();

    file.open("Database.txt");
    file << database.stream.str();
    file.close();
}





#pragma once

#include "library.h"

#include <windows.h>
#include <windowsx.h>
#include <CommCtrl.h>

std::wstring Widen(std::string narrow) {
    wchar_t* buffer = new wchar_t[narrow.length() + 1];
    std::copy(narrow.begin(), narrow.end(), buffer);
    buffer[narrow.length()] = 0;

    std::wstring wide;
    wide.append(buffer);

    delete[] buffer;
    return wide;
}

std::wstring Widen(int narrowInt) {
    std::string narrow = std::to_string(narrowInt);
    wchar_t* buffer = new wchar_t[narrow.length() + 1];
    std::copy(narrow.begin(), narrow.end(), buffer);
    buffer[narrow.length()] = 0;

    std::wstring wide;
    wide.append(buffer);

    delete[] buffer;
    return wide;
}

std::string Narrowen(std::wstring wide){
    int len;
    int slength = wide.size();
    len = WideCharToMultiByte(CP_ACP, 0, wide.c_str(), slength, 0, 0, 0, 0);
    std::string r(len, '\0');
    WideCharToMultiByte(CP_ACP, 0, wide.c_str(), slength, &r[0], len, 0, 0);
    return r;
}

std::string Narrowen(int wideInt) {
    std::wstring wide = std::to_wstring(wideInt);
    int len;
    int slength = wide.size();
    len = WideCharToMultiByte(CP_ACP, 0, wide.c_str(), slength, 0, 0, 0, 0);
    std::string r(len, '\0');
    WideCharToMultiByte(CP_ACP, 0, wide.c_str(), slength, &r[0], len, 0, 0);
    return r;
}

template <class C>
class BaseWindow {
public:
    static HRESULT CALLBACK WindowProc(HWND hwnd, UINT uMsg, WPARAM wparam, LPARAM lparam) {
        C* pThis = NULL;
        
        if (uMsg == WM_NCCREATE) {
            CREATESTRUCT* pCreate = (CREATESTRUCT*)lparam;
            pThis = (C*)pCreate->lpCreateParams;
            SetWindowLongPtr(hwnd, GWLP_USERDATA, (LONG_PTR)pThis);

            pThis->m_hwnd = hwnd;
        }
        else {
            pThis = (C*)GetWindowLongPtr(hwnd, GWLP_USERDATA);
        }
        if (pThis) {
            return pThis->HandleMessage(uMsg, wparam, lparam);
        }
        else {
            return DefWindowProc(hwnd, uMsg, wparam, lparam);
        }
    }

    BaseWindow() : m_hwnd(NULL) {}

    BOOL Create(PCWSTR WindowName, DWORD Style, DWORD ExStyle = 0, int x = CW_USEDEFAULT, int y = CW_USEDEFAULT, int width = CW_USEDEFAULT, int height = 550, HWND hwndParent = 0, HMENU hmenu = 0) {
        WNDCLASS wnd = {0};

        wnd.lpfnWndProc = C::WindowProc;
        wnd.hInstance = GetModuleHandle(NULL);
        wnd.lpszClassName = ClassName();

        RegisterClass(&wnd);

        m_hwnd = CreateWindowEx(ExStyle, ClassName(), WindowName, Style, x, y, width, height, hwndParent, hmenu, GetModuleHandle(NULL), this);

        return (m_hwnd ? TRUE : FALSE);
    }

    HWND Window() const { return m_hwnd; }

protected:
    HWND m_hwnd;

    virtual PCWSTR ClassName() const = 0;
    virtual LRESULT HandleMessage(UINT uMsg, WPARAM wparam, LPARAM lparam) = 0;
};

class MainWindow : public BaseWindow<MainWindow> {
public:
    HWND loginUserBorder;
    HWND loginUserBox;
    HWND loginPasswordBox;
    HWND loginUser;
    HWND loginPassword;
    HWND buttonLogin;
    HWND buttonRegister;
    HWND buttonLogout;

    HWND logID; //1
    HWND logTitle; //2
    HWND logIsOwned; //3
    HWND logTimeBorrow; //4
    HWND logOwnerID; //5
    HWND logPlaceNumber; //6
    HWND logCopy; //7
    HWND logLibrary; //8
    HWND logSection; //9
    HWND logCollection; //10
    HWND logSubSection; //11
    HWND logShape; //12
    HWND logEnviroment; //13
    HWND logLang; //14
    HWND logAuthor; //15
    HWND logResponsible; //16
    HWND logYear; //17
    HWND logISBN; //18
    HWND logInfo; //19
    HWND logPublisher; //20
    HWND logEdition; //21
    HWND logPhysAttrib; //22
    HWND logSerialRec; //23
    HWND logSubject; //24
    HWND logNotes; //25
    HWND logName; //26
    HWND logIsMod; //27

    HWND textID; //1
    HWND textTitle; //2
    HWND textIsOwned; //3
    HWND textTimeBorrow; //4
    HWND textOwnerID; //5
    HWND textPlaceNumber; //6
    HWND textCopy; //7
    HWND textLibrary; //8
    HWND textSection; //9
    HWND textCollection; //10
    HWND textSubSection; //11
    HWND textShape; //12
    HWND textEnviroment; //13
    HWND textLang; //14
    HWND textAuthor; //15
    HWND textResponsible; //16
    HWND textYear; //17
    HWND textISBN; //18
    HWND textInfo; //19
    HWND textPublisher; //20
    HWND textEdition; //21
    HWND textPhysAttrib; //22
    HWND textSerialRec; //23
    HWND textSubject; //24
    HWND textNotes; //25
    HWND textName; //26
    HWND textIsMod; //27

    HWND buttonAdd;
    HWND buttonBorrow;
    HWND buttonDelete;
    HWND buttonMakeMod;

    HWND comboBoxPrimary;
    HWND comboBoxBook;
    HWND comboBoxUser;
    
    HWND buttonAddAlt;
    HWND buttonCancel;

    int colLoginUser = 20;
    int colLoginBorder = colLoginUser - 10;
    int colLoginPassword = colLoginUser;
    int colButtonLogin = colLoginBorder;
    int colButtonRegister = colButtonLogin + 60;
    int colButtonLogout = colButtonLogin;
    int rowLoginUser = 20;
    int rowLoginBorder = rowLoginUser - 20;
    int rowLoginPassword = rowLoginUser + 40;
    int rowButtonLogin = rowLoginBorder + 100;
    int rowButtonRegister = rowButtonLogin;
    int rowButtonLogout = rowButtonLogin;

    int colLogID = 450; //1
    int colLogTitle = colLogID; //2
    int colLogIsOwned = colLogID; //3
    int colLogTimeBorrow = colLogID; //4
    int colLogOwnerID = colLogID; //5
    int colLogPlaceNumber = colLogID; //6
    int colLogCopy = colLogID; //7
    int colLogLibrary = colLogID; //8
    int colLogSection = colLogID; //9
    int colLogCollection = colLogID; //10
    int colLogSubSection = colLogID; //11
    int colLogShape = colLogID; //12
    int colLogEnviroment = colLogID; //13
    int colLogLang = colLogID; //14
    int colLogAuthor = colLogID; //15
    int colLogResponsible = colLogID; //16
    int colLogYear = colLogID; //17
    int colLogISBN = colLogID; //18
    int colLogInfo = colLogID; //19
    int colLogPublisher = colLogID; //20
    int colLogEdition = colLogID; //21
    int colLogPhysAttrib = colLogID; //22
    int colLogSerialRec = colLogID; //23
    int colLogSubject = colLogID; //24
    int colLogNotes = colLogID; //25
    
    int rowLogID = 10; //1
    int rowLogTitle = rowLogID + 20; //2
    int rowLogIsOwned = rowLogTitle + 20; //3
    int rowLogTimeBorrow = rowLogIsOwned + 20; //4
    int rowLogOwnerID = rowLogTimeBorrow + 20; //5
    int rowLogPlaceNumber = rowLogOwnerID + 20; //6
    int rowLogCopy = rowLogPlaceNumber + 20; //7
    int rowLogLibrary = rowLogCopy + 20; //8
    int rowLogSection = rowLogLibrary + 20; //9
    int rowLogCollection = rowLogSection + 20; //10
    int rowLogSubSection = rowLogCollection + 20; //11
    int rowLogShape = rowLogSubSection + 20; //12
    int rowLogEnviroment = rowLogShape + 20; //13
    int rowLogLang = rowLogEnviroment + 20; //14
    int rowLogAuthor = rowLogLang + 20; //15
    int rowLogResponsible = rowLogAuthor + 20; //16
    int rowLogYear = rowLogResponsible + 20; //17
    int rowLogISBN = rowLogYear + 20; //18
    int rowLogInfo = rowLogISBN + 20; //19
    int rowLogPublisher = rowLogInfo + 20; //20
    int rowLogEdition = rowLogPublisher + 20; //21
    int rowLogPhysAttrib = rowLogEdition + 20; //22
    int rowLogSerialRec = rowLogPhysAttrib + 20; //23
    int rowLogSubject = rowLogSerialRec + 20; //24
    int rowLogNotes = rowLogSubject + 20; //25

    int colTextID = colLogID - 100; //1
    int colTextTitle = colLogTitle - 100; //2
    int colTextIsOwned = colLogIsOwned - 100; //3
    int colTextTimeBorrow = colLogTimeBorrow - 100; //4
    int colTextOwnerID = colLogOwnerID - 100; //5
    int colTextPlaceNumber = colLogPlaceNumber - 100; //6
    int colTextCopy = colLogCopy - 100; //7
    int colTextLibrary = colLogLibrary - 100; //8
    int colTextSection = colLogSection - 100; //9
    int colTextCollection = colLogCollection - 100; //10
    int colTextSubSection = colLogSubSection - 100; //11
    int colTextShape = colLogShape - 100; //12
    int colTextEnviroment = colLogEnviroment - 100; //13
    int colTextLang = colLogLang - 100; //14
    int colTextAuthor = colLogAuthor - 100; //15
    int colTextResponsible = colLogResponsible - 100; //16
    int colTextYear = colLogYear - 100; //17
    int colTextISBN = colLogISBN - 100; //18
    int colTextInfo = colLogInfo - 100; //19
    int colTextPublisher = colLogPublisher - 100; //20
    int colTextEdition = colLogEdition - 100; //21
    int colTextPhysAttrib = colLogPhysAttrib - 100; //22
    int colTextSerialRec = colLogSerialRec - 100; //23
    int colTextSubject = colLogSubject - 100; //24
    int colTextNotes = colLogNotes - 100; //25

    int rowTextID = rowLogID; //1
    int rowTextTitle = rowLogTitle; //2
    int rowTextIsOwned = rowLogIsOwned; //3
    int rowTextTimeBorrow = rowLogTimeBorrow; //4
    int rowTextOwnerID = rowLogOwnerID; //5
    int rowTextPlaceNumber = rowLogPlaceNumber; //6
    int rowTextCopy = rowLogCopy; //7
    int rowTextLibrary = rowLogLibrary; //8
    int rowTextSection = rowLogSection; //9
    int rowTextCollection = rowLogCollection; //10
    int rowTextSubSection = rowLogSubSection; //11
    int rowTextShape = rowLogShape; //12
    int rowTextEnviroment = rowLogEnviroment; //13
    int rowTextLang = rowLogLang; //14
    int rowTextAuthor = rowLogAuthor; //15
    int rowTextResponsible = rowLogResponsible; //16
    int rowTextYear = rowLogYear; //17
    int rowTextISBN = rowLogISBN; //18
    int rowTextInfo = rowLogInfo; //19
    int rowTextPublisher = rowLogPublisher; //20
    int rowTextEdition = rowLogEdition; //21
    int rowTextPhysAttrib = rowLogPhysAttrib; //22
    int rowTextSerialRec = rowLogSerialRec; //23
    int rowTextSubject = rowLogSubject; //24
    int rowTextNotes = rowLogNotes; //25

    int colAdd = colTextID;
    int colBorrow = colAdd + 75;
    int colDelete = colBorrow + 75;
    int colMakeMod = colDelete + 75;
    int rowAdd = rowTextID + 520;
    int rowBorrow = rowAdd;
    int rowDelete = rowBorrow;
    int rowMakeMod = rowDelete;

    int colCBoxPrim = colLogID + 350;
    int colCBoxSec = colCBoxPrim + 100;
    int rowCBoxPrim = rowLogID;
    int rowCBoxSec = rowCBoxPrim;
    
    int colAddAlt = colAdd;
    int colCancel = colBorrow;
    int rowAddAlt = rowAdd;
    int rowCancel = rowBorrow;

    int BorrowBook() {
        int selection = SendMessage(comboBoxBook, CB_GETCURSEL, (WPARAM)0, (LPARAM)0);
        int userID = -1;
        bool cont = true;

        if (bookList[selection].getTimeBorrow() != 0) {
            MessageBox(m_hwnd, L"This book is already borrowed.", L"Error", MB_OK);
            cont = false;
        }

        for (int i = 0; i <= userList.size(); i++) {
            if (i == userList.size()) {
                cont = false;
                MessageBox(m_hwnd, L"A user needs to be signed in to borrow books.", L"Error", MB_OK);

                break;
            }
            else if (userList[i].getLogin()) {
                userID = i;
                break;
            }
        }

        if (!cont) {
            return -1;
        }
        else {
            bookList[selection].SetOwnerID(userID);
            bookList[selection].SetTimeBorrow(7);
            UpdateBook(selection);
            MessageBox(m_hwnd, L"You have borrowed this book for 7 days.", L"Success", MB_OK);
        }

        return userID;
    }

    int Login(std::string name, std::string password) {
        int feedback = -1;
        
        for (int i = 0; i <= userList.size(); i++) {
            if (i == userList.size()) {
                return feedback = -1;
            }
            else if (name == userList[i].getName()) {
                if (password == userList[i].getPassword()) {
                    userList[i].login();
                    feedback = userList[i].getID();

                    SendMessage(loginUserBorder, WM_SETTEXT, NULL, (LPARAM)Widen(name).c_str());
                    SendMessage(loginUser, WM_SETTEXT, NULL, (LPARAM)L"");
                    SendMessage(loginPassword, WM_SETTEXT, NULL, (LPARAM)L"");

                    if (userList[feedback].getMod()) {
                        ShowWindow(comboBoxPrimary, SW_SHOW);
                        ShowWindow(buttonDelete, SW_SHOW);
                        ShowWindow(buttonAdd, SW_SHOW);
                    }

                    return feedback;
                }
                else {
                    return feedback = -2;
                }
            }
        }
        return feedback;
    }

    int Logout() {
        int feedback = 0;

        for (int i = 0; i <= userList.size(); i++) {
            if (i == userList.size()) {
                return feedback = -1;
            }
            else if (userList[i].getLogin() == true) {
                userList[i].logout();
                ShowWindow(comboBoxPrimary, SW_HIDE);
                ShowWindow(comboBoxUser, SW_HIDE);
                ShowWindow(buttonDelete, SW_HIDE);
                ShowWindow(buttonAdd, SW_HIDE);

                ShowWindow(comboBoxBook, SW_SHOW);

                SendMessage(comboBoxPrimary, CB_SETCURSEL, (WPARAM)0, (LPARAM)0);
                SendMessage(loginUserBorder, WM_SETTEXT, NULL, (LPARAM)L"Login");
            
                UpdateWindowBook();

                return userList[i].getID();
            }
        }

        

        return feedback;
    }

    void SwitchToAdd() {
        ShowWindow(logID, SW_HIDE);
        ShowWindow(textID, SW_HIDE);
        ShowWindow(logIsOwned, SW_HIDE);
        ShowWindow(textIsOwned, SW_HIDE);
        ShowWindow(logTimeBorrow, SW_HIDE);
        ShowWindow(textTimeBorrow, SW_HIDE);
        ShowWindow(logOwnerID, SW_HIDE);
        ShowWindow(textOwnerID, SW_HIDE);

        ShowWindow(buttonBorrow, SW_HIDE);
        ShowWindow(buttonAdd, SW_HIDE);
        ShowWindow(buttonDelete, SW_HIDE);
        ShowWindow(comboBoxPrimary, SW_HIDE);
        ShowWindow(comboBoxBook, SW_HIDE);
        ShowWindow(comboBoxUser, SW_HIDE);

        SendMessage(logID, WM_SETTEXT, (WPARAM)0, (LPARAM)L"");
        SendMessage(logTitle, WM_SETTEXT, (WPARAM)0, (LPARAM)L"");
        SendMessage(logIsOwned, WM_SETTEXT, (WPARAM)0, (LPARAM)L"");
        SendMessage(logTimeBorrow, WM_SETTEXT, (WPARAM)0, (LPARAM)L"");
        SendMessage(logOwnerID, WM_SETTEXT, (WPARAM)0, (LPARAM)L"");
        SendMessage(logName, WM_SETTEXT, (WPARAM)0, (LPARAM)L"");
        SendMessage(logIsMod, WM_SETTEXT, (WPARAM)0, (LPARAM)L"");

        ShowWindow(buttonAddAlt, SW_SHOW);
        ShowWindow(buttonCancel, SW_SHOW);
    }

    void SwitchToMain() {
        ShowWindow(logID, SW_SHOW);
        ShowWindow(textID, SW_SHOW);
        ShowWindow(logIsOwned, SW_SHOW);
        ShowWindow(textIsOwned, SW_SHOW);

        for (int i = 0; i < userList.size(); i++) {
            if (userList[i].getMod() && userList[i].getLogin()) {
                ShowWindow(comboBoxPrimary, SW_SHOW);
                ShowWindow(buttonDelete, SW_SHOW);
                ShowWindow(buttonAdd, SW_SHOW);
                ShowWindow(buttonMakeMod, SW_SHOW);
            }
        }
        if (SendMessage(comboBoxPrimary, CB_GETCURSEL, (WPARAM)0, (LPARAM)0) == 0) {
            ShowWindow(buttonBorrow, SW_SHOW);
            ShowWindow(logTimeBorrow, SW_SHOW);
            ShowWindow(textTimeBorrow, SW_SHOW);
            ShowWindow(logOwnerID, SW_SHOW);
            ShowWindow(textOwnerID, SW_SHOW);
        }
        else {
        }
        ShowWindow(comboBoxBook, SW_SHOW);
        ShowWindow(comboBoxUser, SW_SHOW);

        ShowWindow(buttonAddAlt, SW_HIDE);
        ShowWindow(buttonCancel, SW_HIDE);
    }

    void SwitchToBook() {
        ShowWindow(comboBoxBook, SW_SHOW);
        ShowWindow(buttonBorrow, SW_SHOW);
        ShowWindow(logIsOwned, SW_SHOW);
        ShowWindow(textIsOwned, SW_SHOW);
        ShowWindow(logTimeBorrow, SW_SHOW);
        ShowWindow(textTimeBorrow, SW_SHOW);
        ShowWindow(logOwnerID, SW_SHOW);
        ShowWindow(textOwnerID, SW_SHOW);
        ShowWindow(logPlaceNumber, SW_SHOW);
        ShowWindow(textPlaceNumber, SW_SHOW);
        ShowWindow(logCopy, SW_SHOW);
        ShowWindow(textCopy, SW_SHOW);
        ShowWindow(logLibrary, SW_SHOW);
        ShowWindow(textLibrary, SW_SHOW);
        ShowWindow(logSection, SW_SHOW);
        ShowWindow(textSection, SW_SHOW);
        ShowWindow(logCollection, SW_SHOW);
        ShowWindow(textCollection, SW_SHOW);
        ShowWindow(logSubSection, SW_SHOW);
        ShowWindow(textSubSection, SW_SHOW);
        ShowWindow(logShape, SW_SHOW);
        ShowWindow(textShape, SW_SHOW);
        ShowWindow(logEnviroment, SW_SHOW);
        ShowWindow(textEnviroment, SW_SHOW);
        ShowWindow(logLang, SW_SHOW);
        ShowWindow(textLang, SW_SHOW);
        ShowWindow(logAuthor, SW_SHOW);
        ShowWindow(textAuthor, SW_SHOW);
        ShowWindow(logResponsible, SW_SHOW);
        ShowWindow(textResponsible, SW_SHOW);
        ShowWindow(logYear, SW_SHOW);
        ShowWindow(textYear, SW_SHOW);
        ShowWindow(logISBN, SW_SHOW);
        ShowWindow(textISBN, SW_SHOW);
        ShowWindow(logInfo, SW_SHOW);
        ShowWindow(textInfo, SW_SHOW);
        ShowWindow(logPublisher, SW_SHOW);
        ShowWindow(textPublisher, SW_SHOW);
        ShowWindow(logEdition, SW_SHOW);
        ShowWindow(textEdition, SW_SHOW);
        ShowWindow(logPhysAttrib, SW_SHOW);
        ShowWindow(textPhysAttrib, SW_SHOW);
        ShowWindow(logSerialRec, SW_SHOW);
        ShowWindow(textSerialRec, SW_SHOW);
        ShowWindow(logSubject, SW_SHOW);
        ShowWindow(textSubject, SW_SHOW);
        ShowWindow(logNotes, SW_SHOW);
        ShowWindow(textNotes, SW_SHOW);
        ShowWindow(buttonAdd, SW_SHOW);

        ShowWindow(comboBoxUser, SW_HIDE);
        ShowWindow(logName, SW_HIDE);
        ShowWindow(textName, SW_HIDE);
        ShowWindow(logIsMod, SW_HIDE);
        ShowWindow(textIsMod, SW_HIDE);
        ShowWindow(buttonMakeMod, SW_HIDE);
        UpdateWindowBook();
    }

    void SwitchToUser(){
        ShowWindow(comboBoxBook, SW_HIDE);
        ShowWindow(buttonBorrow, SW_HIDE);
        ShowWindow(logIsOwned, SW_HIDE);
        ShowWindow(textIsOwned, SW_HIDE);
        ShowWindow(logTimeBorrow, SW_HIDE);
        ShowWindow(textTimeBorrow, SW_HIDE);
        ShowWindow(logOwnerID, SW_HIDE);
        ShowWindow(textOwnerID, SW_HIDE);
        ShowWindow(logPlaceNumber, SW_HIDE);
        ShowWindow(textPlaceNumber, SW_HIDE);
        ShowWindow(logCopy, SW_HIDE);
        ShowWindow(textCopy, SW_HIDE);
        ShowWindow(logLibrary, SW_HIDE);
        ShowWindow(textLibrary, SW_HIDE);
        ShowWindow(logSection, SW_HIDE);
        ShowWindow(textSection, SW_HIDE);
        ShowWindow(logCollection, SW_HIDE);
        ShowWindow(textCollection, SW_HIDE);
        ShowWindow(logSubSection, SW_HIDE);
        ShowWindow(textSubSection, SW_HIDE);
        ShowWindow(logShape, SW_HIDE);
        ShowWindow(textShape, SW_HIDE);
        ShowWindow(logEnviroment, SW_HIDE);
        ShowWindow(textEnviroment, SW_HIDE);
        ShowWindow(logLang, SW_HIDE);
        ShowWindow(textLang, SW_HIDE);
        ShowWindow(logAuthor, SW_HIDE);
        ShowWindow(textAuthor, SW_HIDE);
        ShowWindow(logResponsible, SW_HIDE);
        ShowWindow(textResponsible, SW_HIDE);
        ShowWindow(logYear, SW_HIDE);
        ShowWindow(textYear, SW_HIDE);
        ShowWindow(logISBN, SW_HIDE);
        ShowWindow(textISBN, SW_HIDE);
        ShowWindow(logInfo, SW_HIDE);
        ShowWindow(textInfo, SW_HIDE);
        ShowWindow(logPublisher, SW_HIDE);
        ShowWindow(textPublisher, SW_HIDE);
        ShowWindow(logEdition, SW_HIDE);
        ShowWindow(textEdition, SW_HIDE);
        ShowWindow(logPhysAttrib, SW_HIDE);
        ShowWindow(textPhysAttrib, SW_HIDE);
        ShowWindow(logSerialRec, SW_HIDE);
        ShowWindow(textSerialRec, SW_HIDE);
        ShowWindow(logSubject, SW_HIDE);
        ShowWindow(textSubject, SW_HIDE);
        ShowWindow(logNotes, SW_HIDE);
        ShowWindow(textNotes, SW_HIDE);
        ShowWindow(buttonAdd, SW_HIDE);

        ShowWindow(comboBoxUser, SW_SHOW);
        ShowWindow(logName, SW_SHOW);
        ShowWindow(textName, SW_SHOW);
        ShowWindow(logIsMod, SW_SHOW);
        ShowWindow(textIsMod, SW_SHOW);
        ShowWindow(buttonMakeMod, SW_SHOW);
        UpdateWindowUser();
    }

    void SwitchLogin(int mode) {
        if (mode == 1) {
            ShowWindow(loginUser, SW_HIDE);
            ShowWindow(loginPassword, SW_HIDE);
            ShowWindow(buttonLogin, SW_HIDE);
            ShowWindow(buttonRegister, SW_HIDE);

            ShowWindow(loginUserBox, SW_SHOW);
            ShowWindow(loginPasswordBox, SW_SHOW);
            ShowWindow(buttonLogout, SW_SHOW);
        }
        else if (mode == 0) {
            ShowWindow(loginUser, SW_SHOW);
            ShowWindow(loginPassword, SW_SHOW);
            ShowWindow(buttonLogin, SW_SHOW);
            ShowWindow(buttonRegister, SW_SHOW);

            ShowWindow(loginUserBox, SW_HIDE);
            ShowWindow(loginPasswordBox, SW_HIDE);
            ShowWindow(buttonLogout, SW_HIDE);
            SwitchToBook();
        }
    }

    void InsertToCBoxBook() {
        bool cont = true;
        int count = SendMessage(comboBoxBook, CB_GETCOUNT, (WPARAM)0, (LPARAM)0);
        int len;
        std::wstring title;
        std::string titleNarrow;

        for (int i = 0; i < bookList.size(); i++) {
            for (int k = 0; k < count; k++) {
                len = SendMessage(comboBoxBook, CB_GETLBTEXTLEN, k, (LPARAM)0);
                title.resize(len);
                SendMessage(comboBoxBook, CB_GETLBTEXT, k, (LPARAM)&title.c_str()[0]);
                titleNarrow = Narrowen(title);
                if (bookList[i].getTitle() == titleNarrow) {
                    cont = false;
                    break;
                }
            }

            if (cont == false) { cont = true; continue; }
            std::string insertNarrow = bookList[i].getTitle();
            std::wstring insertWide = Widen(insertNarrow);

            SendMessage(comboBoxBook, CB_INSERTSTRING, (WPARAM)i, (LPARAM)insertWide.c_str());
        }
    }

    void InsertToCBoxUser() {
        bool cont = true;
        int count = SendMessage(comboBoxUser, CB_GETCOUNT, (WPARAM)0, (LPARAM)0);
        int len;
        std::wstring name;
        std::string nameNarrow;

        for (int i = 0; i < userList.size(); i++) {
            for (int k = 0; k < count; k++) {
                len = SendMessage(comboBoxUser, CB_GETLBTEXTLEN, k, (LPARAM)0);
                name.resize(len);
                SendMessage(comboBoxUser, CB_GETLBTEXT, k, (LPARAM)&name.c_str()[0]);
                nameNarrow = Narrowen(name);
                if (userList[i].getName() == nameNarrow) {
                    cont = false;
                    break;
                }
            }

            if (cont == false) { cont = true; continue; }
            std::string insertNarrow = userList[i].getName();
            std::wstring insertWide = Widen(insertNarrow);

            SendMessage(comboBoxUser, CB_INSERTSTRING, (WPARAM)i, (LPARAM)insertWide.c_str());
        }
    }

    void UpdateWindowBook() {
        int selection = SendMessage(comboBoxBook, CB_GETCURSEL, (WPARAM)0, (LPARAM)0);

        if (selection == -1) {
            SendMessage(logID, WM_SETTEXT, (WPARAM)0, (LPARAM)L"");
            SendMessage(logName, WM_SETTEXT, (WPARAM)0, (LPARAM)L"");
            SendMessage(logIsOwned, WM_SETTEXT, (WPARAM)0, (LPARAM)L"");
            SendMessage(logTimeBorrow, WM_SETTEXT, (WPARAM)0, (LPARAM)L"");
            SendMessage(logOwnerID, WM_SETTEXT, (WPARAM)0, (LPARAM)L"");
        }
        else {
            int         bookID; //1
            std::string bookTitle; //2
            int         bookOwnerID; //3
            int         bookTimeBorrow; //4
            std::string bookPlaceNumber; //5
            std::string bookCopy; //6
            std::string bookLibrary; //7
            std::string bookSection; //8
            std::string bookCollection; //9
            std::string bookSubsection; //10
            std::string bookShape; //11
            std::string bookEnviroment;//12
            std::string bookLang; //13
            std::string bookAuthor; //14
            std::string bookResponsible; //15
            std::string bookYear; //16
            std::string bookISBN; //17
            std::string bookInfo; //18
            std::string bookPublisher; //19
            std::string bookEdition; //20
            std::string bookPhysAttrib; //21
            std::string bookSerialRec; //22
            std::string bookSubject; //23
            std::string bookNotes; //24

            std::wstring logText;

            for (int i = 0; i < bookList.size(); i++) {
                if (selection == i) {
                    bookID = bookList[i].getID();
                    bookTitle = bookList[i].getTitle();
                    bookOwnerID = bookList[i].getOwnerID();
                    bookTimeBorrow = bookList[i].getTimeBorrow();
                    bookPlaceNumber = bookList[i].GetPlaceNumber();
                    bookCopy = bookList[i].GetCopy();
                    bookLibrary = bookList[i].GetLibrary();
                    bookSection = bookList[i].GetSection();
                    bookCollection = bookList[i].GetCollection();
                    bookSubsection = bookList[i].GetSubSection();
                    bookShape = bookList[i].GetShape();
                    bookEnviroment = bookList[i].GetEnviroment();
                    bookLang = bookList[i].GetLang();
                    bookAuthor = bookList[i].GetAuthor();
                    bookResponsible = bookList[i].GetResponsible();
                    bookYear = bookList[i].GetYear();
                    bookISBN = bookList[i].GetISBN();
                    bookInfo = bookList[i].GetInfo();
                    bookPublisher = bookList[i].GetPublisher();
                    bookEdition = bookList[i].GetEdition();
                    bookPhysAttrib = bookList[i].GetPhysAttrib();
                    bookSerialRec = bookList[i].GetSerialRec();
                    bookSubject = bookList[i].GetSubject();
                    bookNotes = bookList[i].GetNotes();

                    logText = Widen(bookID);
                    SendMessage(logID, WM_SETTEXT, (WPARAM)0, (LPARAM)logText.c_str());
                    logText = Widen(bookTitle);
                    SendMessage(logTitle, WM_SETTEXT, (WPARAM)0, (LPARAM)logText.c_str());
                    if (bookOwnerID == 0) {
                        logText = L"No";
                        SendMessage(logIsOwned, WM_SETTEXT, (WPARAM)0, (LPARAM)logText.c_str());
                    }
                    else {
                        logText = L"Yes";
                        SendMessage(logIsOwned, WM_SETTEXT, (WPARAM)0, (LPARAM)logText.c_str());
                    }
                    logText = Widen(bookTimeBorrow);
                    SendMessage(logTimeBorrow, WM_SETTEXT, (WPARAM)0, (LPARAM)logText.c_str());
                    logText = Widen(bookOwnerID);
                    SendMessage(logOwnerID, WM_SETTEXT, (WPARAM)0, (LPARAM)logText.c_str());
                    logText = Widen(bookPlaceNumber);
                    SendMessage(logPlaceNumber, WM_SETTEXT, (WPARAM)0, (LPARAM)logText.c_str());
                    logText = Widen(bookCopy);
                    SendMessage(logCopy, WM_SETTEXT, (WPARAM)0, (LPARAM)logText.c_str());
                    logText = Widen(bookLibrary);
                    SendMessage(logLibrary, WM_SETTEXT, (WPARAM)0, (LPARAM)logText.c_str());
                    logText = Widen(bookSection);
                    SendMessage(logSection, WM_SETTEXT, (WPARAM)0, (LPARAM)logText.c_str());
                    logText = Widen(bookCollection);
                    SendMessage(logCollection, WM_SETTEXT, (WPARAM)0, (LPARAM)logText.c_str());
                    logText = Widen(bookSubsection);
                    SendMessage(logSubSection, WM_SETTEXT, (WPARAM)0, (LPARAM)logText.c_str());
                    logText = Widen(bookShape);
                    SendMessage(logShape, WM_SETTEXT, (WPARAM)0, (LPARAM)logText.c_str());
                    logText = Widen(bookEnviroment);
                    SendMessage(logEnviroment, WM_SETTEXT, (WPARAM)0, (LPARAM)logText.c_str());
                    logText = Widen(bookLang);
                    SendMessage(logLang, WM_SETTEXT, (WPARAM)0, (LPARAM)logText.c_str());
                    logText = Widen(bookAuthor);
                    SendMessage(logAuthor, WM_SETTEXT, (WPARAM)0, (LPARAM)logText.c_str());
                    logText = Widen(bookResponsible);
                    SendMessage(logResponsible, WM_SETTEXT, (WPARAM)0, (LPARAM)logText.c_str());
                    logText = Widen(bookYear);
                    SendMessage(logYear, WM_SETTEXT, (WPARAM)0, (LPARAM)logText.c_str());
                    logText = Widen(bookISBN);
                    SendMessage(logISBN, WM_SETTEXT, (WPARAM)0, (LPARAM)logText.c_str());
                    logText = Widen(bookInfo);
                    SendMessage(logInfo, WM_SETTEXT, (WPARAM)0, (LPARAM)logText.c_str());
                    logText = Widen(bookPublisher);
                    SendMessage(logPublisher, WM_SETTEXT, (WPARAM)0, (LPARAM)logText.c_str());
                    logText = Widen(bookEdition);
                    SendMessage(logEdition, WM_SETTEXT, (WPARAM)0, (LPARAM)logText.c_str());
                    logText = Widen(bookPhysAttrib);
                    SendMessage(logPhysAttrib, WM_SETTEXT, (WPARAM)0, (LPARAM)logText.c_str());
                    logText = Widen(bookSerialRec);
                    SendMessage(logSerialRec, WM_SETTEXT, (WPARAM)0, (LPARAM)logText.c_str());
                    logText = Widen(bookSubject);
                    SendMessage(logSubject, WM_SETTEXT, (WPARAM)0, (LPARAM)logText.c_str());
                    logText = Widen(bookNotes);
                    SendMessage(logNotes, WM_SETTEXT, (WPARAM)0, (LPARAM)logText.c_str());

                }
            }
        }
    }

    void UpdateWindowUser() {
        int selection = SendMessage(comboBoxUser, CB_GETCURSEL, (WPARAM)0, (LPARAM)0);

        if (selection == -1) {
            SendMessage(logID, WM_SETTEXT, (WPARAM)0, (LPARAM)L"");
            SendMessage(logTitle, WM_SETTEXT, (WPARAM)0, (LPARAM)L"");
            SendMessage(logIsOwned, WM_SETTEXT, (WPARAM)0, (LPARAM)L"");
            SendMessage(logTimeBorrow, WM_SETTEXT, (WPARAM)0, (LPARAM)L"");
            SendMessage(logOwnerID, WM_SETTEXT, (WPARAM)0, (LPARAM)L"");
        }
        else {
            int userID;
            std::string userName;
            int isMod;
            std::wstring logText;

            for (int i = 0; i < userList.size(); i++) {
                if (selection == i) {
                    userID = userList[i].getID();
                    userName = userList[i].getName();
                    isMod = userList[i].getMod();

                    logText = Widen(userID);
                    SendMessage(logID, WM_SETTEXT, (WPARAM)0, (LPARAM)logText.c_str());

                    logText = Widen(userName);
                    SendMessage(logName, WM_SETTEXT, (WPARAM)0, (LPARAM)logText.c_str());

                    logText = Widen(isMod);
                    SendMessage(logIsMod, WM_SETTEXT, (WPARAM)0, (LPARAM)logText.c_str());
                }
            }
        }
    }

    void AddBook() {
        std::wstring title;
        std::wstring placeNumber;
        std::wstring copy;
        std::wstring library;
        std::wstring section;
        std::wstring collection;
        std::wstring subsection;
        std::wstring shape;
        std::wstring enviroment;
        std::wstring lang;
        std::wstring author;
        std::wstring responsible;
        std::wstring year;
        std::wstring isbn;
        std::wstring info;
        std::wstring publisher;
        std::wstring edition;
        std::wstring physAttrib;
        std::wstring serialRec;
        std::wstring subject;
        std::wstring notes;
        int id;

        for (int i = 0; i <= bookList.size(); i++) {
            title.resize(SendMessage(logTitle, WM_GETTEXTLENGTH, (WPARAM)0, (LPARAM)0));
            SendMessage(logTitle, WM_GETTEXT, (WPARAM)title.size() + 1, (LPARAM)title.c_str());
            placeNumber.resize(SendMessage(logPlaceNumber, WM_GETTEXTLENGTH, (WPARAM)0, (LPARAM)0));
            SendMessage(logPlaceNumber, WM_GETTEXT, (WPARAM)placeNumber.size() + 1, (LPARAM)placeNumber.c_str());
            copy.resize(SendMessage(logCopy, WM_GETTEXTLENGTH, (WPARAM)0, (LPARAM)0));
            SendMessage(logCopy, WM_GETTEXT, (WPARAM)copy.size() + 1, (LPARAM)copy.c_str());
            library.resize(SendMessage(logLibrary, WM_GETTEXTLENGTH, (WPARAM)0, (LPARAM)0));
            SendMessage(logLibrary, WM_GETTEXT, (WPARAM)library.size() + 1, (LPARAM)library.c_str());
            section.resize(SendMessage(logSection, WM_GETTEXTLENGTH, (WPARAM)0, (LPARAM)0));
            SendMessage(logSection, WM_GETTEXT, (WPARAM)section.size() + 1, (LPARAM)section.c_str());
            collection.resize(SendMessage(logCollection, WM_GETTEXTLENGTH, (WPARAM)0, (LPARAM)0));
            SendMessage(logCollection, WM_GETTEXT, (WPARAM)collection.size() + 1, (LPARAM)collection.c_str());
            subsection.resize(SendMessage(logSubSection, WM_GETTEXTLENGTH, (WPARAM)0, (LPARAM)0));
            SendMessage(logSubSection, WM_GETTEXT, (WPARAM)subsection.size() + 1, (LPARAM)subsection.c_str());
            shape.resize(SendMessage(logShape, WM_GETTEXTLENGTH, (WPARAM)0, (LPARAM)0));
            SendMessage(logShape, WM_GETTEXT, (WPARAM)shape.size() + 1, (LPARAM)shape.c_str());
            enviroment.resize(SendMessage(logEnviroment, WM_GETTEXTLENGTH, (WPARAM)0, (LPARAM)0));
            SendMessage(logEnviroment, WM_GETTEXT, (WPARAM)enviroment.size() + 1, (LPARAM)enviroment.c_str());
            lang.resize(SendMessage(logLang, WM_GETTEXTLENGTH, (WPARAM)0, (LPARAM)0));
            SendMessage(logLang, WM_GETTEXT, (WPARAM)lang.size() + 1, (LPARAM)lang.c_str());
            author.resize(SendMessage(logAuthor, WM_GETTEXTLENGTH, (WPARAM)0, (LPARAM)0));
            SendMessage(logAuthor, WM_GETTEXT, (WPARAM)author.size() + 1, (LPARAM)author.c_str());
            responsible.resize(SendMessage(logResponsible, WM_GETTEXTLENGTH, (WPARAM)0, (LPARAM)0));
            SendMessage(logResponsible, WM_GETTEXT, (WPARAM)responsible.size() + 1, (LPARAM)responsible.c_str());
            year.resize(SendMessage(logYear, WM_GETTEXTLENGTH, (WPARAM)0, (LPARAM)0));
            SendMessage(logYear, WM_GETTEXT, (WPARAM)year.size() + 1, (LPARAM)year.c_str());
            isbn.resize(SendMessage(logISBN, WM_GETTEXTLENGTH, (WPARAM)0, (LPARAM)0));
            SendMessage(logISBN, WM_GETTEXT, (WPARAM)isbn.size() + 1, (LPARAM)isbn.c_str());
            info.resize(SendMessage(logInfo, WM_GETTEXTLENGTH, (WPARAM)0, (LPARAM)0));
            SendMessage(logInfo, WM_GETTEXT, (WPARAM)info.size() + 1, (LPARAM)info.c_str());
            publisher.resize(SendMessage(logPublisher, WM_GETTEXTLENGTH, (WPARAM)0, (LPARAM)0));
            SendMessage(logPublisher, WM_GETTEXT, (WPARAM)publisher.size() + 1, (LPARAM)publisher.c_str());
            edition.resize(SendMessage(logEdition, WM_GETTEXTLENGTH, (WPARAM)0, (LPARAM)0));
            SendMessage(logEdition, WM_GETTEXT, (WPARAM)edition.size() + 1, (LPARAM)edition.c_str());
            physAttrib.resize(SendMessage(logPhysAttrib, WM_GETTEXTLENGTH, (WPARAM)0, (LPARAM)0));
            SendMessage(logPhysAttrib, WM_GETTEXT, (WPARAM)physAttrib.size() + 1, (LPARAM)physAttrib.c_str());
            serialRec.resize(SendMessage(logSerialRec, WM_GETTEXTLENGTH, (WPARAM)0, (LPARAM)0));
            SendMessage(logSerialRec, WM_GETTEXT, (WPARAM)serialRec.size() + 1, (LPARAM)serialRec.c_str());
            subject.resize(SendMessage(logSubject, WM_GETTEXTLENGTH, (WPARAM)0, (LPARAM)0));
            SendMessage(logSubject, WM_GETTEXT, (WPARAM)subject.size() + 1, (LPARAM)subject.c_str());
            notes.resize(SendMessage(logNotes, WM_GETTEXTLENGTH, (WPARAM)0, (LPARAM)0));
            SendMessage(logNotes, WM_GETTEXT, (WPARAM)notes.size() + 1, (LPARAM)notes.c_str());

            if (i == bookList.size()) {
                if (bookList.empty()) {
                    id = 0;
                }
                else {
                    id = bookList.size() + 1;
                }
                ClassBook(
                    id,
                    Narrowen(title),
                    0,
                    0,
                    Narrowen(placeNumber),
                    Narrowen(copy),
                    Narrowen(library),
                    Narrowen(section),
                    Narrowen(collection),
                    Narrowen(subsection),
                    Narrowen(shape),
                    Narrowen(enviroment),
                    Narrowen(lang),
                    Narrowen(author),
                    Narrowen(responsible),
                    Narrowen(year),
                    Narrowen(isbn),
                    Narrowen(info),
                    Narrowen(publisher),
                    Narrowen(edition),
                    Narrowen(physAttrib),
                    Narrowen(serialRec),
                    Narrowen(subject),
                    Narrowen(notes)
                );
                saveDatabase();
                readDatabase();
                InsertToCBoxBook();

                MessageBox(m_hwnd, L"Addition successful.", L"Success", MB_OK);
                break;
            }
            else if (title.empty()) {
                MessageBox(m_hwnd, L"Books must have a name.", L"Error", MB_OK);
                break;
            }
            else if (Narrowen(title) == "Start book") {
                MessageBox(m_hwnd, L"A book's name cannot be \"Start book\".", L"Error", MB_OK);
                break;
            }
            else if (Narrowen(title) == "End book") {
                MessageBox(m_hwnd, L"A book's name cannot be \"End book\".", L"Error", MB_OK);
                break;
            }
            else if (Narrowen(title) == bookList[i].getTitle()) {
                MessageBox(m_hwnd, L"A book with this title already exists.", L"Error", MB_OK);
                break;
            }
        }
    }

    PCWSTR ClassName() const { return L"Main Window"; }
    LRESULT HandleMessage(UINT uMsg, WPARAM wparam, LPARAM lparam) {
        switch (uMsg) {

        case WM_CREATE: {
            loginUserBorder  = CreateWindow(WC_BUTTON, L"Login",    WS_VISIBLE | WS_CHILD | BS_GROUPBOX, colLoginBorder, rowLoginBorder, 120, 100, m_hwnd, NULL, NULL, NULL);
            loginUserBox     = CreateWindow(WC_STATIC, L"",         WS_CHILD | WS_BORDER, colLoginUser, rowLoginUser, 80, 20, m_hwnd, NULL, NULL, NULL);
            loginPasswordBox = CreateWindow(WC_STATIC, L"",         WS_CHILD | WS_BORDER, colLoginPassword, rowLoginPassword, 80, 20, m_hwnd, NULL, NULL, NULL);
            loginUser        = CreateWindow(WC_EDIT,   L"",         WS_VISIBLE | WS_CHILD | WS_BORDER | ES_AUTOHSCROLL, colLoginUser, rowLoginUser, 80, 20, m_hwnd, NULL, NULL, NULL);
            loginPassword    = CreateWindow(WC_EDIT,   L"",         WS_VISIBLE | WS_CHILD | WS_BORDER | ES_AUTOHSCROLL, colLoginPassword, rowLoginPassword, 80, 20, m_hwnd, NULL, NULL, NULL);
            buttonLogin      = CreateWindow(WC_BUTTON, L"Login",    WS_VISIBLE | WS_CHILD | WS_BORDER, colButtonLogin, rowButtonLogin, 50, 20, m_hwnd, NULL, NULL, NULL);
            buttonRegister   = CreateWindow(WC_BUTTON, L"Register", WS_VISIBLE | WS_CHILD | WS_BORDER, colButtonRegister, rowButtonRegister, 60, 20, m_hwnd, NULL, NULL, NULL);
            buttonLogout     = CreateWindow(WC_BUTTON, L"Logout",                WS_CHILD | WS_BORDER, colButtonLogout, rowButtonLogout, 50, 20, m_hwnd, NULL, NULL, NULL);

            logID          = CreateWindow(WC_EDIT, L"", WS_VISIBLE | WS_CHILD | WS_BORDER | ES_AUTOHSCROLL, colLogID, rowLogID, 150, 20, m_hwnd, NULL, NULL, NULL); //1
            logTitle       = CreateWindow(WC_EDIT, L"", WS_VISIBLE | WS_CHILD | WS_BORDER | ES_AUTOHSCROLL, colLogTitle, rowLogTitle, 150, 20, m_hwnd, NULL, NULL, NULL); //2
            logIsOwned     = CreateWindow(WC_EDIT, L"", WS_VISIBLE | WS_CHILD | WS_BORDER | ES_AUTOHSCROLL, colLogIsOwned, rowLogIsOwned, 150, 20, m_hwnd, NULL, NULL, NULL); //3
            logTimeBorrow  = CreateWindow(WC_EDIT, L"", WS_VISIBLE | WS_CHILD | WS_BORDER | ES_AUTOHSCROLL, colLogTimeBorrow, rowLogTimeBorrow, 150, 20, m_hwnd, NULL, NULL, NULL); //4
            logOwnerID     = CreateWindow(WC_EDIT, L"", WS_VISIBLE | WS_CHILD | WS_BORDER | ES_AUTOHSCROLL, colLogOwnerID, rowLogOwnerID, 150, 20, m_hwnd, NULL, NULL, NULL); //5
            logPlaceNumber = CreateWindow(WC_EDIT, L"", WS_VISIBLE | WS_CHILD | WS_BORDER | ES_AUTOHSCROLL, colLogPlaceNumber, rowLogPlaceNumber, 150, 20, m_hwnd, NULL, NULL, NULL); //7
            logCopy        = CreateWindow(WC_EDIT, L"", WS_VISIBLE | WS_CHILD | WS_BORDER | ES_AUTOHSCROLL, colLogCopy, rowLogCopy, 150, 20, m_hwnd, NULL, NULL, NULL); //8
            logLibrary     = CreateWindow(WC_EDIT, L"", WS_VISIBLE | WS_CHILD | WS_BORDER | ES_AUTOHSCROLL, colLogLibrary, rowLogLibrary, 150, 20, m_hwnd, NULL, NULL, NULL); //9
            logSection     = CreateWindow(WC_EDIT, L"", WS_VISIBLE | WS_CHILD | WS_BORDER | ES_AUTOHSCROLL, colLogSection, rowLogSection, 150, 20, m_hwnd, NULL, NULL, NULL); //10
            logCollection  = CreateWindow(WC_EDIT, L"", WS_VISIBLE | WS_CHILD | WS_BORDER | ES_AUTOHSCROLL, colLogCollection, rowLogCollection, 150, 20, m_hwnd, NULL, NULL, NULL); //11
            logSubSection  = CreateWindow(WC_EDIT, L"", WS_VISIBLE | WS_CHILD | WS_BORDER | ES_AUTOHSCROLL, colLogSubSection, rowLogSubSection, 150, 20, m_hwnd, NULL, NULL, NULL); //12
            logShape       = CreateWindow(WC_EDIT, L"", WS_VISIBLE | WS_CHILD | WS_BORDER | ES_AUTOHSCROLL, colLogShape, rowLogShape, 150, 20, m_hwnd, NULL, NULL, NULL); //13
            logEnviroment  = CreateWindow(WC_EDIT, L"", WS_VISIBLE | WS_CHILD | WS_BORDER | ES_AUTOHSCROLL, colLogEnviroment, rowLogEnviroment, 150, 20, m_hwnd, NULL, NULL, NULL); //14
            logLang        = CreateWindow(WC_EDIT, L"", WS_VISIBLE | WS_CHILD | WS_BORDER | ES_AUTOHSCROLL, colLogLang, rowLogLang, 150, 20, m_hwnd, NULL, NULL, NULL); //15
            logAuthor      = CreateWindow(WC_EDIT, L"", WS_VISIBLE | WS_CHILD | WS_BORDER | ES_AUTOHSCROLL, colLogAuthor, rowLogAuthor, 150, 20, m_hwnd, NULL, NULL, NULL); //16
            logResponsible = CreateWindow(WC_EDIT, L"", WS_VISIBLE | WS_CHILD | WS_BORDER | ES_AUTOHSCROLL, colLogResponsible, rowLogResponsible, 150, 20, m_hwnd, NULL, NULL, NULL); //17
            logYear        = CreateWindow(WC_EDIT, L"", WS_VISIBLE | WS_CHILD | WS_BORDER | ES_AUTOHSCROLL, colLogYear, rowLogYear, 150, 20, m_hwnd, NULL, NULL, NULL); //18
            logISBN        = CreateWindow(WC_EDIT, L"", WS_VISIBLE | WS_CHILD | WS_BORDER | ES_AUTOHSCROLL, colLogISBN, rowLogISBN, 150, 20, m_hwnd, NULL, NULL, NULL); //19
            logInfo        = CreateWindow(WC_EDIT, L"", WS_VISIBLE | WS_CHILD | WS_BORDER | ES_AUTOHSCROLL, colLogInfo, rowLogInfo, 150, 20, m_hwnd, NULL, NULL, NULL); //20
            logPublisher   = CreateWindow(WC_EDIT, L"", WS_VISIBLE | WS_CHILD | WS_BORDER | ES_AUTOHSCROLL, colLogPublisher, rowLogPublisher, 150, 20, m_hwnd, NULL, NULL, NULL); //21
            logEdition     = CreateWindow(WC_EDIT, L"", WS_VISIBLE | WS_CHILD | WS_BORDER | ES_AUTOHSCROLL, colLogEdition, rowLogEdition, 150, 20, m_hwnd, NULL, NULL, NULL); //22
            logPhysAttrib  = CreateWindow(WC_EDIT, L"", WS_VISIBLE | WS_CHILD | WS_BORDER | ES_AUTOHSCROLL, colLogPhysAttrib, rowLogPhysAttrib, 150, 20, m_hwnd, NULL, NULL, NULL); //23
            logSerialRec   = CreateWindow(WC_EDIT, L"", WS_VISIBLE | WS_CHILD | WS_BORDER | ES_AUTOHSCROLL, colLogSerialRec, rowLogSerialRec, 150, 20, m_hwnd, NULL, NULL, NULL); //24
            logSubject     = CreateWindow(WC_EDIT, L"", WS_VISIBLE | WS_CHILD | WS_BORDER | ES_AUTOHSCROLL, colLogSubject, rowLogSubject, 150, 20, m_hwnd, NULL, NULL, NULL); //25
            logNotes       = CreateWindow(WC_EDIT, L"", WS_VISIBLE | WS_CHILD | WS_BORDER | ES_AUTOHSCROLL, colLogNotes, rowLogNotes, 150, 20, m_hwnd, NULL, NULL, NULL); //26
            logName        = CreateWindow(WC_EDIT, L"",              WS_CHILD | WS_BORDER | ES_AUTOHSCROLL, colLogTitle, rowLogTitle, 150, 20, m_hwnd, NULL, NULL, NULL); //27
            logIsMod       = CreateWindow(WC_EDIT, L"",              WS_CHILD | WS_BORDER | ES_AUTOHSCROLL, colLogIsOwned, rowLogIsOwned, 150, 20, m_hwnd, NULL, NULL, NULL); //28

            textID          = CreateWindow(WC_STATIC, L"ID",              WS_VISIBLE | WS_CHILD | WS_BORDER, colTextID, rowTextID, 90, 20, m_hwnd, NULL, NULL, NULL); //1
            textTitle       = CreateWindow(WC_STATIC, L"Title",           WS_VISIBLE | WS_CHILD | WS_BORDER, colTextTitle, rowTextTitle, 90, 20, m_hwnd, NULL, NULL, NULL); //2
            textIsOwned     = CreateWindow(WC_STATIC, L"Is Owned",        WS_VISIBLE | WS_CHILD | WS_BORDER, colTextIsOwned, rowTextIsOwned, 90, 20, m_hwnd, NULL, NULL, NULL); //3
            textTimeBorrow  = CreateWindow(WC_STATIC, L"Time Borrow",     WS_VISIBLE | WS_CHILD | WS_BORDER, colTextTimeBorrow, rowTextTimeBorrow, 90, 20, m_hwnd, NULL, NULL, NULL); //4
            textOwnerID     = CreateWindow(WC_STATIC, L"Owner ID",        WS_VISIBLE | WS_CHILD | WS_BORDER, colTextOwnerID, rowTextOwnerID, 90, 20, m_hwnd, NULL, NULL, NULL); //5
            textPlaceNumber = CreateWindow(WC_STATIC, L"Place Number",    WS_VISIBLE | WS_CHILD | WS_BORDER, colTextPlaceNumber, rowTextPlaceNumber, 90, 20, m_hwnd, NULL, NULL, NULL); //7
            textCopy        = CreateWindow(WC_STATIC, L"Copy",            WS_VISIBLE | WS_CHILD | WS_BORDER, colTextCopy, rowTextCopy, 90, 20, m_hwnd, NULL, NULL, NULL); //8
            textLibrary     = CreateWindow(WC_STATIC, L"Library",         WS_VISIBLE | WS_CHILD | WS_BORDER, colTextLibrary, rowTextLibrary, 90, 20, m_hwnd, NULL, NULL, NULL); //9
            textSection     = CreateWindow(WC_STATIC, L"Section",         WS_VISIBLE | WS_CHILD | WS_BORDER, colTextSection, rowTextSection, 90, 20, m_hwnd, NULL, NULL, NULL); //10
            textCollection  = CreateWindow(WC_STATIC, L"Collection",      WS_VISIBLE | WS_CHILD | WS_BORDER, colTextCollection, rowTextCollection, 90, 20, m_hwnd, NULL, NULL, NULL); //11
            textSubSection  = CreateWindow(WC_STATIC, L"Subsection",      WS_VISIBLE | WS_CHILD | WS_BORDER, colTextSubSection, rowTextSubSection, 90, 20, m_hwnd, NULL, NULL, NULL); //12
            textShape       = CreateWindow(WC_STATIC, L"Shape",           WS_VISIBLE | WS_CHILD | WS_BORDER, colTextShape, rowTextShape, 90, 20, m_hwnd, NULL, NULL, NULL); //13
            textEnviroment  = CreateWindow(WC_STATIC, L"Enviroment",      WS_VISIBLE | WS_CHILD | WS_BORDER, colTextEnviroment, rowTextEnviroment, 90, 20, m_hwnd, NULL, NULL, NULL); //14
            textLang        = CreateWindow(WC_STATIC, L"Language",        WS_VISIBLE | WS_CHILD | WS_BORDER, colTextLang, rowTextLang, 90, 20, m_hwnd, NULL, NULL, NULL); //15
            textAuthor      = CreateWindow(WC_STATIC, L"Author",          WS_VISIBLE | WS_CHILD | WS_BORDER, colTextAuthor, rowTextAuthor, 90, 20, m_hwnd, NULL, NULL, NULL); //16
            textResponsible = CreateWindow(WC_STATIC, L"Responsible",     WS_VISIBLE | WS_CHILD | WS_BORDER, colTextResponsible, rowTextResponsible, 90, 20, m_hwnd, NULL, NULL, NULL); //17
            textYear        = CreateWindow(WC_STATIC, L"Date",            WS_VISIBLE | WS_CHILD | WS_BORDER, colTextYear, rowTextYear, 90, 20, m_hwnd, NULL, NULL, NULL); //18
            textISBN        = CreateWindow(WC_STATIC, L"ISBN",            WS_VISIBLE | WS_CHILD | WS_BORDER, colTextISBN, rowTextISBN, 90, 20, m_hwnd, NULL, NULL, NULL); //19
            textInfo        = CreateWindow(WC_STATIC, L"Publishing Info", WS_VISIBLE | WS_CHILD | WS_BORDER, colTextInfo, rowTextInfo, 90, 20, m_hwnd, NULL, NULL, NULL); //20
            textPublisher   = CreateWindow(WC_STATIC, L"Publisher",       WS_VISIBLE | WS_CHILD | WS_BORDER, colTextPublisher, rowTextPublisher, 90, 20, m_hwnd, NULL, NULL, NULL); //21
            textEdition     = CreateWindow(WC_STATIC, L"Edition",         WS_VISIBLE | WS_CHILD | WS_BORDER, colTextEdition, rowTextEdition, 90, 20, m_hwnd, NULL, NULL, NULL); //22
            textPhysAttrib  = CreateWindow(WC_STATIC, L"Attributes",      WS_VISIBLE | WS_CHILD | WS_BORDER, colTextPhysAttrib, rowTextPhysAttrib, 90, 20, m_hwnd, NULL, NULL, NULL); //23
            textSerialRec   = CreateWindow(WC_STATIC, L"Serial Record",   WS_VISIBLE | WS_CHILD | WS_BORDER, colTextSerialRec, rowTextSerialRec, 90, 20, m_hwnd, NULL, NULL, NULL); //24
            textSubject     = CreateWindow(WC_STATIC, L"Subjects",        WS_VISIBLE | WS_CHILD | WS_BORDER, colTextSubject, rowTextSubject, 90, 20, m_hwnd, NULL, NULL, NULL); //25
            textNotes       = CreateWindow(WC_STATIC, L"Notes",           WS_VISIBLE | WS_CHILD | WS_BORDER, colTextNotes, rowTextNotes, 90, 20, m_hwnd, NULL, NULL, NULL); //26
            textName        = CreateWindow(WC_STATIC, L"Name",                         WS_CHILD | WS_BORDER, colTextTitle, rowTextTitle, 90, 20, m_hwnd, NULL, NULL, NULL); //27
            textIsMod       = CreateWindow(WC_STATIC, L"Is Mod",                       WS_CHILD | WS_BORDER, colTextIsOwned, rowTextIsOwned, 90, 20, m_hwnd, NULL, NULL, NULL); //28

            buttonBorrow  = CreateWindow(WC_BUTTON, L"Borrow", WS_VISIBLE | WS_CHILD | WS_BORDER, colBorrow, rowBorrow, 60, 20, m_hwnd, NULL, NULL, NULL);
            buttonAdd     = CreateWindow(WC_BUTTON, L"Add",                 WS_CHILD | WS_BORDER, colAdd, rowAdd, 60, 20, m_hwnd, NULL, NULL, NULL);
            buttonDelete  = CreateWindow(WC_BUTTON, L"Delete",              WS_CHILD | WS_BORDER, colDelete, rowDelete, 60, 20, m_hwnd, NULL, NULL, NULL);
            buttonMakeMod = CreateWindow(WC_BUTTON, L"Make Mod",            WS_CHILD | WS_BORDER, colMakeMod, rowMakeMod, 80, 20, m_hwnd, NULL, NULL, NULL);

            comboBoxPrimary = CreateWindow(WC_COMBOBOX, L"",              WS_CHILD | WS_OVERLAPPED | CBS_DROPDOWNLIST | CBS_DISABLENOSCROLL | CBS_HASSTRINGS, colCBoxPrim, rowCBoxPrim, 80, 500, m_hwnd, NULL, NULL, NULL);
            comboBoxBook    = CreateWindow(WC_COMBOBOX, L"", WS_VISIBLE | WS_CHILD | WS_OVERLAPPED | CBS_DROPDOWNLIST | CBS_DISABLENOSCROLL | CBS_HASSTRINGS, colCBoxSec, rowCBoxSec, 100, 500, m_hwnd, NULL, NULL, NULL);
            comboBoxUser    = CreateWindow(WC_COMBOBOX, L"",              WS_CHILD | WS_OVERLAPPED | CBS_DROPDOWNLIST | CBS_DISABLENOSCROLL | CBS_HASSTRINGS, colCBoxSec, rowCBoxSec, 100, 500, m_hwnd, NULL, NULL, NULL);

            buttonCancel = CreateWindow(WC_BUTTON, L"Cancel", WS_CHILD | WS_BORDER, colCancel, rowCancel, 60, 20, m_hwnd, NULL, NULL, NULL);
            buttonAddAlt = CreateWindow(WC_BUTTON, L"Add",    WS_CHILD | WS_BORDER, colAddAlt, rowAddAlt, 60, 20, m_hwnd, NULL, NULL, NULL);

            SendMessage(comboBoxPrimary, CB_ADDSTRING, (WPARAM)0, (LPARAM)L"Books");
            SendMessage(comboBoxPrimary, CB_ADDSTRING, (WPARAM)0, (LPARAM)L"Users");
            SendMessage(comboBoxPrimary, CB_SETCURSEL, (WPARAM)0, (LPARAM)0);

            if (!bookList.empty()) {
                InsertToCBoxBook();
                SendMessage(comboBoxBook, CB_SETCURSEL, (WPARAM)0, (LPARAM)0);
            }
            else {
                SendMessage(comboBoxBook, CB_SETCURSEL, (WPARAM)-1, (LPARAM)0);
            }

            if (!userList.empty()) {
                InsertToCBoxUser();
                SendMessage(comboBoxUser, CB_SETCURSEL, (WPARAM)0, (LPARAM)0);
            }
            else {
                SendMessage(comboBoxUser, CB_SETCURSEL, (WPARAM)-1, (LPARAM)0);
            }
        }
            return 0;

        case WM_COMMAND: {
            if (HIWORD(wparam) == BN_CLICKED) {
                if (lparam == LPARAM(buttonBorrow)) {
                    if (BorrowBook() != -1) {
                        saveDatabase();
                        readDatabase();
                        
                        UpdateWindowBook();
                    }
                }
                else if (lparam == LPARAM(buttonAdd)) {
                    SwitchToAdd();
                }
                else if (lparam == LPARAM(buttonCancel)) {
                    SwitchToMain();
                }
                else if (lparam == LPARAM(buttonAddAlt)) {
                    int confirm = MessageBox(m_hwnd, L"Do you want add a book with these attributes?", L"Confirm", MB_OKCANCEL);
                    if (confirm == IDOK) {
                        AddBook();
                    }
                }
                else if (lparam == LPARAM(buttonLogin)) {
                    std::wstring name;
                    std::wstring password;
                    name.resize(SendMessage(loginUser, WM_GETTEXTLENGTH, (WPARAM)0, (LPARAM)0));
                    password.resize(SendMessage(loginPassword, WM_GETTEXTLENGTH, (WPARAM)0, (LPARAM)0));
                    SendMessage(loginUser, WM_GETTEXT, (WPARAM)name.size() + 1, (LPARAM)name.c_str());
                    SendMessage(loginPassword, WM_GETTEXT, (WPARAM)password.size() + 1, (LPARAM)password.c_str());

                    int feedback = Login(Narrowen(name), Narrowen(password));
                    if (feedback == -1) {
                        MessageBox(m_hwnd, L"Could not find this user.", L"Error", MB_OK);
                    }
                    else if (feedback == -2) {
                        MessageBox(m_hwnd, L"Password is incorrect.", L"Error", MB_OK);
                    }
                    else {
                        SwitchLogin(1);

                        MessageBox(m_hwnd, L"Login successful.", L"Success", MB_OK);
                    }
                }
                else if (lparam == LPARAM(buttonLogout)) {
                        SwitchLogin(0);
                        Logout();
                        MessageBox(m_hwnd, L"Logout successful.", L"Success", MB_OK);
                }
                else if (lparam == LPARAM(buttonRegister)) {
                    int confirm = MessageBox(m_hwnd, L"Do you want to register a user with this name and password?", L"Confirm", MB_OKCANCEL);
                    if (confirm == IDOK) {
                        std::wstring name;
                        std::wstring password;

                        for (int i = 0; i <= userList.size(); i++) {
                            name.resize(SendMessage(loginUser, WM_GETTEXTLENGTH, (WPARAM)0, (LPARAM)0));
                            password.resize(SendMessage(loginPassword, WM_GETTEXTLENGTH, (WPARAM)0, (LPARAM)0));
                            SendMessage(loginUser, WM_GETTEXT, (WPARAM)name.size() + 1, (LPARAM)name.c_str());
                            SendMessage(loginPassword, WM_GETTEXT, (WPARAM)password.size() + 1, (LPARAM)password.c_str());

                            if (i == userList.size()) {
                                ClassUser(userList.size(), Narrowen(name), Narrowen(password), 0);
                                saveDatabase();
                                readDatabase();
                                InsertToCBoxUser();

                                Login(Narrowen(name), Narrowen(password));
                                SwitchLogin(1);
                                MessageBox(m_hwnd, L"Register successful.", L"Success", MB_OK);
                                break;
                            }
                            else if (name.empty()) {
                                MessageBox(m_hwnd, L"Users must have a name.", L"Error", MB_OK);
                                break;
                            }
                            else if (Narrowen(name) == "Start user") {
                                MessageBox(m_hwnd, L"A book's name cannot be \"Start user\".", L"Error", MB_OK);
                                break;
                            }
                            else if (Narrowen(name) == "End book") {
                                MessageBox(m_hwnd, L"A book's name cannot be \"End user\".", L"Error", MB_OK);
                                break;
                            }
                            else if (Narrowen(name) == userList[i].getName()) {
                                MessageBox(m_hwnd, L"This name has already been taken.", L"Error", MB_OK);
                                break;
                            }
                        }
                    }
                }
                else if (lparam == LPARAM(buttonDelete)) {
                    int bookID = SendMessage(comboBoxBook, CB_GETCURSEL, (WPARAM)0, (LPARAM)0);
                    int userID = SendMessage(comboBoxUser, CB_GETCURSEL, (WPARAM)0, (LPARAM)0);
                    int selection = SendMessage(comboBoxPrimary, CB_GETCURSEL, (WPARAM)0, (LPARAM)0);

                    if (selection == 0) {
                        if (MessageBox(m_hwnd, L"Are you sure you want to delete this book?", L"Confirm", MB_OKCANCEL) == IDOK) {
                            for (int i = 0; i <= bookList.size(); i++)
                            {
                                if (i == bookList.size()) {
                                    MessageBox(m_hwnd, L"Could not find this book.", L"Error", MB_OK);
                                    break;
                                }
                                if (i == bookID) {
                                    DeleteBook(bookID);
                                    saveDatabase();
                                    readDatabase();
                                    int selection = SendMessage(comboBoxBook, CB_GETCURSEL, (WPARAM)0, (LPARAM)0);
                                    SendMessage(comboBoxBook, CB_RESETCONTENT, (WPARAM)0, (LPARAM)0);
                                    if (selection >= bookList.size() - 1) {
                                        SendMessage(comboBoxBook, CB_SETCURSEL, (WPARAM)0, (LPARAM)0);
                                    }
                                    else {
                                        SendMessage(comboBoxBook, CB_SETCURSEL, (WPARAM)selection, (LPARAM)0);
                                    }
                                    InsertToCBoxBook();
                                    UpdateWindowBook();
                                    break;
                                }
                            }
                        }
                    }
                    else {
                        if (userList.size() == 0) {
                            MessageBox(m_hwnd, L"You cannot delete the only remaining user.", L"Error", MB_OK);
                        }
                        else {
                            if (MessageBox(m_hwnd, L"Are you sure you want to delete this user?", L"Confirm", MB_OKCANCEL) == IDOK) {
                                for (int i = 0; i <= userList.size(); i++) {
                                    if (i == userList.size()) {
                                        MessageBox(m_hwnd, L"Could not find this user.", L"Error", MB_OK);
                                        break;
                                    }
                                    if (i == userID) {
                                        if (userList[i].getLogin()) {
                                            SwitchLogin(0);
                                            Logout();
                                        }
                                        DeleteUser(userID);
                                        saveDatabase();
                                        readDatabase();
                                        int selection = SendMessage(comboBoxUser, CB_GETCURSEL, (WPARAM)0, (LPARAM)0);
                                        SendMessage(comboBoxUser, CB_RESETCONTENT, (WPARAM)0, (LPARAM)0);
                                        if (selection >= userList.size() - 1) {
                                            SendMessage(comboBoxUser, CB_SETCURSEL, (WPARAM)0, (LPARAM)0);
                                        }
                                        else {
                                            SendMessage(comboBoxUser, CB_SETCURSEL, (WPARAM)selection, (LPARAM)0);
                                        }
                                        InsertToCBoxUser();
                                        UpdateWindowUser();
                                        break;
                                    }
                                }
                            }
                        }
                    }
                }
                else if (lparam == LPARAM(buttonMakeMod)) {
                    int userID = SendMessage(comboBoxUser, CB_GETCURSEL, (WPARAM)0, (LPARAM)0);

                    if (userID != -1) {

                        if (MessageBox(m_hwnd, L"Are you sure you want to make this user a moderator?", L"Confirm", MB_OKCANCEL) == IDOK) {
                            for (int i = 0; i <= userList.size(); i++) {
                                if (i == userList.size()) {
                                    MessageBox(m_hwnd, L"Could not find this user.", L"Error", MB_OK);
                                    break;
                                }
                                if (i == userID) {
                                    userList[i].SetMod(true);
                                    UpdateUser(userID);
                                    MessageBox(m_hwnd, L"User is now a moderator.", L"Success", MB_OK);
                                    saveDatabase();
                                    readDatabase();
                                    UpdateWindowUser();
                                    break;
                                }
                            }
                        }
                    }
                }
                return 0;
            }

            else if (HIWORD(wparam) == CBN_SELCHANGE) {

                if (lparam == LPARAM(comboBoxPrimary)) {
                    int selection = SendMessage(comboBoxPrimary, CB_GETCURSEL, (WPARAM)0, (LPARAM)0);
                    
                    if (selection == 0) {
                        SwitchToBook();
                    }
                    else if (selection == 1) {
                        SwitchToUser();
                    }
                }
                else if (lparam == LPARAM(comboBoxBook)) {
                    UpdateWindowBook();
                }
                else if (lparam == LPARAM(comboBoxUser)) {
                    UpdateWindowUser();
                }
                return 0;
            }
        }
            return 0;

        case WM_DESTROY:
            PostQuitMessage(0);
            return 0;

        case WM_PAINT:{
            PAINTSTRUCT ps;
            HDC hdc = BeginPaint(m_hwnd, &ps);
            FillRect(hdc, &ps.rcPaint, (HBRUSH)(COLOR_WINDOW));
            EndPaint(m_hwnd, &ps);
        }
            return 0;

        default:
            return DefWindowProc(m_hwnd, uMsg, wparam, lparam);
        }
        return TRUE;
    }
};
