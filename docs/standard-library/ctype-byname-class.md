---
title: ctype_byname, classe | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- xlocale/std::ctype_byname
dev_langs:
- C++
helpviewer_keywords:
- ctype_byname class
ms.assetid: a5cec021-a1f8-425f-8757-08e6f064b604
caps.latest.revision: 22
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 65f4e356ad0d46333b0d443d0fd6ac0b9f2b6f58
ms.openlocfilehash: 5f57ef8eadf5ea963ef4a8b8c1eaa7b6ec48ee6d
ms.contentlocale: fr-fr
ms.lasthandoff: 10/03/2017

---
# <a name="ctypebyname-class"></a>ctype_byname, classe
Classe de modèle dérivée qui décrit un objet pouvant servir de facette ctype de paramètres régionaux donnés, permettant ainsi la classification des caractères et la conversion des caractères entre des jeux de caractères natifs, de casse ou de paramètres régionaux spécifiés.  
  
## <a name="syntax"></a>Syntaxe  
  
```
template <class _Elem>
class ctype_byname : public ctype<_Elem>
{
public:
    explicit ctype_byname(
    const char* _Locname,
    size_t _Refs = 0);

    explicit ctype_byname(
    const string& _Locname,
    size_t _Refs = 0);

protected:
    virtual __CLR_OR_THIS_CALL ~ctype_byname();

};
```  
  
## <a name="remarks"></a>Remarques  
 Leur comportement est déterminé par les paramètres régionaux nommés `_Locname`. Chaque constructeur initialise son objet de base avec [ctype](../standard-library/ctype-class.md)\<CharType>( `_Refs`) ou l’équivalent pour la classe de base `ctype<char>`.  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** \<locale>  
  
 **Espace de noms :** std  
  
## <a name="see-also"></a>Voir aussi  
 [Sécurité des threads dans la bibliothèque standard C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)




