---
title: "numpunct_byname, classe | Microsoft Docs"
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
  - "std.numpunct_byname"
  - "numpunct_byname"
  - "xlocnum/std::numpunct_byname"
  - "std::numpunct_byname"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "numpunct_byname (classe)"
ms.assetid: 18412924-e085-4771-b5e9-7a200cbdd7c0
caps.latest.revision: 24
caps.handback.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# numpunct_byname, classe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

La classe de modèle dérivée décrit un objet qui peut servir de facette de type `numpunct` pour des paramètres régionaux donnés permettant la mise en forme et la ponctuation d'expressions numériques et booléennes.  
  
## Syntaxe  
  
```  
template<Class CharType>  
    class numpunct_byname : public numpunct<Elem> {  
public:  
    explicit numpunct_byname(  
        const char* _Locname,  
        size_t _Refs = 0  
    );  
    explicit numpunct_byname(  
        const string& _Locname,  
        size_t _Refs = 0  
    );  
protected:  
    virtual ~numpunct_byname( );  
   };  
```  
  
## Notes  
 Son comportement est déterminé par le [nommé](../Topic/locale::name.md) paramètres régionaux `_Locname`.  Le constructeur initialise son objet de base avec [numpunct](../Topic/numpunct::numpunct.md)\<CharType\>\(`_Refs`\).  
  
## Configuration requise  
 **En\-tête:** \<paramètres régionaux\>  
  
 **Espace de noms :** std  
  
## Voir aussi  
 [Sécurité des threads dans la bibliothèque standard C\+\+](../standard-library/thread-safety-in-the-cpp-standard-library.md)