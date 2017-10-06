---
title: _com_ptr_t::GetActiveObject | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- _com_ptr_t::GetActiveObject
dev_langs:
- C++
helpviewer_keywords:
- GetActiveObject method [C++]
ms.assetid: 2fa94853-0410-4620-91f2-136dae923f9f
caps.latest.revision: 9
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
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: a61e41c750fdf5865a475d92ba9e1def0aefd748
ms.contentlocale: fr-fr
ms.lasthandoff: 09/25/2017

---
# <a name="comptrtgetactiveobject"></a>_com_ptr_t::GetActiveObject
**Section spécifique à Microsoft**  
  
 Joint à une instance existante d’un objet avec un **CLSID** ou **ProgID**.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
      HRESULT GetActiveObject(  
   const CLSID& rclsid   
) throw( );  
HRESULT GetActiveObject(  
   LPCWSTR clsidString   
) throw( );  
HRESULT GetActiveObject(  
   LPCSTR clsidStringA   
) throw( );  
```  
  
#### <a name="parameters"></a>Paramètres  
 `rclsid`  
 Le **CLSID** d’un objet.  
  
 `clsidString`  
 Une chaîne Unicode qui contient un **CLSID** (en commençant par «**{**») ou un **ProgID**.  
  
 `clsidStringA`  
 Chaîne multioctet, à l’aide de la page de codes ANSI, qui contient un **CLSID** (en commençant par «**{**») ou un **ProgID**.  
  
## <a name="remarks"></a>Remarques  
 Ces fonctions membres appellent `GetActiveObject` pour récupérer un pointeur vers un objet en cours d'exécution qui a été inscrit avec OLE, puis des requêtes pour le type d'interface de ce pointeur intelligent. Le pointeur résultant est alors encapsulé dans cet objet `_com_ptr_t`. **Version** est appelé pour décrémenter le décompte de références du pointeur précédemment encapsulé. Cette routine retourne l'objet `HRESULT` pour indiquer un succès ou un échec.  
  
-   **GetActiveObject (**`rclsid`**)** joint à une instance existante d’un objet avec un **CLSID**.      
  
-   **GetActiveObject (**`clsidString`**)** joint à une instance existante d’un objet avec une chaîne Unicode qui contient un **CLSID** (en commençant par «**{**») ou un **ProgID**.      
  
-   **GetActiveObject (**`clsidStringA`**)** joint à une instance existante d’un objet avec une chaîne de caractères multioctets qui contient un **CLSID** (en commençant par «**{**») ou un **ProgID**.     Appels [MultiByteToWideChar](http://msdn.microsoft.com/library/windows/desktop/dd319072), qui suppose que la chaîne figure dans la page de codes ANSI plutôt que sur une page de codes OEM.  
  
 **FIN de la section spécifique à Microsoft**  
  
## <a name="see-also"></a>Voir aussi  
 [_com_ptr_t, classe](../cpp/com-ptr-t-class.md)
