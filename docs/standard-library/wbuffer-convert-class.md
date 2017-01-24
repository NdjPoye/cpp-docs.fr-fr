---
title: "wbuffer_convert, classe | Microsoft Docs"
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
  - "stdext::cvt::wbuffer_convert"
  - "wbuffer_convert"
  - "stdext.cvt.wbuffer_convert"
  - "cvt.wbuffer_convert"
  - "cvt::wbuffer_convert"
  - "wbuffer/stdext::cvt::wbuffer_convert"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "wbuffer_convert (classe)"
ms.assetid: 4a56f9bf-4138-4612-b516-525fea401358
caps.latest.revision: 20
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# wbuffer_convert, classe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Décrit une mémoire tampon de flux qui contrôle la transmission des éléments vers et à partir d'une mémoire tampon de flux d'octets.  
  
## Syntaxe  
  
```  
template<class Codecvt,  
    class Elem = wchar_t,  
    class Traits = std::char_traits<Elem>  
>  
    class wbuffer_convert  
        : public std::basic_streambuf<Elem, Traits>  
```  
  
#### Paramètres  
  
|Paramètre|Description|  
|---------------|-----------------|  
|`Codecvt`|Facette [locale](../standard-library/locale-class.md) qui représente l'objet de conversion.|  
|`Elem`|Type d'élément à caractères larges.|  
|`Traits`|Caractéristiques associées à *Elem*.|  
  
## Notes  
 Cette classe de modèle décrit une mémoire tampon de flux qui contrôle la transmission d'éléments de type `_Elem`, dont les caractéristiques sont décrites par la classe `Traits`, vers et à partir d'une mémoire tampon de flux d'octets de type `std::streambuf`.  
  
 La conversion entre une séquence de valeurs `Elem` et des séquences multioctets est effectuée par un objet de classe `Codecvt<Elem, char, std::mbstate_t>`, qui répond aux exigences de la facette de conversion de code standard `std::codecvt<Elem, char, std::mbstate_t>`.  
  
 Un objet de cette classe de modèle stocke :  
  
-   un pointeur vers sa mémoire tampon de flux d'octets sous\-jacente ;  
  
-   un pointeur vers l'objet de conversion alloué \(qui est libéré quand l'objet [wbuffer\_convert](../standard-library/wbuffer-convert-class.md) est détruit\) ;  
  
-   un objet d'état de conversion de type [state\_type](../Topic/wbuffer_convert::state_type.md).  
  
### Constructeurs  
  
|||  
|-|-|  
|[wbuffer\_convert](../Topic/wbuffer_convert::wbuffer_convert.md)|Construit un objet de type `wbuffer_convert`.|  
  
### Typedefs  
  
|||  
|-|-|  
|[state\_type](../Topic/wbuffer_convert::state_type.md)|Type qui représente l'état de conversion.|  
  
### Fonctions membres  
  
|||  
|-|-|  
|[rdbuf](../Topic/wbuffer_convert::rdbuf.md)|Retourne la mémoire tampon de flux d'octets.|  
|[état](../Topic/wbuffer_convert::state.md)|Retourne un objet représentant l'état de la conversion.|  
  
## Configuration requise  
 **En\-tête :** \<locale\>  
  
 **Espace de noms :** std