---
title: "codecvt_utf8_utf16 | Microsoft Docs"
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
  - "codecvt_utf8_utf16"
  - "codecvt/std::cvt_utf8_utf16"
  - "std::codecvt_utf8_utf16"
  - "std.codecvt_utf8_utf16"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "codecvt_utf8_utf16 (classe)"
ms.assetid: 4c12c881-5dba-4e39-b338-0b9caff5af29
caps.latest.revision: 21
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# codecvt_utf8_utf16
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Représente une facette de [paramètres régionaux](../standard-library/locale-class.md) qui convertit entre les caractères encodés comme UTF\-16, et un flux d'octets encodé en UTF\-8.  
  
## Syntaxe  
  
```  
template<  
    class Elem,  
    unsigned long Maxcode = 0x10ffff,  
    codecvt_mode Mode = (codecvt_mode)0  
>  
class codecvt_utf8_utf16 : public _STD codecvt<Elem, char, StateType>  
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