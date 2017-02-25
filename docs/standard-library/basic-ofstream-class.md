---
title: "basic_ofstream, classe | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std::basic_ofstream"
  - "basic_ofstream"
  - "std.basic_ofstream"
  - "fstream/std::basic_ofstream"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "basic_ofstream (classe)"
ms.assetid: 3bcc9c51-6dfc-4844-8fcc-22ef57c9dff1
caps.latest.revision: 24
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 24
---
# basic_ofstream, classe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Décrit un objet qui contrôle l'insertion d'éléments et d'objets encodés dans une mémoire tampon de flux de classe [basic\_filebuf](../standard-library/basic-filebuf-class.md)\<`Elem`, `Tr`\>, avec des éléments de type `Elem`, dont les caractéristiques sont déterminées par la classe `Tr`.  
  
## Syntaxe  
  
```  
template <class Elem, class Tr = char_traits<Elem> >  
    class basic_ofstream : public basic_ostream<Elem, Tr>  
```  
  
#### Paramètres  
 `Elem`  
 Élément de base de la mémoire tampon de fichier.  
  
 `Tr`  
 Caractéristiques de l'élément de base de la mémoire tampon de fichier \(généralement `char_traits`\<`Elem`\>\).  
  
## Notes  
 Quand la spécialisation `wchar_t` de `basic_ofstream` écrit dans le fichier, si celui\-ci est ouvert en mode texte, elle écrit une séquence MBCS.  La représentation interne utilisera une mémoire tampon de caractères `wchar_t`.  
  
 L'objet stocke un objet de classe `basic_filebuf`\<`Elem`, `Tr`\>.  
  
## Exemple  
 L'exemple suivant montre comment créer un objet `basic_ofstream` et y écrire du texte.  
  
```  
// basic_ofstream_class.cpp  
// compile with: /EHsc  
#include <fstream>  
  
using namespace std;  
  
int main(int argc, char **argv)  
{  
    ofstream ofs("ofstream.txt");  
    if (!ofs.bad())  
    {  
        ofs << "Writing to a basic_ofstream object..." << endl;  
        ofs.close();  
    }  
}  
```  
  
### Constructeurs  
  
|||  
|-|-|  
|[basic\_ofstream](../Topic/basic_ofstream::basic_ofstream.md)|Crée un objet de type `basic_ofstream`.|  
  
### Fonctions membres  
  
|||  
|-|-|  
|[fermer](../Topic/basic_ofstream::close.md)|Ferme un fichier.|  
|[is\_open](../Topic/basic_ofstream::is_open.md)|Détermine si un fichier est ouvert.|  
|[ouvrir](../Topic/basic_ofstream::open.md)|Ouvre un fichier.|  
|[rdbuf](../Topic/basic_ofstream::rdbuf.md)|Retourne l'adresse de la mémoire tampon de flux stockée.|  
|[échange](../Topic/basic_ofstream::swap.md)|Échange le contenu de ce `basic_ofstream` avec le contenu du `basic_ofstream` fourni.|  
  
### Opérateurs  
  
|||  
|-|-|  
|[opérateur \=](../Topic/basic_ofstream::operator=.md)|Assigne le contenu de cet objet de flux.  Il s'agit d'une assignation de déplacement impliquant une `rvalue reference` qui ne laisse pas de copie.|  
  
## Configuration requise  
 **En\-tête :** \<fstream\>  
  
 **Espace de noms :** std  
  
## Voir aussi  
 [basic\_ostream, classe](../standard-library/basic-ostream-class.md)   
 [Sécurité des threads dans la bibliothèque standard C\+\+](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [iostream, programmation](../standard-library/iostream-programming.md)   
 [iostreams, conventions](../standard-library/iostreams-conventions.md)