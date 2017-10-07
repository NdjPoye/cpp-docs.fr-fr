---
title: _bstr_t::operator +=, + | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- _bstr_t::operator+
- _bstr_t::operator+=
dev_langs:
- C++
helpviewer_keywords:
- += operator [C++], appending strings
- + operator [C++], _bstr_t objects
ms.assetid: d28316ce-c2c8-4a38-bdb3-44fa4e582c44
caps.latest.revision: 6
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: 0ba8936df56359523a76992866642521f899af69
ms.contentlocale: fr-fr
ms.lasthandoff: 09/25/2017

---
# <a name="bstrtoperator--"></a>_bstr_t::operator +=, +
**Section spécifique à Microsoft**  
  
 Ajoute des caractères à la fin de l'objet `_bstr_t` ou concatène deux chaînes.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
      _bstr_t& operator+=(  
   const _bstr_t& s1   
);  
_bstr_t operator+(  
   const _bstr_t& s1   
);  
friend _bstr_t operator+(  
   const char* s2,  
   const _bstr_t& s1   
);  
friend _bstr_t operator+(  
   const wchar_t* s3,  
   const _bstr_t& s1   
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 *s1*  
 Objet `_bstr_t`.  
  
 *s2*  
 Chaîne multioctet.  
  
 `s3`  
 Chaîne Unicode.  
  
## <a name="remarks"></a>Remarques  
 Ces opérateurs exécutent une concaténation de chaînes :  
  
-   **opérateur += (***s1***)** ajoute caractères encapsulé `BSTR` de *s1* à la fin de encapsuléedel’objet`BSTR`.      
  
-   **operator + (***s1***)** retourne le nouvel `_bstr_t` qui est formé en concaténant de cet objet `BSTR` avec celle de *s1*.      
  
-   **operator + (***s2***&#124;** *s1***)** retourne un nouveau `_bstr_t` qui est formé en concaténant une chaîne multioctet *s2*, il est converti au format Unicode, avec la `BSTR` encapsulé dans *s1*.          
  
-   **operator + (** `s3` **,***s1***)** retourne un nouveau `_bstr_t` qui est formé en concaténant une chaîne Unicode `s3` avec la `BSTR` encapsulé dans *s1*.        
  
 **FIN de la section spécifique à Microsoft**  
  
## <a name="see-also"></a>Voir aussi  
 [_bstr_t, classe](../cpp/bstr-t-class.md)
