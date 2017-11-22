---
title: time_get_byname, classe | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: xloctime/std::time_get_byname
dev_langs: C++
helpviewer_keywords: time_get_byname class
ms.assetid: 6e54153e-da40-4bb9-a942-1a6ce57b30c9
caps.latest.revision: "25"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: f32cb9d5412cc8f6c0f053e8ad8c43fe7a197de5
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="timegetbyname-class"></a>time_get_byname, classe
La classe de modèle dérivée décrit un objet pouvant servir de facette de paramètres régionaux de type `time_get`\<CharType, InputIterator>.  
  
## <a name="syntax"></a>Syntaxe  
  
```
template <class Elem, class InputIterator =
    istreambuf_iterator<CharType, char_traits<CharType>>>
class time_get_byname : public time_get<CharType, InputIterator>
{
public:
    explicit time_get_byname(
    const char* _Locname,
    size_t _Refs = 0);

    explicit time_get_byname(
    const string& _Locname,
    size_t _Refs = 0);

protected:
    virtual ~time_get_byname()
};
```  
  
#### <a name="parameters"></a>Paramètres  
 `_Locname`  
 Paramètres régionaux nommés.  
  
 `_Refs`  
 Nombre initial de références.  
  
## <a name="requirements"></a>Spécifications  
 Son comportement est déterminé par les paramètres régionaux nommés `_Locname`. Chaque constructeur initialise son objet de base avec [time_get](../standard-library/time-get-class.md#time_get)\<CharType, InputIterator>( `_Refs`).  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** \<locale>  
  
 **Espace de noms :** std  
  
## <a name="see-also"></a>Voir aussi  
 [Sécurité des threads dans la bibliothèque standard C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)


