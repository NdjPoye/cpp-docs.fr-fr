---
title: "time_put_byname, classe | Microsoft Docs"
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
  - "time_put_byname"
  - "xloctime/std::time_put_byname"
  - "std.time_put_byname"
  - "std::time_put_byname"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "time_put_byname (classe)"
ms.assetid: e08c2348-64d2-4ace-98b1-1496e14c7b1a
caps.latest.revision: 25
caps.handback.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# time_put_byname, classe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

La classe dérivée de modèle décrit un objet pouvant servir de facette de paramètres régionaux de type `time_put`\< CharType, OutputIterator \>.  
  
## Syntaxe  
  
```  
template<class CharType,  
 class OutIt = ostreambuf_iterator<CharType, char_traits<CharType> > >  
 class time_put_byname : public time_put<CharType, OutputIterator>  
{  
public:  
    explicit time_put_byname(  
        const char *_Locname,  
        size_t _Refs = 0  
    );  
    explicit time_put_byname(  
        const string& _Locname,  
        size_t _Refs = 0  
    );  
protected:  
    virtual ~time_put_byname();  
};  
```  
  
#### Paramètres  
 `_Locname`  
 Un nom de paramètres régionaux.  
  
 `_Refs`  
 Un décompte de références initial.  
  
## Notes  
 Son comportement est déterminé par le [nommé](../Topic/locale::name.md) paramètres régionaux `_Locname`. Chaque constructeur initialise les objets de base avec [time\_put](../Topic/time_put::time_put.md)\< CharType, OutputIterator \> \(`_Refs`\).  
  
## Configuration requise  
 **En\-tête :** \<locale\>  
  
 **Espace de noms :** std  
  
## Voir aussi  
 [Sécurité des threads dans la bibliothèque standard C\+\+](../standard-library/thread-safety-in-the-cpp-standard-library.md)