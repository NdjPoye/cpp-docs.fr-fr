---
title: "Fonctions membres de flux de fichiers d&#39;entr&#233;e | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "objets de flux d'entrée"
  - "flux d'entrée, fonctions membres"
ms.assetid: b4b9465d-0da9-4ccf-859d-72a68418982e
caps.latest.revision: 7
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Fonctions membres de flux de fichiers d&#39;entr&#233;e
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Les fonctions membres du flux d'entrée sont utilisées pour l'entrée de disque.  Les fonctions membres sont les suivantes :  
  
-   [La fonction ouverte pour les flux d'entrée](#vclrftheopenfunctionforinputstreamsanchor11)  
  
-   [La fonction système](#vclrfthegetfunctionanchor12)  
  
-   [La fonction de getline](#vclrfthegetlinefunctionanchor13)  
  
-   [La fonction de lecture](#vclrfthereadfunctionanchor14)  
  
-   [Les fonctions de seekg et de tellg](#vclrftheseekgandtellgfunctionsanchor7)  
  
-   [La fonction proche pour les flux d'entrée](#vclrftheclosefunctionforinputstreamsanchor15)  
  
##  <a name="vclrftheopenfunctionforinputstreamsanchor11"></a> La fonction ouverte pour les flux d'entrée  
 Si vous utilisez un flux de fichier d'entrée \(ifstream\), vous devez associer ce flux de données avec un fichier de disque spécifique.  Effectuez cette opération dans le constructeur, ou vous pouvez utiliser la fonction de **ouvrir**.  Dans l'un et l'autre cas, les arguments sont les mêmes.  
  
 Vous spécifiez en général un indicateur de [ios\_base::openmode](../Topic/ios_base::openmode.md) lorsque vous ouvrez le fichier associé à un flux d'entrée \(mode par défaut est **ios::in**\).  Pour obtenir la liste des indicateurs d'**open\_mode**, consultez l'[La fonction ouverte](#vclrftheopenfunctionforinputstreamsanchor11).  Les indicateurs peuvent être combinées avec le niveau de le bit \( &#124; opérateur.\)  
  
 Pour lire un fichier, utilisez tout d'abord la fonction membre du **Échec** pour déterminer si elle est remplie :  
  
```  
istream ifile( "FILENAME" );  
if ( ifile.fail() )  
// The file does not exist ...  
```  
  
##  <a name="vclrfthegetfunctionanchor12"></a> La fonction système  
 Les travaux non formatés de fonction membre du **obtenir** comme l'opérateur de **\>\>** à deux exceptions.  En premier lieu, la fonction de **obtenir** inclut les espaces blancs, tandis que l'extracteur exclut l'espace blanc si l'indicateur d'[skipws](../Topic/skipws.md) a la valeur \(valeur par défaut\).  Ensuite, la fonction de **obtenir** est inférieure pour générer un flux de sortie attaché \(`cout`, par exemple\) à vider.  
  
 Une variante de la fonction de **obtenir** spécifie une adresse de mémoire tampon et le nombre maximal de caractères à lire.  Cette option est utile pour limiter le nombre de caractères envoyés à une variable spécifique, car cet exemple montre :  
  
```  
// ioo_get_function.cpp  
// compile with: /EHsc  
// Type up to 24 characters and a terminating character.   
// Any remaining characters can be extracted later.  
#include <iostream>  
using namespace std;  
  
int main()  
{  
   char line[25];  
   cout << " Type a line terminated by carriage return\n>";  
   cin.get( line, 25 );  
   cout << line << endl;  
}  
```  
  
### Entrée  
  
```  
1234  
```  
  
### Résultat de l'exemple  
  
```  
1234  
```  
  
##  <a name="vclrfthegetlinefunctionanchor13"></a> La fonction de getline  
 La fonction membre du **getline** est similaire à la fonction de **obtenir**.  Les deux fonctions permettent un troisième argument qui spécifie le caractère de fin pour l'entrée.  La valeur par défaut est le caractère de saut de ligne.  Les deux fonctions réservent un caractère du caractère de fin requis.  Toutefois, **obtenir** permet le caractère de fin du flux de données et **getline** supprime le caractère de fin.  
  
 L'exemple suivant spécifie un caractère de fin du flux d'entrée :  
  
```  
// getline_func.cpp  
// compile with: /EHsc  
#include <iostream>  
using namespace std;  
  
int main( )  
{  
   char line[100];  
   cout << " Type a line terminated by 't'" << endl;  
   cin.getline( line, 100, 't' );  
   cout << line;  
}  
```  
  
### Entrée  
  
```  
test  
```  
  
##  <a name="vclrfthereadfunctionanchor14"></a> La fonction de lecture  
 La fonction membre du **lecture** lit les octets à partir d'un fichier dans une zone de mémoire spécifiée.  L'argument de longueur détermine le nombre d'octets.  Si vous n'incluez pas cet argument, lire s'arrête lorsque la fin de fichier physique est atteint ou, dans le cas d'un fichier de mode texte, lorsqu'un caractère incorporée d'`EOF` est lu.  
  
 Cet exemple lit un enregistrement binaire à partir d'un fichier de registre du personnel dans une structure :  
  
```  
#include <fstream>  
#include <iostream>  
using namespace std;  
  
int main()  
{  
   struct  
   {  
      double salary;  
      char name[23];  
   } employee;  
  
   ifstream is( "payroll" );  
   if( is ) {  // ios::operator void*()  
      is.read( (char *) &employee, sizeof( employee ) );  
      cout << employee.name << ' ' << employee.salary << endl;  
   }  
   else {  
      cout << "ERROR: Cannot open file 'payroll'." << endl;  
   }  
}  
```  
  
 Le programme suppose que les enregistrements de données sont mis en forme exactement comme spécifié par la structure sans arrêter les caractères de retour chariot ou de saut de ligne.  
  
##  <a name="vclrftheseekgandtellgfunctionsanchor7"></a> Les fonctions de seekg et de tellg  
 Les flux de fichier d'entrée conservent un pointeur interne à la position du fichier dans lequel les données doivent être lues suivant.  Vous définissez le pointeur à la fonction d'`seekg`, comme indiqué ici :  
  
```  
#include <iostream>  
#include <fstream>  
using namespace std;  
  
int main( )  
{  
   char ch;  
  
   ifstream tfile( "payroll" );  
   if( tfile ) {  
      tfile.seekg( 8 );        // Seek 8 bytes in (past salary)  
      while ( tfile.good() ) { // EOF or failure stops the reading  
         tfile.get( ch );  
         if( !ch ) break;      // quit on null  
         cout << ch;  
      }  
   }  
   else {  
      cout << "ERROR: Cannot open file 'payroll'." << endl;  
   }  
}  
```  
  
 Pour utiliser `seekg` pour implémenter les systèmes de gestion de données enregistrement\- orientés, multipliez la taille d'enregistrement de longueur fixe par le numéro d'enregistrement pour obtenir la position d'octets par rapport à la fin de le fichier, puis utiliser l'objet de **obtenir** pour lire l'enregistrement.  
  
 La fonction membre d'`tellg` retourne la position actuelle du fichier en lecture.  Cette valeur est de type `streampos`, `typedef` défini dans \<l'iostream\>.  L'exemple suivant lit un fichier et affiche des messages indiquant les positions des espaces.  
  
```  
#include <fstream>  
#include <iostream>  
using namespace std;  
  
int main( )  
{  
   char ch;  
   ifstream tfile( "payroll" );  
   if( tfile ) {  
       while ( tfile.good( ) ) {  
          streampos here = tfile.tellg();  
          tfile.get( ch );  
          if ( ch == ' ' )  
             cout << "\nPosition " << here << " is a space";  
       }  
   }  
   else {  
      cout << "ERROR: Cannot open file 'payroll'." << endl;  
   }  
}  
```  
  
##  <a name="vclrftheclosefunctionforinputstreamsanchor15"></a> La fonction proche pour les flux d'entrée  
 La fonction membre du **fermer** ferme le fichier disque associé à un flux de fichier d'entrée et libère le handle de fichier du système d'exploitation.  Le destructeur de [ifstream](../standard-library/basic-ifstream-class.md) ferme le fichier pour vous, mais vous pouvez utiliser la fonction de **fermer** si vous devez ouvrir un autre fichier pour le même objet de flux.  
  
## Voir aussi  
 [Flux d'entrée](../standard-library/input-streams.md)