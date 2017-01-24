---
title: "basic_ifstream, classe | Microsoft Docs"
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
  - "basic_ifstream"
  - "fstream/std::basic_ifstream"
  - "std::basic_ifstream"
  - "std.basic_ifstream"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "basic_ifstream (classe)"
ms.assetid: 366cd9a7-efc4-4b7f-ba10-c8271e47ffcf
caps.latest.revision: 23
caps.handback.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# basic_ifstream, classe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Décrit un objet qui contrôle l'extraction d'éléments et d'objets encodés à partir d'une mémoire tampon de flux de classe [basic\_filebuf](../standard-library/basic-filebuf-class.md)\<`Elem`, `Tr`\>, avec des éléments de type `Elem`, dont les caractéristiques sont déterminées par la classe `Tr`.  
  
## Syntaxe  
  
```  
template <class Elem, class Tr = char_traits<Elem> >  
    class basic_ifstream : public basic_istream<Elem, Tr>  
```  
  
#### Paramètres  
 `Elem`  
 Élément de base de la mémoire tampon de fichier.  
  
 `Tr`  
 Caractéristiques de l'élément de base de la mémoire tampon de fichier \(généralement `char_traits`\<`Elem`\>\).  
  
## Notes  
 L'objet stocke un objet de classe `basic_filebuf`\<`Elem`, `Tr`\>.  
  
## Exemple  
 L'exemple suivant montre comment lire le texte d'un fichier.  
  
```  
// basic_ifstream_class.cpp  
// compile with: /EHsc  
  
#include <fstream>  
#include <iostream>  
  
using namespace std;  
  
int main(int argc, char **argv)  
{  
    ifstream ifs("basic_ifstream_class.txt");  
    if (!ifs.bad())  
    {  
        // Dump the contents of the file to cout.  
        cout << ifs.rdbuf();  
        ifs.close();  
    }  
}  
```  
  
## Entrée : basic\_ifstream\_class.txt  
  
```  
This is the contents of basic_ifstream_class.txt.  
```  
  
## Sortie  
  
```  
This is the contents of basic_ifstream_class.txt.  
```  
  
### Constructeurs  
  
|||  
|-|-|  
|[basic\_ifstream](../Topic/basic_ifstream::basic_ifstream.md)|Initialise une nouvelle instance d'un objet `basic_ifstream`.|  
  
### Fonctions membres  
  
|||  
|-|-|  
|[fermer](../Topic/basic_ifstream::close.md)|Ferme un fichier.|  
|[is\_open](../Topic/basic_ifstream::is_open.md)|Détermine si un fichier est ouvert.|  
|[ouvrir](../Topic/basic_ifstream::open.md)|Ouvre un fichier.|  
|[rdbuf](../Topic/basic_ifstream::rdbuf.md)|Retourne l'adresse de la mémoire tampon de flux stockée.|  
|[échange](../Topic/basic_ifstream::swap.md)|Échange le contenu de ce `basic_ifstream` avec le contenu du `basic_ifstream` fourni.|  
  
### Opérateurs  
  
|||  
|-|-|  
|[opérateur \=](../Topic/basic_ifstream::operator=.md)|Assigne le contenu de cet objet de flux.  Il s'agit d'une assignation de déplacement impliquant une `rvalue` qui ne laisse pas de copie.|  
  
## Configuration requise  
 **En\-tête :** \<fstream\>  
  
 **Espace de noms :** std  
  
## Voir aussi  
 [Sécurité des threads dans la bibliothèque standard C\+\+](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [iostream, programmation](../standard-library/iostream-programming.md)   
 [iostreams, conventions](../standard-library/iostreams-conventions.md)