---
title: "basic_filebuf, classe | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std.basic_filebuf"
  - "fstream/std::basic_filebuf"
  - "std::basic_filebuf"
  - "basic_filebuf"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "basic_filebuf (classe)"
ms.assetid: 3196ba5c-bf38-41bd-9a95-70323ddfca1a
caps.latest.revision: 24
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 24
---
# basic_filebuf, classe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Décrit une mémoire tampon de flux qui contrôle la transmission d'éléments de type `Elem`, dont les caractéristiques sont déterminées par la classe `Tr`, vers et à partir d'une séquence d'éléments stockés dans un fichier externe.  
  
## Syntaxe  
  
```  
template <class Elem, class Tr = char_traits<Elem> >  
    class basic_filebuf : public basic_streambuf<Elem, Tr>  
```  
  
#### Paramètres  
 `Elem`  
 Élément de base de la mémoire tampon de fichier.  
  
 `Tr`  
 Caractéristiques de l'élément de base de la mémoire tampon de fichier \(généralement `char_traits`\<`Elem`\>\).  
  
## Notes  
 La classe de modèle décrit une mémoire tampon de flux qui contrôle la transmission d'éléments de type `Elem`, dont les caractéristiques sont déterminées par la classe `Tr`, vers et à partir d'une séquence d'éléments stockés dans un fichier externe.  
  
> [!NOTE]
>  Les objets de type `basic_filebuf` sont créés avec une mémoire tampon interne de type `char *` quel que soit le `char_type` spécifié par le paramètre de type `Elem`.  Cela signifie qu'une chaîne Unicode \(contenant des caractères `wchar_t`\) sera convertie en chaîne ANSI \(contenant des caractères `char`\) avant d'être écrite dans la mémoire tampon interne.  Pour stocker des chaînes Unicode dans la mémoire tampon, créez une mémoire tampon de type `wchar_t` et définissez\-la à l'aide de la méthode [basic\_streambuf::pubsetbuf](../Topic/basic_streambuf::pubsetbuf.md)`()`.  Pour obtenir un exemple qui illustre ce comportement, voir ci\-dessous.  
  
 Un objet de classe `basic_filebuf`\<`Elem`, `Tr`\> stocke un pointeur de fichier, qui désigne l'objet `FILE` qui contrôle le flux associé à un fichier ouvert.  Il stocke également des pointeurs vers deux facettes de conversion de fichier utilisables par les fonctions membres protégées [overflow](../Topic/basic_filebuf::overflow.md) et [underflow](../Topic/basic_filebuf::underflow.md).  Pour plus d'informations, consultez [basic\_filebuf::open](../Topic/basic_filebuf::open.md).  
  
## Exemple  
 L'exemple suivant montre comment forcer un objet de type `basic_filebuf<wchar_t>` à stocker des caractères Unicode dans sa mémoire tampon interne en appelant la méthode `pubsetbuf()`.  
  
```  
// unicode_basic_filebuf.cpp  
// compile with: /EHsc  
  
#include <iostream>  
#include <string>  
#include <fstream>  
#include <iomanip>  
#include <memory.h>  
#include <string.h>  
  
#define IBUFSIZE 16  
  
using namespace std;  
  
void hexdump(const string& filename);  
  
int main()  
{  
    wchar_t* wszHello = L"Hello World";  
    wchar_t wBuffer[128];  
  
    basic_filebuf<wchar_t> wOutFile;  
  
    // Open a file, wcHello.txt, then write to it, then dump the  
    // file's contents in hex  
    wOutFile.open("wcHello.txt",  
        ios_base::out | ios_base::trunc | ios_base::binary);  
    if(!wOutFile.is_open())  
    {  
        cout << "Error Opening wcHello.txt\n";  
        return -1;  
    }  
    wOutFile.sputn(wszHello, (streamsize)wcslen(wszHello));  
    wOutFile.close();  
    cout << "Hex Dump of wcHello.txt - note that output is ANSI chars:\n";  
    hexdump(string("wcHello.txt"));  
  
    // Open a file, wwHello.txt, then set the internal buffer of  
    // the basic_filebuf object to be of type wchar_t, then write  
    // to the file and dump the file's contents in hex  
    wOutFile.open("wwHello.txt",  
        ios_base::out | ios_base::trunc | ios_base::binary);  
    if(!wOutFile.is_open())  
    {  
        cout << "Error Opening wwHello.txt\n";  
        return -1;  
    }  
    wOutFile.pubsetbuf(wBuffer, (streamsize)128);  
    wOutFile.sputn(wszHello, (streamsize)wcslen(wszHello));  
    wOutFile.close();  
    cout << "\nHex Dump of wwHello.txt - note that output is wchar_t chars:\n";  
    hexdump(string("wwHello.txt"));  
  
    return 0;  
}  
  
// dump contents of filename to stdout in hex  
void hexdump(const string& filename)  
{  
    fstream ifile(filename.c_str(),  
        ios_base::in | ios_base::binary);  
    char *ibuff = new char[IBUFSIZE];  
    char *obuff = new char[(IBUFSIZE*2)+1];  
    int i;  
  
    if(!ifile.is_open())  
    {  
        cout << "Cannot Open " << filename.c_str()  
             << " for reading\n";  
        return;  
    }  
    if(!ibuff || !obuff)  
    {  
        cout << "Cannot Allocate buffers\n";  
        ifile.close();  
        return;  
    }  
  
    while(!ifile.eof())  
    {  
        memset(obuff,0,(IBUFSIZE*2)+1);  
        memset(ibuff,0,IBUFSIZE);  
        ifile.read(ibuff,IBUFSIZE);  
  
        // corner case where file is exactly a multiple of  
        // 16 bytes in length  
        if(ibuff[0] == 0 && ifile.eof())  
            break;  
  
        for(i = 0; i < IBUFSIZE; i++)  
        {  
            if(ibuff[i] >= ' ')  
                obuff[i] = ibuff[i];  
            else  
                obuff[i] = '.';  
  
            cout << setfill('0') << setw(2) << hex  
                 << (int)ibuff[i] << ' ';  
        }  
        cout << "  " << obuff << endl;  
    }  
    ifile.close();  
}  
```  
  
  **Vidage hexadécimal de wcHello.txt. Notez que la sortie se compose de caractères ANSI :**  
**48 65 6c 6c 6f 20 57 6f 72 6c 64 00 00 00 00 00   Hello World.....  Vidage hexadécimal de wwHello.txt. Notez que la sortie se compose de caractères wchar\_t :**  
**48 00 65 00 6c 00 6c 00 6f 00 20 00 57 00 6f 00   H.e.l.l.o.  .W.o.  72 00 6c 00 64 00 00 00 00 00 00 00 00 00 00 00   r.l.d...........**    
### Constructeurs  
  
|||  
|-|-|  
|[basic\_filebuf](../Topic/basic_filebuf::basic_filebuf.md)|Construit un objet de type `basic_filebuf`.|  
  
### Typedefs  
  
|||  
|-|-|  
|[char\_type](../Topic/basic_filebuf::char_type.md)|Associe un nom de type au paramètre de modèle `Elem`.|  
|[int\_type](../Topic/basic_filebuf::int_type.md)|Rend ce type dans la portée de `basic_filebuf` équivalent au type du même nom dans la portée de `Tr`.|  
|[off\_type](../Topic/basic_filebuf::off_type.md)|Rend ce type dans la portée de `basic_filebuf` équivalent au type du même nom dans la portée de `Tr`.|  
|[pos\_type](../Topic/basic_filebuf::pos_type.md)|Rend ce type dans la portée de `basic_filebuf` équivalent au type du même nom dans la portée de `Tr`.|  
|[traits\_type](../Topic/basic_filebuf::traits_type.md)|Associe un nom de type au paramètre de modèle `Tr`.|  
  
### Fonctions membres  
  
|||  
|-|-|  
|[fermer](../Topic/basic_filebuf::close.md)|Ferme un fichier.|  
|[is\_open](../Topic/basic_filebuf::is_open.md)|Indique si un fichier est ouvert.|  
|[ouvrir](../Topic/basic_filebuf::open.md)|Ouvre un fichier.|  
|[dépassement de capacité](../Topic/basic_filebuf::overflow.md)|Fonction virtuelle protégée qui peut être appelée quand un nouveau caractère est inséré dans une mémoire tampon saturée.|  
|[pbackfail](../Topic/basic_filebuf::pbackfail.md)|La fonction membre virtuelle protégée tente de remettre un élément dans le flux d'entrée, puis d'en faire l'élément actif \(vers lequel pointe le pointeur suivant\).|  
|[seekoff](../Topic/basic_filebuf::seekoff.md)|La fonction membre virtuelle protégée tente de modifier les positions actuelles des flux contrôlés.|  
|[seekpos](../Topic/basic_filebuf::seekpos.md)|La fonction membre virtuelle protégée tente de modifier les positions actuelles des flux contrôlés.|  
|[setbuf](../Topic/basic_filebuf::setbuf.md)|La fonction membre virtuelle protégée effectue une opération spécifique à chaque mémoire tampon de flux dérivée.|  
|[Swap](../Topic/basic_filebuf::swap.md)|Échange le contenu de ce `basic_filebuf` avec le contenu du paramètre `basic_filebuf` fourni.|  
|[sync](../Topic/basic_filebuf::sync.md)|La fonction virtuelle protégée tente de synchroniser les flux contrôlés avec n'importe quel flux externe associé.|  
|[uflow](../Topic/basic_streambuf::uflow.md)|Fonction virtuelle protégée pour extraire l'élément actif du flux d'entrée.|  
|[underflow](../Topic/basic_filebuf::underflow.md)|Fonction virtuelle protégée pour extraire l'élément actif du flux d'entrée.|  
  
## Configuration requise  
 **En\-tête :** \<fstream\>  
  
 **Espace de noms :** std  
  
## Voir aussi  
 [\<fstream\>](../standard-library/fstream.md)   
 [Sécurité des threads dans la bibliothèque standard C\+\+](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [iostream, programmation](../standard-library/iostream-programming.md)   
 [iostreams, conventions](../standard-library/iostreams-conventions.md)