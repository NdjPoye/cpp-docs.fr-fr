---
title: "ctype_byname, classe | Microsoft Docs"
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
  - "xlocale/std::ctype_byname"
  - "std::ctype_byname"
  - "ctype_byname"
  - "std.ctype_byname"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ctype_byname (classe)"
ms.assetid: a5cec021-a1f8-425f-8757-08e6f064b604
caps.latest.revision: 22
caps.handback.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# ctype_byname, classe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

La classe de modèle dérivée décrit un objet qui peut servir de facette C des paramètres régionaux fournis, ce qui permet la classification des caractères et conversion de caractères entre le cas et mode natif et les jeux de caractères spécifiés par les paramètres régionaux.  
  
## Syntaxe  
  
```  
template<class _Elem>  
class ctype_byname : public ctype<_Elem>  
{  
public:  
    explicit ctype_byname(  
        const char *_Locname,  
        size_t _Refs = 0  
    );  
    explicit ctype_byname(  
        const string& _Locname,  
        size_t _Refs = 0  
    );  
protected:  
    virtual __CLR_OR_THIS_CALL ~ctype_byname();  
};  
```  
  
## Notes  
 Son comportement est déterminé par les paramètres régionaux nommés `_Locname`.  Chaque constructeur initialise l'objet de base de [C](../standard-library/ctype-class.md)\<CharType\>\(`_Refs`\) ou l'équivalent de la classe de base `ctype<char>`.  
  
## Configuration requise  
 **En\-tête :**paramètres régionaux \<de \>  
  
 **Espace de noms :** std  
  
## Voir aussi  
 [Sécurité des threads dans la bibliothèque standard C\+\+](../standard-library/thread-safety-in-the-cpp-standard-library.md)