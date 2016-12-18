---
title: "codecvt_utf16 | Microsoft Docs"
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
  - "codecvt/std::codecvt_utf16"
  - "std::codecvt_utf16"
  - "std.codecvt_utf16"
  - "codecvt_utf16"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "codecvt_utf16 (classe)"
ms.assetid: a9897f98-f84d-4db6-90ad-858b2727570c
caps.latest.revision: 21
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# codecvt_utf16
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Représente un [paramètres régionaux](../standard-library/locale-class.md) facette qui effectue la conversion entre des caractères larges encodées sous la forme UCS\-2 ou UCS\-4 et un flux d’octets encodée en UTF\-16LE ou UTF\-16BE.  
  
## Syntaxe  
  
```  
template<  
    class Elem,  
    unsigned long Maxcode = 0x10ffff,  
    codecvt_mode Mode = (codecvt_mode)0  
>  
class codecvt_utf16 : public std::codecvt<Elem, char, StateType>  
```  
  
#### Paramètres  
  
|Paramètre|Description|  
|---------------|-----------------|  
|`Elem`|Type d'élément à caractères larges.|  
|`Maxcode`|Le nombre maximal de caractères pour la facette de paramètres régionaux.|  
|`Mode`|Informations de configuration pour la facette de paramètres régionaux.|  
  
## Notes  
 Cette classe de modèle effectue la conversion entre des caractères larges encodées sous la forme UCS\-2 ou UCS\-4 et un flux d’octets encodée en UTF\-16LE, si `Mode & little_endian`, ou UTF\-16BE sinon.  
  
 Le flux d’octets doit être écrit dans un fichier binaire. Il peut être endommagé s’écrit dans un fichier texte.  
  
## Configuration requise  
 **En\-tête :** \< codecvt \>  
  
 **Espace de noms :** std