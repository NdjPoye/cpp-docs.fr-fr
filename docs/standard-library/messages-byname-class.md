---
title: messages_byname, classe | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- messages_byname
- std::messages_byname
- std.messages_byname
- xlocmes/std::messages_byname
dev_langs:
- C++
helpviewer_keywords:
- messages_byname class
ms.assetid: c6c64841-3e80-43c8-b54c-fed41833ad6b
caps.latest.revision: 22
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
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
translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: f72361dec79e82a5e4f531ad686978010f01450e
ms.lasthandoff: 02/24/2017

---
# <a name="messagesbyname-class"></a>messages_byname, classe
La classe de modèle dérivée décrit un objet pouvant servir de facette de message de paramètres régionaux donnés, permettant ainsi la récupération de messages localisés.  
  
## <a name="syntax"></a>Syntaxe  
  
```
template <class CharType>
class messages_byname : public messages<CharType> {
public:
    explicit messages_byname(
    const char *_Locname,
    size_t _Refs = 0);

    explicit messages_byname(
    const string& _Locname,
    size_t _Refs = 0);

protected:
    virtual ~messages_byname();

};
```  
  
#### <a name="parameters"></a>Paramètres  
 `_Locname`  
 Paramètres régionaux nommés.  
  
 `_Refs`  
 Nombre initial de références.  
  
## <a name="remarks"></a>Remarques  
 Son comportement est déterminé par les paramètres régionaux nommés `_Locname`. Chaque constructeur initialise son objet de base avec [messages](../standard-library/messages-class.md#messages__messages)\<CharType>( `_Refs`).  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** \<locale>  
  
 **Espace de noms :** std  
  
## <a name="see-also"></a>Voir aussi  
 [Sécurité des threads dans la bibliothèque standard C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)




