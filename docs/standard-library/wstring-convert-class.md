---
title: "wstring_convert, classe | Microsoft Docs"
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
  - "cvt.wstring_convert"
  - "wstring_convert"
  - "stdext::cvt::wstring_convert"
  - "cvt::wstring_convert"
  - "wstring/stdext::cvt::wstring_convert"
  - "stdext.cvt.wstring_convert"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "wstring_convert (classe)"
ms.assetid: e34f5b65-d572-4bdc-ac69-20778712e376
caps.latest.revision: 25
caps.handback.revision: 15
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# wstring_convert, classe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

La classe de modèle `wstring_convert` effectue des conversions entre une chaîne étendue et une chaîne d'octets.  
  
## Syntaxe  
  
```  
template<  
    class Codecvt,  
    class Elem = wchar_t  
>  
class wstring_convert  
```  
  
#### Paramètres  
 Codecvt  
 Facette [locale](../standard-library/locale-class.md) qui représente l'objet de conversion.  
  
 Elem  
 Type d'élément à caractères larges.  
  
## Notes  
 La classe de modèle décrit un objet qui contrôle les conversions entre des objets de chaîne étendue de la classe `std::basic_string<Elem>` et des objets de chaîne d'octets de la classe `std::basic_string<char>` \(également appelée `std::string`\). La classe de modèle définit les types `wide_string` et `byte_string` comme synonymes de ces deux types. La conversion entre une séquence de valeurs `Elem` \(stockée dans un objet `wide_string`\) et des séquences multioctets \(stockées dans un objet `byte_string`\) est effectuée par un objet de classe `Codecvt<Elem, char, std::mbstate_t>`, qui répond aux exigences de la facette de conversion de code standard `std::codecvt<Elem, char, std::mbstate_t>`.  
  
 Un objet de cette classe de modèle stocke :  
  
-   une chaîne d'octets à afficher en cas d'erreur ;  
  
-   une chaîne étendue à afficher en cas d'erreur ;  
  
-   un pointeur vers l’objet de conversion alloué \(qui est libéré quand l’objet wbuffer\_convert est détruit\) ;  
  
-   un objet d'état de conversion de type [state\_type](../Topic/wstring_convert::state_type.md) ;  
  
-   un décompte des conversions.  
  
### Constructeurs  
  
|||  
|-|-|  
|[wstring\_convert](../Topic/wstring_convert::wstring_convert.md)|Construit un objet de type `wstring_convert`.|  
  
### Typedefs  
  
|||  
|-|-|  
|[byte\_string](../Topic/wstring_convert::byte_string.md)|Type qui représente une chaîne d'octets.|  
|[wide\_string](../Topic/wstring_convert::wide_string.md)|Type qui représente une chaîne étendue.|  
|[state\_type](../Topic/wstring_convert::state_type.md)|Type qui représente l'état de conversion.|  
|[int\_type](../Topic/wstring_convert::int_type.md)|Type qui représente un entier.|  
  
### Fonctions membres  
  
|||  
|-|-|  
|[from\_bytes](../Topic/wstring_convert::from_bytes.md)|Convertit une chaîne d'octets en chaîne étendue.|  
|[to\_bytes](../Topic/wstring_convert::to_bytes.md)|Convertit une chaîne étendue en chaîne d'octets.|  
|[converted](../Topic/wstring_convert::converted.md)|Retourne le nombre de conversions réussies.|  
|[état](../Topic/wstring_convert::state.md)|Retourne un objet représentant l'état de la conversion.|  
  
## Configuration requise  
 **En\-tête :** \<locale\>  
  
 **Espace de noms :** std