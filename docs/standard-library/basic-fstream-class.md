---
title: "basic_fstream, classe | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std::basic_fstream"
  - "basic_fstream"
  - "fstream/std::basic_fstream"
  - "std.basic_fstream"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "basic_fstream (classe)"
ms.assetid: 8473817e-42a4-430b-82b8-b476c86bcf8a
caps.latest.revision: 24
caps.handback.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# basic_fstream, classe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Décrit un objet qui contrôle l'insertion et l'extraction d'éléments et d'objets encodés à l'aide d'une mémoire tampon de flux de classe [basic\_filebuf](../standard-library/basic-filebuf-class.md)\<`Elem`, `Tr`\>, avec des éléments de type `Elem`, dont les caractéristiques sont déterminées par la classe `Tr`.  
  
## Syntaxe  
  
```  
template <class Elem, class Tr = char_traits<Elem> >  
    class basic_fstream : public basic_iostream<Elem, Tr>  
```  
  
#### Paramètres  
 `Elem`  
 Élément de base de la mémoire tampon de fichier.  
  
 `Tr`  
 Caractéristiques de l'élément de base de la mémoire tampon de fichier \(généralement `char_traits`\<`Elem`\>\).  
  
## Notes  
 L'objet stocke un objet de classe `basic_filebuf`\<`Elem`, `Tr`\>.  
  
> [!NOTE]
>  Les pointeurs get et put d'un objet fstream ne sont **PAS** indépendants l'un de l'autre.  Si le pointeur get bouge, le pointeur put bouge aussi.  
  
## Exemple  
 L'exemple suivant montre comment créer un objet `basic_fstream` qui peut être lu et écrit.  
  
```  
// basic_fstream_class.cpp  
// compile with: /EHsc  
  
#include <fstream>  
#include <iostream>  
  
using namespace std;  
  
int main(int argc, char **argv)  
{  
    fstream fs("fstream.txt", ios::in | ios::out | ios::trunc);  
    if (!fs.bad())  
    {  
        // Write to the file.  
        fs << "Writing to a basic_fstream object..." << endl;  
        fs.close();  
  
        // Dump the contents of the file to cout.  
        fs.open("fstream.txt", ios::in);  
        cout << fs.rdbuf();  
        fs.close();  
    }  
}  
```  
  
  **Écriture dans un objet basic\_fstream...**   
### Constructeurs  
  
|||  
|-|-|  
|[basic\_fstream](../Topic/basic_fstream::basic_fstream.md)|Construit un objet de type `basic_fstream`.|  
  
### Fonctions membres  
  
|||  
|-|-|  
|[fermer](../Topic/basic_fstream::close.md)|Ferme un fichier.|  
|[is\_open](../Topic/basic_fstream::is_open.md)|Détermine si un fichier est ouvert.|  
|[ouvrir](../Topic/basic_fstream::open.md)|Ouvre un fichier.|  
|[rdbuf](../Topic/basic_fstream::rdbuf.md)|Retourne l'adresse de la mémoire tampon de flux stockée, de type pointeur vers [basic\_filebuf](../standard-library/basic-filebuf-class.md)\<`Elem`, `Tr`\>.|  
|[échange](../Topic/basic_fstream::swap.md)|Échange le contenu de cet objet avec le contenu d'un autre objet `basic_fstream`.|  
  
## Configuration requise  
 **En\-tête :** \<fstream\>  
  
 **Espace de noms :** std  
  
## Voir aussi  
 [Sécurité des threads dans la bibliothèque standard C\+\+](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [iostream, programmation](../standard-library/iostream-programming.md)   
 [iostreams, conventions](../standard-library/iostreams-conventions.md)