---
title: Structure de _ATL_COM_MODULE70 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ATL::_ATL_COM_MODULE70
- ATL._ATL_COM_MODULE70
- _ATL_COM_MODULE70
dev_langs:
- C++
helpviewer_keywords:
- _ATL_COM_MODULE70 structure
- ATL_COM_MODULE70 structure
ms.assetid: 5b0b2fd0-bdeb-4c7e-8870-78fa69ace6e6
caps.latest.revision: 15
author: mikeblome
ms.author: mblome
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 4e393abb2a904a0f5e101efe3d78d0645664397b
ms.openlocfilehash: 503c2a29cf0e70020b012911c51b056f00562374
ms.contentlocale: fr-fr
ms.lasthandoff: 02/24/2017

---
# <a name="atlcommodule70-structure"></a>Structure de _ATL_COM_MODULE70
Utilisé par le code lié à COM dans ATL.  
  
## <a name="syntax"></a>Syntaxe  
  
```
struct _ATL_COM_MODULE70 {
    UINT cbSize;
    HINSTANCE m_hInstTypeLib;
    _ATL_OBJMAP_ENTRY** m_ppAutoObjMapFirst;
    _ATL_OBJMAP_ENTRY** m_ppAutoObjMapLast;
    CRITICAL_SECTION m_csObjMap;
};
```  
  
## <a name="members"></a>Membres  
 `cbSize`  
 La taille de la structure utilisée pour le contrôle de version.  
  
 `m_hInstTypeLib`  
 L’instance de descripteur pour la bibliothèque de types de ce module.  
  
 **m_ppAutoObjMapFirst**  
 Adresse de l’élément de tableau indiquant le début des entrées de mappage d’objet de ce module.  
  
 **m_ppAutoObjMapLast**  
 Adresse de l’élément de tableau indiquant la fin des entrées de mappage d’objet de ce module.  
  
 `m_csObjMap`  
 Section critique pour sérialiser l’accès pour les entrées de mappage d’objet. Utilisé en interne par ATL.  
  
## <a name="remarks"></a>Remarques  
 [_ATL_COM_MODULE](atl-typedefs.md#_atl_com_module) est défini comme un typedef de `_ATL_COM_MODULE70`.  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** atlbase.h  
  
## <a name="see-also"></a>Voir aussi  
 [Structures](../../atl/reference/atl-structures.md)






