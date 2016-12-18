---
title: "_bstr_t, classe | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "_bstr_t"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_bstr_t (classe)"
  - "BSTR (objet)"
  - "BSTR (objet), encapsulation COM"
ms.assetid: 58841fef-fe21-4a84-aab9-780262b5201f
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# _bstr_t, classe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Section spécifique à Microsoft**  
  
 Un objet `_bstr_t` encapsule le [type de données BSTR](http://msdn.microsoft.com/fr-fr/1b2d7d2c-47af-4389-a6b6-b01b7e915228).  La classe gère l'allocation et la désallocation des ressources via des appels de fonction adressés à **SysAllocString** et **SysFreeString**, ainsi qu'à d'autres API `BSTR` en fonction des besoins.  La classe `_bstr_t` utilise le décompte de références pour éviter une charge excessive.  
  
### Construction  
  
|||  
|-|-|  
|[\_bstr\_t](../cpp/bstr-t-bstr-t.md)|Construit un objet `_bstr_t`.|  
  
### Opérations  
  
|||  
|-|-|  
|[Assign](../cpp/bstr-t-assign.md)|Copie un `BSTR` dans le `BSTR` encapsulé par un `_bstr_t`.|  
|[Attacher](../cpp/bstr-t-attach.md)|Lie un wrapper `_bstr_t` à un `BSTR`.|  
|[copy](../cpp/bstr-t-copy.md)|Construit une copie du `BSTR` encapsulé.|  
|[Detach](../cpp/bstr-t-detach.md)|Retourne le `BSTR` encapsulé par un `_bstr_t` et détache `BSTR` du `_bstr_t`.|  
|[GetAddress](../cpp/bstr-t-getaddress.md)|Pointe vers le `BSTR` encapsulé par un `_bstr_t`.|  
|[GetBSTR](../cpp/bstr-t-getbstr.md)|Pointe sur le début du `BSTR` encapsulé par l'objet `_bstr_t`.|  
|[length](../cpp/bstr-t-length.md)|Retourne le nombre de caractères du `_bstr_t`.|  
  
### Opérateurs  
  
|||  
|-|-|  
|[opérateur \=](../cpp/bstr-t-operator-equal.md)|Assigne une nouvelle valeur à un objet `_bstr_t` existant.|  
|[opérateur \+\=](../cpp/bstr-t-operator-add-equal-plus.md)|Ajoute des caractères à la fin de l'objet `_bstr_t`.|  
|[opérateur \+](../cpp/bstr-t-operator-add-equal-plus.md)|Concatène deux chaînes.|  
|[opérateur \!](../cpp/bstr-t-operator-logical-not.md)|Vérifie si le `BSTR` encapsulé est une chaîne **NULL**.|  
|[opérateur \=\=, \!\=, \<, \>, \<\=, \>\=](../cpp/bstr-t-relational-operators.md)|Compare deux objets `_bstr_t`.|  
|[opérateur wchar\_t\* &#124; char\*](../cpp/bstr-t-wchar-t-star-bstr-t-char-star.md)|Extrayez les pointeurs dans l'objet `BSTR` Unicode ou multioctets encapsulé.|  
  
## FIN de la section spécifique à Microsoft  
  
## Configuration requise  
 **En\-tête :** comutil.h  
  
 **Bibliothèque :** comsuppw.lib ou comsuppwd.lib \(voir [\/Zc:wchar\_t \(wchar\_t est un type natif\)](../build/reference/zc-wchar-t-wchar-t-is-native-type.md) pour plus d'informations\)  
  
## Voir aussi  
 [Classes du support COM du compilateur](../cpp/compiler-com-support-classes.md)