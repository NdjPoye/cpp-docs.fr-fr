---
title: codecvt_byname, classe | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: xlocale/std::codecvt_byname
dev_langs: C++
helpviewer_keywords: codecvt_byname class
ms.assetid: b63b6c04-f60c-47b9-8e30-a933f24a8ffb
caps.latest.revision: "24"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 7b35b2c32f6472d2b1c7124d2681feeda1f42793
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="codecvtbyname-class"></a>codecvt_byname, classe
Classe de modèle dérivée qui décrit un objet susceptible de servir de facette d'assemblage de paramètres régionaux donnés, permettant ainsi la récupération d'informations spécifiques à une zone culturelle concernant les conversions.  
  
## <a name="syntax"></a>Syntaxe  
  
```
template <class CharType, class Byte, class StateType>
class codecvt_byname: public codecvt<CharType, Byte, StateType> {
public:
    explicit codecvt_byname(
    const char* _Locname,
    size_t _Refs = 0);
```  
  
```
explicit codecvt_byname(
    const string& _Locname,
    size_t _Refs = 0);
```  
  
```
protected:
    virtual ~codecvt_byname();

};
```  
  
#### <a name="parameters"></a>Paramètres  
 `_Locname`  
 Paramètres régionaux nommés.  
  
 `_Refs`  
 Nombre initial de références.  
  
## <a name="remarks"></a>Notes  
 Les facettes byname sont créées automatiquement pendant la construction de paramètres régionaux nommés.  
  
 Leur comportement est déterminé par les paramètres régionaux nommés `_Locname`. Chaque constructeur initialise son objet de base avec [odecvt](../standard-library/codecvt-class.md)\<CharType, Byte, StateType>( `_Refs`).  
  
## <a name="requirements"></a>Configuration requise  
 **En-tête :** \<locale>  
  
 **Espace de noms :** std  
  
## <a name="see-also"></a>Voir aussi  
 [Sécurité des threads dans la bibliothèque standard C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)



