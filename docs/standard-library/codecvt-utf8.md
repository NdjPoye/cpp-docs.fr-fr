---
title: "codecvt_utf8 | Microsoft Docs"
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
  - "std.codecvt_utf8"
  - "std::codecvt_utf8"
  - "codecvt_utf8"
  - "codecvt/std::codecvt_utf8"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "codecvt_utf8 (classe)"
ms.assetid: 2a87478f-e2d4-4b8d-ad9c-00add01d1bb0
caps.latest.revision: 20
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# codecvt_utf8
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Représente une facette de [paramètres régionaux](../standard-library/locale-class.md) qui convertit entre les caractères encodés comme UCS\-2 ou l'UCS\-4, et un flux d'octets encodé en UTF\-8.  
  
## Syntaxe  
  
```  
template<  
    class Elem,  
    unsigned long Maxcode = 0x10ffff,  
    codecvt_mode Mode = (codecvt_mode)0  
>  
class codecvt_utf8 : public std::codecvt<Elem, char, StateType>  
```  
  
#### Paramètres  
  
|Paramètre|Description|  
|---------------|-----------------|  
|`Elem`|Le type d'élément de caractères étendus.|  
|`Maxcode`|Le nombre maximal de caractères pour la facette de paramètres régionaux.|  
|`Mode`|Informations de configuration pour la facette de paramètres régionaux.|  
  
## Notes  
 Le flux d'octets peut être écrit dans un fichier binaire ou un fichier texte.  
  
## Configuration requise  
 **En\-tête :** \<codecvt\>  
  
 **Espace de noms :** std