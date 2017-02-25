---
title: "codecvt_byname, classe | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std.codecvt_byname"
  - "codecvt_byname"
  - "std::codecvt_byname"
  - "xlocale/std::codecvt_byname"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "codecvt_byname (classe)"
ms.assetid: b63b6c04-f60c-47b9-8e30-a933f24a8ffb
caps.latest.revision: 24
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 24
---
# codecvt_byname, classe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Une classe de modèle dérivée qui décrit un objet qui peut servir de facette pour assembler des paramètres régionaux fournis, ce qui permet la récupération des informations spécifiques à une zone culturelles au relatives aux conversions.  
  
## Syntaxe  
  
```  
template<Class CharType, class Byte, class StateType>  
    class codecvt_byname: public codecvt<CharType, Byte, StateType> {  
public:  
    explicit codecvt_byname(  
        const char* _Locname,  
        size_t _Refs = 0  
    );  
```  
  
```  
explicit codecvt_byname(  
    const string& _Locname,  
    size_t _Refs = 0  
);  
```  
  
```  
protected:  
    virtual ~codecvt_byname( );  
};  
```  
  
#### Paramètres  
 `_Locname`  
 Les paramètres régionaux nommés.  
  
 `_Refs`  
 Le premier nombre de références.  
  
## Notes  
 Des facettes de Byname sont automatiquement créées lorsque les paramètres régionaux nommés sont construits.  
  
 Son comportement est déterminé par les paramètres régionaux nommés `_Locname`.  Chaque constructeur initialise l'objet de base de [codecvt](../standard-library/codecvt-class.md)\<CharType, byte, StateType\>\(`_Refs`\).  
  
## Configuration requise  
 **En\-tête :**paramètres régionaux \<de \>  
  
 **Espace de noms :** std  
  
## Voir aussi  
 [Sécurité des threads dans la bibliothèque standard C\+\+](../standard-library/thread-safety-in-the-cpp-standard-library.md)