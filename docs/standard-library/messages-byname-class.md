---
title: "messages_byname, classe | Microsoft Docs"
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
  - "messages_byname"
  - "std::messages_byname"
  - "std.messages_byname"
  - "xlocmes/std::messages_byname"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "messages_byname (classe)"
ms.assetid: c6c64841-3e80-43c8-b54c-fed41833ad6b
caps.latest.revision: 22
caps.handback.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# messages_byname, classe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

La classe de modèle dérivée décrit un objet qui peut servir de facette de message les paramètres régionaux fournis, ce qui permet la récupération des messages localisés.  
  
## Syntaxe  
  
```  
template<class CharType>  
    class messages_byname : public messages<CharType> {  
public:  
    explicit messages_byname(  
        const char *_Locname,  
        size_t _Refs = 0  
    );  
    explicit messages_byname(  
        const string& _Locname,  
        size_t _Refs = 0  
    );   
protected:  
    virtual ~messages_byname();  
};  
```  
  
#### Paramètres  
 `_Locname`  
 Les paramètres régionaux nommés.  
  
 `_Refs`  
 Le premier nombre de références.  
  
## Notes  
 Son comportement est déterminé par les paramètres régionaux nommés `_Locname`.  Chaque constructeur initialise l'objet de base de [messages](../Topic/messages::messages.md)\<CharType\>\(`_Refs`\).  
  
## Configuration requise  
 **En\-tête :**paramètres régionaux \<de \>  
  
 **Espace de noms :** std  
  
## Voir aussi  
 [Sécurité des threads dans la bibliothèque standard C\+\+](../standard-library/thread-safety-in-the-cpp-standard-library.md)