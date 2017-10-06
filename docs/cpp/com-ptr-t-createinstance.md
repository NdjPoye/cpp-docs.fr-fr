---
title: _com_ptr_t::CreateInstance | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- _com_ptr_t::CreateInstance
dev_langs:
- C++
helpviewer_keywords:
- CreateInstance method [C++]
ms.assetid: ab89b0e1-9da3-4784-a079-58b17340f111
caps.latest.revision: 6
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
ms.openlocfilehash: 1c07f7366c76c96580fc989475bd7f5ea23a38fe
ms.contentlocale: fr-fr
ms.lasthandoff: 09/25/2017

---
# <a name="comptrtcreateinstance"></a>_com_ptr_t::CreateInstance
**Section spécifique à Microsoft**  
  
 Crée une instance d’un objet avec un **CLSID** ou **ProgID**.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
      HRESULT CreateInstance(  
   const CLSID& rclsid,  
   IUnknown* pOuter=NULL,  
   DWORD dwClsContext = CLSCTX_ALL   
) throw( );  
HRESULT CreateInstance(  
   LPCWSTR clsidString,  
   IUnknown* pOuter=NULL,  
   DWORD dwClsContext = CLSCTX_ALL   
) throw( );  
HRESULT CreateInstance(  
   LPCSTR clsidStringA,  
   IUnknown* pOuter=NULL,  
   DWORD dwClsContext = CLSCTX_ALL   
) throw( );  
```  
  
#### <a name="parameters"></a>Paramètres  
 `rclsid`  
 Le **CLSID** d’un objet.  
  
 `clsidString`  
 Une chaîne Unicode qui contient un **CLSID** (en commençant par «**{**») ou un **ProgID**.  
  
 `clsidStringA`  
 Chaîne multioctet, à l’aide de la page de codes ANSI, qui contient un **CLSID** (en commençant par «**{**») ou un **ProgID**.  
  
 `dwClsContext`  
 Contexte d'exécution du code exécutable.  
  
 `pOuter`  
 Inconnu externe pour [agrégation](../atl/aggregation.md).  
  
## <a name="remarks"></a>Remarques  
 Ces fonctions membres appellent `CoCreateInstance` pour créer un objet COM puis des requêtes pour le type d'interface de ce pointeur intelligent. Le pointeur résultant est alors encapsulé dans cet objet `_com_ptr_t`. **Version** est appelé pour décrémenter le décompte de références du pointeur précédemment encapsulé. Cette routine retourne l'objet `HRESULT` pour indiquer un succès ou un échec.  
  
-   **CreateInstance (** `rclsid` **,**`dwClsContext`**)** crée une instance en cours d’exécution d’un objet avec un **CLSID**.        
  
-   **CreateInstance (** `clsidString` **,**`dwClsContext`**)** crée une instance en cours d’exécution d’un objet avec une chaîne Unicode qui contient un **CLSID** (en commençant par «**{**») ou un **ProgID**.        
  
-   **CreateInstance (** `clsidStringA` **,**`dwClsContext`**)** crée une instance en cours d’exécution d’un objet avec une chaîne de caractères multioctets qui contient un ** CLSID** (en commençant par «**{**») ou un **ProgID**.       Appels [MultiByteToWideChar](http://msdn.microsoft.com/library/windows/desktop/dd319072), qui suppose que la chaîne figure dans la page de codes ANSI plutôt que sur une page de codes OEM.  
  
 **FIN de la section spécifique à Microsoft**  
  
## <a name="see-also"></a>Voir aussi  
 [_com_ptr_t, classe](../cpp/com-ptr-t-class.md)
