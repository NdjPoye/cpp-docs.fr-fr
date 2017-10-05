---
title: time_put_byname, classe | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- xloctime/std::time_put_byname
dev_langs:
- C++
helpviewer_keywords:
- time_put_byname class
ms.assetid: e08c2348-64d2-4ace-98b1-1496e14c7b1a
caps.latest.revision: 25
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.mt:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: MT
ms.sourcegitcommit: 65f4e356ad0d46333b0d443d0fd6ac0b9f2b6f58
ms.openlocfilehash: ba50414643d430798912e6a7a25d3fe9c49c1b9a
ms.contentlocale: fr-fr
ms.lasthandoff: 10/03/2017

---
# <a name="timeputbyname-class"></a>time_put_byname, classe
La classe de modèle dérivée décrit un objet pouvant servir de facette de paramètres régionaux du type `time_put`\< CharType, OutputIterator >.  
  
## <a name="syntax"></a>Syntaxe  
  
```
template <class CharType, class OutIt = ostreambuf_iterator<CharType, char_traits<CharType>>>
class time_put_byname : public time_put<CharType, OutputIterator>
{
public:
    explicit time_put_byname(
    const char* _Locname,
    size_t _Refs = 0);

    explicit time_put_byname(
    const string& _Locname,
    size_t _Refs = 0);

protected:
    virtual ~time_put_byname();

};
```  
  
#### <a name="parameters"></a>Paramètres  
 `_Locname`  
 Nom de paramètres régionaux.  
  
 `_Refs`  
 Nombre initial de références.  
  
## <a name="remarks"></a>Notes  
 Son comportement est déterminé par les paramètres régionaux [nommés](../standard-library/locale-class.md#name) `_Locname`. Chaque constructeur initialise son objet de base avec [time_put](../standard-library/time-put-class.md#time_put)\<CharType, OutputIterator>( `_Refs`).  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** \<locale>  
  
 **Espace de noms :** std  
  
## <a name="see-also"></a>Voir aussi  
 [Sécurité des threads dans la bibliothèque standard C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)




