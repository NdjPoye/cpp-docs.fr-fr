---
title: "Navigation dans le syst&#232;me de fichiers | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: f7cc5f5e-a541-4e00-87c7-a3769ef6096d
caps.latest.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# Navigation dans le syst&#232;me de fichiers
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

L’en\-tête \<filesystem\> implémente le projet de spécification technique de système de fichiers \(File System Technical Specification\) \([ISO\/IEC JTC 1\/SC 22\/WG 21 N4100](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n4100.pdf)\), et a des types et des fonctions qui vous permettent d’écrire du code indépendant des plateformes pour naviguer dans le système de fichiers. Comme il est interplateforme, il contient des API qui ne s'appliquent pas aux systèmes Windows. Par exemple, cela signifie que `is_fifo(const path&)` retourne toujours `false` sur Windows. L’en\-tête est une basée sur un projet de spécification technique qui n’a pas encore été inclus dans la norme C\+\+17 au moment de la réalisation de Visual Studio 2015 RTM. Ses membres sont trouvent dans l’espace de noms `std::experimental::filesystem::v1`.  
  
## Vue d'ensemble  
 Utilisez les API \<filesystem\> pour les tâches suivantes :  
  
-   effectuer une itération des fichiers et répertoires sous un chemin d'accès spécifié ;  
  
-   obtenir des informations sur les fichiers \(date de création, taille, extension, répertoire racine, etc.\) ;  
  
-   composer, décomposer et comparer des chemins d'accès ;  
  
-   créer, copier et supprimer des répertoires ;  
  
-   copier et supprimer des fichiers.  
  
 Pour plus d'informations sur les E\/S de fichiers avec la bibliothèque standard, voir [iostream, programmation](../standard-library/iostream-programming.md).  
  
## Chemins d'accès  
  
### Construction et composition de chemins d'accès  
 Dans Windows \(depuis XP\), les chemins d'accès sont stockés en mode natif au format Unicode. La classe [path](../standard-library/path-class-cpp-standard-template-library.md) effectue automatiquement toutes les conversions de chaînes nécessaires. Elle accepte les arguments des tableaux de caractères larges et étroits, ainsi que des types `std::string` et `std::wstring` au format UTF8 ou UTF16. La classe `path` normalise aussi automatiquement les séparateurs des chemins. Vous pouvez utiliser une seule barre oblique comme séparateur de répertoires dans les arguments de constructeur. Cela vous permet d'utiliser les mêmes chaînes pour stocker des chemins d'accès dans les environnements Windows et UNIX :  
  
```cpp  
path pathToDisplay(L"/FileSystemTest/SubDir3"); // OK! path pathToDisplay2(L"\\FileSystemTest\\SubDir3"); // Still OK as always path pathToDisplay3(LR"(\FileSystemTest\SubDir3)"); // Raw string literals are OK, too.  
```  
  
 Pour concaténer deux chemins, utilisez les opérateurs  `/` et `/=` surchargés, qui sont similaires aux opérateurs `+` et `+=` sur `std::string` et `std::wstring`. Si vous n’indiquez pas ces opérateurs, l’objet `path` les fournit.  
  
```cpp  
path myRoot("C:/FileSystemTest"); // no trailing separator, no problem! myRoot /= path("SubDirRoot"); // C:/FileSystemTest/SubDirRoot  
```  
  
### Examen des chemins d'accès  
 La classe path contient plusieurs méthodes qui retournent des informations sur différents éléments du chemin d'accès proprement dit, de manière distincte de l'entité système de fichiers à laquelle il fait référence. Vous pouvez ainsi obtenir la racine, le chemin d'accès relatif, le nom et l'extension de fichier, etc. Vous pouvez itérer un objet path pour examiner tous les répertoires de l'arborescence. L'exemple suivant montre comment itérer un chemin d'accès \(pas le répertoire qu'il référence\) et récupérer des informations sur les éléments qui le composent.  
  
```cpp  
  
#include <string> #include <iostream> #include <sstream> #include <filesystem> using namespace std; using namespace std::experimental::filesystem::v1; wstring  DisplayPathInfo() { // This path may or may not refer to an existing file. We are // examining this path string, not file system objects. path pathToDisplay(L"C:/FileSystemTest/SubDir3/SubDirLevel2/File2.txt "); wostringstream wos; int i = 0; wos << L"Displaying path info for: " << pathToDisplay << endl; for (path::iterator itr = pathToDisplay.begin(); itr != pathToDisplay.end(); ++itr) { wos << L"path part: " << i++ << L" = " << *itr << endl; } wos << L"root_name() = " << pathToDisplay.root_name() << endl << L"root_path() = " << pathToDisplay.root_path() << endl << L"relative_path() = " << pathToDisplay.relative_path() << endl << L"parent_path() = " << pathToDisplay.parent_path() << endl << L"filename() = " << pathToDisplay.filename() << endl << L"stem() = " << pathToDisplay.stem() << endl << L"extension() = " << pathToDisplay.extension() << endl; return wos.str(); } void main(int argc, char* argv[]) { wcout << DisplayPathInfo() << endl; // wcout << ComparePaths() << endl; // see following example wcout << endl << L"Press Enter to exit" << endl; wstring input; getline(wcin, input); }  
```  
  
 Le code génère cette sortie :  
  
```cpp  
Displaying path info for: C:\FileSystemTest\SubDir3\SubDirLevel2\File2.txt path part: 0 = C: path part: 1 = \ path part: 2 = FileSystemTest path part: 3 = SubDir3 path part: 4 = SubDirLevel2 path part: 5 = File2.txt root_name() = C: root_path() = C:\ relative_path() = FileSystemTest\SubDir3\SubDirLevel2\File2.txt parent_path() = C:\FileSystemTest\SubDir3\SubDirLevel2 filename() = File2.txt stem() = File2 extension() = .txt  
```  
  
### Comparaison des chemins d'accès  
 La classe `path` surcharge les mêmes opérateurs de comparaison que `std::string` et `std::wstring`. Quand vous comparez deux chemins d'accès, vous effectuez une comparaison de chaînes une fois que les séparateurs ont été normalisés. Si une barre oblique de fin \(ou barre oblique inverse\) est manquante, elle n'est pas ajoutée, ce qui a une incidence sur la comparaison. L'exemple suivant montre comment les valeurs de chemin d'accès sont comparées :  
  
```cpp  
  
wstring ComparePaths() { path p0(L"C:/Documents"); // no trailing separator path p1(L"C:/Documents/"); //p0 < p1 path p2(L"C:/Documents/2013/"); // p1 < p2 path p3(L"C:/Documents/2013/Reports/"); // p2 < p3 path p4(L"C:/Documents/2014/");  // p3 < p4 path p5(L"D:/Documents/2013/Reports/"); // p4 < p5 wostringstream wos; wos << boolalpha << p0.wstring() << L" < " << p1.wstring() << L": " << (p0 < p1) << endl << p1.wstring() << L" < " << p2.wstring() << L": " << (p1 < p2) << endl << p2.wstring() << L" < " << p3.wstring() << L": " << (p2 < p3) << endl << p3.wstring() << L" < " << p4.wstring() << L": " << (p3 < p4) << endl << p4.wstring() << L" < " << p5.wstring() << L": " << (p4 < p5) << endl; return wos.str(); } /* Output: C:\Documents < C:\Documents\: true C:\Documents\ < C:\Documents\2013\: true C:\Documents\2013\ < C:\Documents\2013\Reports\: true C:\Documents\2013\Reports\ < C:\Documents\2014\: true C:\Documents\2014\ < D:\Documents\2013\Reports\: true */  
```  
  
 Pour exécuter ce code, collez\-le dans l’exemple complet ci\-dessus et supprimez les commentaires de la ligne qui l’appelle dans la fonction main.  
  
### Conversion entre les types chemin d'accès et chaîne  
 Un objet `path` est implicitement convertible en `std::wstring` ou en `std::string`. Cela signifie que vous pouvez passer un chemin d'accès à des fonctions telles que [wofstream::open](../Topic/basic_ofstream::open.md), comme illustré dans cet exemple :  
  
```cpp  
wchar_t* p = L"C:/test"; path filePath(p); filePath /= L"NewFile.txt"; // Open, write to, and close the file. wofstream myFile; myFile.open(filePath); myFile << L"Lorem ipsum..."; myFile.close  
  
```  
  
## Itération de répertoires et de fichiers  
 L'en\-tête \<filesystem\> fournit le type [directory\_iterator](../standard-library/directory-iterator-class.md) pour itérer un seul répertoire, et la classe [recursive\_directory\_iterator](../standard-library/recursive-directory-iterator-class.md) pour itérer de manière récursive un répertoire et tous ses sous\-répertoires. Après avoir construit un itérateur en lui passant un objet `path`, l’itérateur pointe vers le premier objet directory\_entry dans le chemin. Créez l'itérateur de fin en appelant le constructeur par défaut.  
  
 Lors d'une itération d'un répertoire, plusieurs types d'éléments peuvent être examinés, tels que des répertoires, des fichiers, des liens symboliques et des fichiers socket, entre autres. Le `directory_iterator` retourne ses éléments en tant qu’objets [directory\_entry](../standard-library/directory-entry-class.md), et chaque objet a un membre [status\(\)](http://msdn.microsoft.com/fr-fr/a70a3c55-3a76-417f-abaf-862ff94b2056) qui indique le type d’entrée que vous examinez. L'examen de cette valeur vous permet de déterminer l'action à faire pour une entrée donnée. L'exemple suivant itère un seul répertoire. Si l'entrée répertoire \(directory\) correspond à un fichier standard, le code affiche des informations sur ce fichier. Si l'entrée est un répertoire, seul le nom s'affiche.  
  
```cpp  
#include <string> #include <iostream> #include <iomanip> #include <filesystem> #include <chrono> #include <time.h> using namespace std; using namespace std::experimental::filesystem::v1; // Display the last write time for the file wstring LastWriteTimeToLocalTime(const path& file_path) { const auto last = chrono::system_clock::to_time_t(last_write_time(file_path)); tm timeinfo; localtime_s(&timeinfo, &last); wchar_t buf[56]; _wasctime_s(buf, 56, &timeinfo); // appends '\n' return wstring{ buf }; } // List files and directories in the specified path void DisplayFolderContents(const path& p) { wcout << L"Begin iterating " << p.wstring() << endl; for (const auto& entry : directory_iterator{ p }) { if (is_regular_file(entry.status())) { wcout << L" File: " << entry.path().filename() << " : " << LastWriteTimeToLocalTime(entry.path()); } else if (is_directory(entry.status())) { wcout << L" Dir: " << entry.path().filename() << endl; } } } void main() { wstring dir{ LR"(C:\users\public\documents\)" }; path p{ dir }; if (!is_directory(p)) { wcout << L"No such directory: " << dir << endl; return; } DisplayFolderContents(p); // IterateFolderRecursively(p); // see example wcout << endl << L"Press Enter to exit" << endl; wstring input; getline(wcin, input); }  
```  
  
### Itération récursive d'une arborescence de répertoires  
 L'exemple suivant montre comment itérer plusieurs fois une arborescence de répertoires. Pour exécuter cette fonction, collez\-le dans l’exemple de code précédent après la fonction DisplayFolderContents et supprimez les commentaires de la ligne qui l’appelle dans la fonction main.  
  
```cpp  
// List files and directories recursively in the path void IterateFolderRecursively(const path& p) { wcout << L"Begin iterating " << p.wstring() << " recursively" << endl; for (recursive_directory_iterator it{ p }, end; it != end; ++it) { if (is_regular_file(it->status())) { wcout << setw(it.depth()) << L" " << L"File: " << it->path().filename() << L" : " << LastWriteTimeToLocalTime(it->path()); } else if (is_directory(it->status())) { wcout << setw(it.depth()) << L" " << L"Dir: " << it->path().filename() << endl; } } }  
```  
  
### Gestion des liens symboliques  
 La détection des liens symboliques n'est pas encore prise en charge par Visual C\+\+ dans Visual Studio 2015.